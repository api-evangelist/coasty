---
name: Schedule recurring automation
description: Create a recurring Coasty schedule, attach an HMAC-authenticated webhook trigger, fire it on demand, and inspect run history.
api: openapi/coasty-openapi-original.json
operations: [createSchedule, addTrigger, runScheduleNow, listScheduleRuns]
---

# Schedule recurring automation

Use this to run a task on a cron/frequency cadence or from an external webhook.

## Auth & conventions
- `X-API-Key: sk-coasty-{live|test}-...`. Creating schedules and running-now are free but require a $0.20 API-wallet balance as an anti-abuse gate.

## Steps
1. **Create the schedule** — `createSchedule` (`POST /v1/schedules`) with `machine_id`, `task_prompt`, and either `cron` (+ `timezone`) or `frequency`. Store the `id`.
2. **Attach a trigger** — `addTrigger` (`POST /v1/schedules/{schedule_id}/triggers`) with `kind: webhook` (or `chain`). Store the returned `webhook_url` and one-time `webhook_secret`.
3. **Fire on demand** — `runScheduleNow` (`POST /v1/schedules/{schedule_id}/run`), or have your external system POST to `POST /v1/triggers/webhook/{webhook_id}` with a valid `Coasty-Signature`.
4. **Inspect history** — `listScheduleRuns` (`GET /v1/schedules/{schedule_id}/runs`); each `ScheduleRunRecord` has `status`, `trigger`, `duration_seconds`, and `credits_charged`.

## Rules
- Verify inbound webhook fires: `signed_payload = "<t>." + raw_body`; `compare_digest(HMAC-SHA256(secret, signed_payload), v1)`; reject timestamps older than 5 minutes.
- Default fire limit is 60/min per webhook. Pause/resume with `pauseSchedule` / `resumeSchedule`.
- Long-running scheduled jobs bill 10 credits/minute (min 20 to start, max 6h).
