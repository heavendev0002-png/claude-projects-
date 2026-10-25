---
name: do-not-touch-simulator-folder
description: Never read or modify D:\Mitul(AI)\word-processing-simulator — Antigravity owns all changes there
metadata:
  node_type: memory
  type: feedback
  originSessionId: efa0d84a-b8d6-4ebb-98f4-7d21a107804c
  modified: 2026-10-23T12:47:28.428Z
---

Never edit D:\Mitul(AI)\word-processing-simulator. Reading it is allowed only when the user asks for it (2026-10-23 they granted view-only access for an Excel audit) — read only what the task needs, never change files or run git commands that modify state.

**Why:** The user does all simulator changes through Antigravity and got upset when I looked inside that folder on my own (2026-10-14).

**How to apply:** For simulator work, only write prompts for Antigravity. Direct edits are OK only in folders the user hands me, e.g. the host test app D:\host-ms-word. Also: user removed unit tests; never ask Antigravity to run Karma or add tests — verify with `npm run build` and the test harness. See [[microsoft-simulator-project]].
