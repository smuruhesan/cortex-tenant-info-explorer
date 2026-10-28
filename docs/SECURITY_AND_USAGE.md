# Security & Usage

**Cortex TAC Tenant Info Explorer · Version 1.0.0.0 · Internal Use Only**

This repository distributes two internal browser tools: **About Info Explorer (GitLab)** and **Tenant Investigator (Grafana)**. Both may display confidential customer, tenant, licensing, infrastructure or troubleshooting information. Use only in approved company environments.

## Access and execution

- **GitLab Explorer:** Runs within an authenticated internal GitLab session; visibility depends on the engineer's existing permissions to the underlying configuration repositories. **Without GitLab access, contact a Cortex TAC SME.**
- **Grafana Investigator:** Runs within an authenticated internal Grafana session; datasource access and tenant-scoped query guards still apply. It is designed for read-only metric retrieval and report generation.
- Neither tool grants access, reads passwords for the user, or justifies circumventing authentication, RBAC, browser policy or datasource restrictions.
- Do not execute these scripts in unrelated sites or paste code supplied from unverified sources.

## Data classification and handling

The tools may display or export customer/account references, tenant IDs, Cortex/XDR IDs, licence metadata, CLCS associations, configured features, image tags, query expressions and operational evidence.

- Treat reports, screenshots, pasted summaries and exports as **confidential internal TAC material**.
- Save artifacts only to approved company-managed storage. Share only with recipients who have a valid business need and the required authorization.
- Do not upload tenant reports or customer data to this repository, public AI tools, public issue trackers, uncontrolled file-sharing sites or personal storage.
- Do not share Grafana reports or internal GitLab configurations with customers/external parties without the applicable approval.
- When asking for support, use sanitized steps, expected/actual behavior and error messages. Keep sensitive raw evidence in approved channels.

## Data interpretation

**GitLab describes configured or intended state. Grafana shows observed telemetry.** These can differ due to deployment timing, scrape gaps, unavailable metrics, retention and source conventions. Check provenance rather than presenting either output as an unquestionable source of current truth.

- **Redacted** means the source deliberately masked a value. Do not attempt to infer or recover the original name from unauthorized sources.
- **Not available / No series / Unknown** does not by itself prove a feature is absent or a system is healthy.
- CLCS metadata observed through a 15-minute Prometheus lookback is **not** proof of current subscription health.
- Interpret diagnostic findings together with source evidence and human technical judgment.

## Network and third-party dependencies

- The shared `index.html` is an offline installation portal; opening the page alone should not run either investigation.
- The Grafana Investigator communicates with the authenticated Grafana environment and must retain existing tenant/datasource scope validation.
- **GitLab Explorer dependency:** The supplied GitLab script may dynamically load `js-yaml` from an external public CDN when the parser is not already present. It also has HTML-rendering paths requiring careful output-encoding review. These are security considerations for maintainers; do not assume this dependency has received formal company approval. If your environment blocks it, consult the maintainer/SME rather than bypassing CSP or network restrictions.
- Bookmarklets and clipboard/DevTools paste actions can be restricted in managed browsers. Honor those restrictions.

## Repository and release hygiene

Keep the repository private and use it only in a company-approved hosting environment. It should contain tool sources, bookmark URLs and reviewed documentation—not real tenant data.

**Never commit:**

- Grafana downloaded investigation HTML or response bodies;
- GitLab customer configurations copied from restricted repositories;
- CLCS/customer identity exports, support logs or screenshots containing sensitive details;
- browser cookies, sessions, access tokens, secrets or credentials.

Verify release files against `SHA256SUMS` when available. If an executable script is updated, refresh any embedded portal payload and `.bookmarklet.txt` copy together so the installation methods remain consistent.

## Approval and responsibility

This is an internal TAC workflow aid, not an authorization to bypass company security controls. Do not claim formal InfoSec certification, independent security clearance or official product support unless those approvals exist. Each engineer remains responsible for confirming the intended tenant, interpreting output correctly and following internal data-handling requirements.

For related technical details, see [Security & Access](SECURITY-AND-ACCESS.md), [Disclaimer](../DISCLAIMER.md) and [Support](../SUPPORT.md).
