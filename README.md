# Cortex TAC Tenant Info Explorer

Private internal Cortex TAC installer repository for two independent tools.

## Start here

Open **index.html**. The first screen has only **GitLab** and **Grafana** selections and a concise comparison. Select a tool to view its bookmark installation, Direct JS, and More Info tabs. No Grafana or GitLab requests are sent by the portal itself.

| Tool | Use it for | Access |
|---|---|---|
| **About Info Explorer** (GitLab, v23-Fixes) | Customer identity, desired-state tenant configuration, licences, modules and deployment details | GitLab access; otherwise contact a Cortex TAC SME |
| **Tenant Investigator** (Grafana, rc.7) | Read-only telemetry and diagnostic investigation, CLCS identifiers, links and offline reports | Authorized Grafana access; rc.7 live acceptance still pending |

### Install

Select GitLab or Grafana, then choose **Bookmark Install** (drag the button to Chrome bookmarks) or **Direct JS** (Copy JS/Download JS and run in Chrome DevTools Sources → Snippets). The supplied rc.7 Grafana installer officially documents the Direct JS route. The optional Grafana bookmarklet may be limited by Chrome's maximum bookmark-URL size or company browser policy and has not been independently proven in live Chrome.

For individual instructions read [GitLab user guide](about-info-explorer/USER-GUIDE.md) and [Grafana user guide](tenant-investigator/USER-GUIDE.md). See [Security and Access](docs/SECURITY-AND-ACCESS.md), [Release Status](docs/RELEASE-STATUS.md) and [Publishing Checklist](docs/PUBLISHING-CHECKLIST.md).

All tool JS files are preserved byte-for-byte from the supplied artifacts. The launcher SHA256 is `92c14bab34455e967f52340b5e57beaddec48a1d3ea60db75db8e83eb977df0a`. The portal is self-contained and uses no remote CSS or JS.

**IMPORTANT:** Internal-use only. Do not commit live tenant reports or raw metrics to the repository. GitLab's external YAML-library loading must be reviewed against company policy before wide release. The Cortex TAC Query Launcher is separate and intended for Marvel integration.
