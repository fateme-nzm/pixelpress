# PixelPress — Project Status

Repo: https://github.com/fateme-nzm/pixelpress
Local path: H:\ffmpeg_nezam\reference-project
Local dev server: `node server.js` → http://127.0.0.1:5500 (must be running to test)

## Completed
- Phase 0 — Environment Audit: Git 2.50, Node v24.20.0, npm 11.19.0 confirmed working on Windows.
- Phase 1 — Reference project (ffmpeg-webCLI) cloned and runs locally.
- Phase 2 — Codebase understood: docs/index.html (single-file UI+logic), docs/worker.js (ffmpeg.wasm worker), server.js (local dev server w/ COOP+COEP), docs/vercel.json (deploy config), coi-serviceworker.js (COOP/COEP shim for static hosts — NOT currently wired into index.html).
- Phase 3 — Personal identity: renamed to PixelPress, public GitHub repo created, attribution + CHANGES.md added per GPL-3.0.
- Phase 4 — Removed Auto-Caption (UI entry points only — see "Known items" below) and PWA/offline features (service worker registration, install prompt, manifest.json); rebranded header. Verified in browser, committed and pushed.

## Current Phase
Phase 5 — Improve Core FFmpeg Workflow (about to start; likely a light smoke-test pass since the core operations are inherited working code, not a rebuild).

## Known Items / Technical Debt
- Auto-Caption's underlying JS (Whisper transcription helper functions, ~lines 4693+ in the pre-edit file) was left in place as dead/unreachable code to avoid risky large edits under time pressure. Safe to fully remove in a later cleanup pass.
- `docs/coi-serviceworker.js` exists but is not yet referenced anywhere. It will matter later for Phase 12 (static hosting on something like GitHub Pages that can't set custom headers) — decide then whether to wire it in.
- `benchmark/video/long.mp4` (54MB) is in the repo history; GitHub warned it's over the 50MB recommended size. Not blocking, but could be removed later if repo size becomes a concern.

## Decisions Made
- Project name: PixelPress
- GitHub repo: public, https://github.com/fateme-nzm/pixelpress
- Reference base: ffmpeg-webCLI (GPL-3.0) by tejaswigowda
- Excluded from v1: Auto-Caption, PWA/offline/installable-app features, Whisper, batch cloud processing, accounts, payments (most of these were never in the reference project to begin with)

## Installed Tools (this machine)
- Git 2.50.0
- Node.js v24.20.0 / npm 11.19.0
- Chrome (primary test browser)
- PowerShell execution policy set to RemoteSigned for CurrentUser (needed for npm)

## Deployment Status
Not yet deployed publicly. Still local-only (Phase 12 will handle static hosting).

## Next Step
Quick smoke-test of core operations (Convert, Compress, Trim, Crop) to confirm nothing broke in Phase 4, then move to Phase 6 — Build Video Analyzer (first custom feature).
