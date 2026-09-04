# CMS Report Manager — update feed

This repository is the update channel for the **CMS Report Manager**, the desktop
app that downloads lead exports from the CMS dealer dashboard and turns them into
visual performance reports.

| File | Purpose |
|---|---|
| `latest.json` | The update manifest: current version, download URL and SHA-256 |
| `CMS.Report.Manager.exe` | The current build |

The app checks `latest.json` once a day. If the published version is newer than
the one running, it offers an update, downloads the exe, and verifies it against
the SHA-256 in the manifest before replacing anything. A hash mismatch aborts the
update.

The application is unsigned, so Windows SmartScreen (and Smart App Control, where
enforcing) may ask for confirmation the first time a new version runs.

Nothing here contains credentials. The app reads its dashboard login from a local
`cms_credentials.env` beside the exe, which is never part of a release.
