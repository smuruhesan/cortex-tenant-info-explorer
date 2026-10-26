# About Info Explorer — User Guide

## When to use

Use About Info Explorer for **who / configured what / desired-state** questions, particularly customer name when Grafana reports `Redacted`, license setup, feature flags, configured image tags, product quotas, region, and METRO/MSSP relationships. It reads authorized GitLab configuration—not current tenant-health metrics.

## Required access

- Authenticated Chrome or supported browser session at the approved internal GitLab host.
- Read access to the relevant `tenants-config-prod` project and auxiliary frontend metadata if required.
- Access is not granted by the tool. Engineers without GitLab access must contact a Cortex TAC SME.

## Install as bookmarklet (recommended when permitted)

1. Open `../index.html` from the repository in Chrome and show the Bookmarks bar (Mac: `⌘⇧B`; Windows: `Ctrl+Shift+B`).
2. Drag **About Info Explorer** from the installation page onto the bar. Some browser policies reject large JavaScript bookmarklets.
3. If drag fails, add a bookmark manually named `About Info Explorer`. Use **Copy bookmarklet** from the portal and paste the exact text (starts with `javascript:`) in the bookmark's URL field.
4. While signed in to the internal GitLab tab, click the bookmarklet.

## Alternative: DevTools console

Choose **Copy console code** from `index.html` (or open `about-info-explorer-v23-Fixes-console.js`) and paste it into DevTools on the authenticated GitLab tab. The console version deliberately omits the `javascript:` prefix. Follow company DevTools policies.

## Usage

1. In the popup, search customer name, tenant/project ID, serial, URL or another value appearing in tenant configuration; GitLab's blob search is described in the script as literal and case-sensitive.
2. If multiple tenant configurations match, pick the intended row or select multiple rows to parse.
3. Review **Quick Summary**, configured platform/image tags, dashboard shortcuts and **Advanced Info**.
4. If METRO, MSSP or Parent Tenant information appears, interpret it as configured topology, not a real-time check.
5. Use **Copy Summary**, **Copy Full Report**, or **Download** (text). Keep all output in approved internal channels.
6. When the objective becomes *what is failing now?*, copy the LCAAS or Cortex ID and switch to Tenant Investigator in Grafana.

## Limits and safe interpretation

- GitLab configuration describes **desired state**; it may differ from observed Grafana metrics.
- Search may miss content not indexed in GitLab blob search or inaccessible to your account.
- The script uses an external CDN for YAML parsing if js-yaml is absent on the page; fallback flat parsing may omit nested configuration. Verify with an SME if information is incomplete.
- Version mapping may use a matching commit or branch fallback; check the source note.
- The UI dynamically renders GitLab values and needs a security hardening review before wide distribution.
- The bookmarklet reads internal APIs using your browser's GitLab session; do not run it on other websites.
