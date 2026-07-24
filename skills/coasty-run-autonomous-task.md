---
name: Run an autonomous computer-use task
description: Hand Coasty a natural-language task and a machine, then drive the autonomous run to completion, streaming events and handling human-takeover pauses.
api: openapi/coasty-openapi-original.json
operations: [createRun, getRun, streamRunEvents, resumeRun, cancelRun]
---

# Run an autonomous computer-use task

Use this to run a self-verifying agent job on a Coasty machine.

## Auth & conventions
- Send `X-API-Key: sk-coasty-{live|test}-...` (or `Authorization: Bearer`). Use a `sk-coasty-test-*` key first — it is free and returns mocked VMs with identical schemas.
- Put an `Idempotency-Key` (≤128 chars) on `createRun` so a retry never double-starts a run.
- Every error is a JSON envelope: `error.{code,message,type,request_id,retryable,retry_with_same_idempotency_key}` (see `errors/coasty-problem-types.yml`).

## Steps
1. **Start the run** — `createRun` (`POST /v1/runs`) with `machine_id` and `task`. Optionally set `max_steps`, `on_awaiting_human`, `budget_cents`, and a `webhook_url`. Store the returned `id` and one-time `webhook_secret`.
2. **Watch it work** — `streamRunEvents` (`GET /v1/runs/{run_id}/events`, SSE). Handle `status`, `step`, `tool_call`, `tool_result`, `billing`, `awaiting_human`, `error`, and `done`. On reconnect, send `Last-Event-ID`.
3. **Poll if not streaming** — `getRun` (`GET /v1/runs/{run_id}`) until `status` is `succeeded`, `failed`, `cancelled`, or `timed_out`.
4. **Resume after a pause** — if `status` is `awaiting_human`, take over, then `resumeRun` (`POST /v1/runs/{run_id}/resume`).
5. **Abort** — `cancelRun` (`POST /v1/runs/{run_id}/cancel`) to stop early.

## Rules
- Runs bill per completed step (v3/v4: 5 credits; v1: 8). Guard spend with `budget_cents` and `max_steps`.
- Verify webhook deliveries with the HMAC `Coasty-Signature` header (`t=`,`v1=`) — see `conventions/coasty-conventions.yml`.
