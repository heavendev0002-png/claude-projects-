---
name: microsoft-simulator-project
description: "User's Word Processing Simulator (Angular 16, iframe plugin) project — status, workflow with Antigravity, open items as of 2026-10-13"
metadata:
  node_type: memory
  type: project
  originSessionId: efa0d84a-b8d6-4ebb-98f4-7d21a107804c
  modified: 2026-10-20T16:01:43.733Z
---

User builds a Word Processing Simulator (Angular 16, repo "microsoft-simulator" / word-processing-simulator, runs at http://localhost:4200) for a client LMS. Part of a 3-app deal (Word $800, then Excel, PowerPoint; $2,400 total). Embedded via iframe, postMessage contract: pluginReady → PLUGIN_DATA_IN → activityCompleted; also PAUSE, FORCE_FINISH, PREFERENCE_CHANGED. Client: Veda Acosta. Client wants Microsoft Word ribbon UI (NOT Google Docs, never mention Google Docs in prompts). Variables stays under Tools, as a dialog. Client delivers static build folders (no /word routes) — recommended 3 separate builds; awaiting client reply on single-build vs 3-builds.

Workflow: user does the coding through the "Antigravity" AI agent; I write prompts for it and review its replies/diffs. Prompts must have strict rules (touch only what's asked, diagnose before fixing, show diff, run Karma). User wants short, token-saving prompts; do not include git commit/push unless asked. User also asks for short client updates and detailed DPRs (daily progress reports).

Status at 2026-10-13 end: ~58 Karma tests passing; pushed to GitHub (commit e8894ad on 10-12). Done: bugs 1–3, harness 14 lessons, README licenses, ribbon rebuild (Insert/Layout/References), page break, header/footer, image resize handles, deletion of all 11 insertables, dark mode, Find/Replace left nav pane, File tab disabled, comments gutter, Force Finish fix, Variables dialog, Word Count removed, paper size/margins fix, instruction audit, Insert icon alignment, Paragraph group layout.
Open: Find/Replace "Result X of Y" counter never fixed; light-mode yellow selection fix unconfirmed; same icon-alignment fix maybe for Layout/References; Lovable/OpenCode host test site (localhost:5000) — "Activity not found" bug and auto-advance-to-next-lesson request pending; Excel spec not yet received.

Code review 2026-10-14 (user-approved read-only pass): AppComponent (1900 lines) IS the Word editor and calls bridge.init('word') — no shell yet; shared/ lib already typed for word|excel|powerpoint. Found: host DARK theme never applies Word dark styles (isDarkTheme reads ThemeService, nothing sets it — verified live); activity-level `comments` ignored (wordDoc.init reads task.comments; spec puts comments at activity level); find counter hardcoded "Result 1"; Replace runs regex on innerHTML (can break markup); Layout>Orientation dropdown doesn't update docSetup (likely). Client now requires top-level "app" field + lazy-loaded editors (2026-10-14). Excel/PowerPoint spec PDFs are in Downloads.

Excel phase (started 2026-10-19), decisions as of 2026-10-20: the user placed the Excel task card themselves — don't raise card position again. README is updated by the user at commit time — never mention README in Antigravity prompts. No commits/pushes until the user says so. Excel spec text: C:\Users\NS 73\Documents\excel-simulator\spreadsheet_spec.txt (Home tab working items listed there; everything else greyed out).

Full chat export: Microsoft-Simulator-Chat.html / .md in the 2026-10-14 session folder.
