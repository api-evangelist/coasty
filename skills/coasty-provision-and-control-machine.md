---
name: Provision and control a machine
description: Provision a sandboxed VM, execute mouse/keyboard actions and shell commands on it, capture screenshots, then tear it down.
api: openapi/coasty-openapi-original.json
operations: [provisionMachine, getMachine, executeAction, executeBatch, getScreenshot, terminalExec, terminateMachine]
---

# Provision and control a machine

Use this for low-level, deterministic control of a Coasty VM.

## Auth & conventions
- `X-API-Key: sk-coasty-{live|test}-...`. A test key returns a mock VM in <50ms at 0 credits.
- `provisionMachine`, `executeAction`, `executeBatch`, `terminalExec`, and `snapshot` accept an `Idempotency-Key`. Lifecycle ops (start/stop/restart/delete/TTL) do not.

## Steps
1. **Provision** — `provisionMachine` (`POST /v1/machines`) choosing `os_type` (Linux $0.05/hr, Windows $0.09/hr) and an optional `ttl_minutes` auto-destroy lease (5–10080). Store the `id`.
2. **Confirm ready** — `getMachine` (`GET /v1/machines/{machine_id}`) until `status` is running.
3. **Act** — `executeAction` (`POST /v1/machines/{machine_id}/actions`) for one action, or `executeBatch` (`POST /v1/machines/{machine_id}/actions/batch`, ≤50 sequential). Action types: `click`, `type_text`, `key_press`, `key_combo`, `scroll`, `drag`, `move`, `wait`, `done`, `fail`.
4. **Shell** — `terminalExec` (`POST /v1/machines/{machine_id}/terminal`) to run a command.
5. **Observe** — `getScreenshot` (`GET /v1/machines/{machine_id}/screenshot`) to capture the current screen (base64 PNG/JPEG).
6. **Tear down** — always `terminateMachine` (`DELETE /v1/machines/{machine_id}`) when finished; running machines bill hourly.

## Rules
- `getConnectionDetails` returns SSH key + VNC password and is HIGH-RISK — request `connection:read` scope only when needed.
- Out-of-funds stops a machine, never destroys it; a stopped machine still bills $0.01/hr.
