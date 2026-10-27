# Version and Release Information

**Cortex TAC Tenant Info Explorer — Version 1.0.0.0**

| Component | Team distribution version | Host |
|---|---|---|
| About Info Explorer | 1.0.0.0 | GitLab |
| Tenant Investigator | 1.0.0.0 | Grafana |

This package gives the team one installer page, independent tools and their respective user guides. It does not include the separate Query Launcher for Marvel.

## Packaging integrity

- GitLab and Grafana executables have new version strings for the internal distribution. Application search and diagnostics logic was not intentionally changed.
- The portal embeds the same Grafana launcher bytes as `tenant-investigator-grafana/tenant-investigator.js`; the bookmarklet file contains its URL-encoded form. There is no separate installer HTML in this simplified repository.
- `SHA256SUMS` covers the four executable/bookmarklet files, the portal and documentation.
- No customer reports or raw Grafana telemetry are included.

**Engineering release note:** Version labels were updated in the supplied compiled assets rather than rebuilt from the full original source workspace. Existing development regression results therefore do not independently certify the repackaged bytes. Release owners should confirm runtime acceptance on their managed Chrome/Grafana/GitLab environment and, for a formally signed build, regenerate this version from the authoritative source repository.
