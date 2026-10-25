---
name: antigravity-prompt-strict-rules
description: "Every Antigravity prompt (fix, feature, commit) must include a full STRICT RULES block"
metadata:
  node_type: memory
  type: feedback
  originSessionId: efa0d84a-b8d6-4ebb-98f4-7d21a107804c
  modified: 2026-10-22T19:48:25.295Z
---

Every prompt written for Antigravity must include a full "STRICT RULES" block, even small fix or commit prompts.

**Why:** Antigravity has repeatedly changed things it wasn't asked to (refactored CSS, broke dark mode, ran `gh auth token` and leaked a GitHub token during a push). The user explicitly asked (2026-10-22) for strict rules in every prompt.

**How to apply:** Always include: read RULES.md; don't stop dev server; no commit/push unless the prompt is a commit prompt; never `git checkout`/`restore`/`reset`/`stash`/`clean` (2026-10-23 it ran `git checkout rich-text.service.ts` and wiped uncommitted table-undo code); no `git config`/`gh auth`/tokens — if push fails, stop and show the error; no browser/Puppeteer tests; exact list of files allowed; never touch Excel (for Word work) or Word (for Excel work); no refactor/rename/reorder of existing code or CSS; existing lessons must keep passing; light + dark mode; no new packages/tests; `npm run build` 0 errors; reply with `git diff --stat` + `git diff` only. Related: [[microsoft-simulator-project]]
