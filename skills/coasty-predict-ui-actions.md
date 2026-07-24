---
name: Predict UI actions from a screenshot
description: Turn a screenshot plus an instruction into structured mouse/keyboard actions — statelessly or inside a session — and ground/parse coordinates, on any screen you control.
api: openapi/coasty-openapi-original.json
operations: [predict, createSession, sessionPredict, ground, parse, deleteSession]
---

# Predict UI actions from a screenshot

Use this to drive ANY screen (a Coasty VM, the user's desktop, a Playwright page, an emulator) — screenshot in, coordinates/actions out.

## Auth & conventions
- `X-API-Key: sk-coasty-{live|test}-...`. `predict`, `sessionPredict`, `ground`, `createSession` accept `Idempotency-Key`.
- Send screenshots as base64 PNG/JPEG WITHOUT the `data:` prefix (else `INVALID_SCREENSHOT`). Coordinates return in the space of the screenshot you sent.

## Stateless path
1. **Predict** — `predict` (`POST /v1/predict`, $0.05) with the screenshot + `instructions`. Execute the returned action locally, screenshot again, repeat until action type is `done`.
2. **Ground** — `ground` (`POST /v1/ground`, $0.03) to resolve a described UI element to `(x, y)`.
3. **Parse** — `parse` (`POST /v1/parse`, free) to convert pyautogui code into structured actions.

## Stateful path (cheaper per step)
1. **Open** — `createSession` (`POST /v1/sessions`, $0.10). Store the session `id`.
2. **Step** — `sessionPredict` (`POST /v1/sessions/{session_id}/predict`, $0.04) each turn; server keeps trajectory context.
3. **Close** — `deleteSession` (`DELETE /v1/sessions/{session_id}`) in a `finally` block to free concurrency quota. Idle sessions expire after 2h.

## Rules
- Six prompt presets for `instructions`: precise-ui, forms-data-entry, qa-regression, read-extract, cautious, fast-batch.
- If you downscaled the screenshot, scale returned coordinates back up before clicking.
