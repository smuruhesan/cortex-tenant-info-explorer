# Tenant Investigator — User Guide

## When to use

Use Tenant Investigator to check **current observability**: tenant identity, product/licence evidence, CLCS IDs when the metric is present, agents, ingestion, performance, detection, cloud posture, modules and engineering metrics, across eligible regions accessible in Grafana. It does not replace desired-state config inspection in GitLab.

## Install / start

1. Open the approved internal Grafana in Chrome and authenticate.
2. Open [`index.html`](../index.html) and click **Copy Grafana launcher**, or open the [original rc.7 installer](releases/v1.0.0-rc.7/cortex-tac-investigator-v1.0.0-rc.7-installer.html).
3. In the Grafana tab open DevTools Console: Mac `⌥⌘J`, Windows/Linux `Ctrl+Shift+J`; paste and run once. This is **not a bookmarklet**.
4. The launcher performs local checks without Grafana data queries. Search by LCAAS, Cortex/XDR ID, project/tenant ID or support account ID.
5. A single verified tenant can auto-run after the necessary regional lookups succeed; for multiple matches use **Run Investigation** on exactly one row. All actions remain restricted to the current authorized session and tenant/datasource binding.
6. Review the Overview and diagnostics; use arrows for Grafana Explore evidence; copy the Overview or download a restricted offline HTML report.

## Understanding results

- **REDACTED:** Grafana returned an explicitly masked customer name. Don't infer the original name; authorized engineers can look up configuration in About Info.
- **NOT AVAILABLE:** field/source absent, unsupported or not accepted. View `?` evidence for the specific reason.
- **NO SERIES:** metric did not return a series within its query semantics. Not proof of absence of the relevant subscription or feature.
- **UNKNOWN:** insufficient evidence to call the check healthy or unhealthy.
- **CLCS ID(s):** source may emit multiple paired CLCS and Subscription IDs. 15-minute lookback means *seen during that window*, not fresh licensing status.
- **METRO/shared tenants:** some diagnostics or deployment inference may be unavailable by design.

## Reports and data handling

- Downloaded HTML includes query evidence and restricted telemetry. Save only in approved restricted storage; do not post publicly.
- Offline viewing does not require Grafana; Grafana evidence links will need an authenticated company session when clicked.
- Report values reflect a point in time; tenant health may change on a later run.
- If a region is inaccessible, missing or fails lookup, the UI must show the actual condition rather than pretending no tenant exists.

## Status

rc.7 has offline test evidence reported as **520/520 Node tests**, but final production acceptance is pending live browser checks for the intended regional rollout. Do not describe rc.7 as a signed global production release.


## Shared portal installation
Select **Grafana** in `index.html`. The **Direct JS** tab mirrors the approved rc.7 installer. A draggable bookmarklet is offered for convenience but is not an approved/validated substitute until its long bookmark URL has been tested in Chrome. If it fails, use **Direct JS**.
