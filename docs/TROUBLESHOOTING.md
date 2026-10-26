# Troubleshooting

| Symptom | Explanation / safe next step |
|---|---|
| Cannot open GitLab repository | About Info requires existing repository authorization. Contact a Cortex TAC SME. |
| GitLab bookmarklet drag fails | Create a bookmark manually; paste copied `javascript:` text in the URL field. Corporate browser policy may still block it. |
| GitLab parser only shows partial configuration | Third-party `js-yaml` may be blocked and the script falls back to a limited flat parser. Check source values with an authorized SME. |
| GitLab customer search misses known tenant | GitLab blob search is literal/case-sensitive per script, and only accessible indexed repositories are searched. Try a precise configured ID. |
| Grafana launcher doesn't open | Refresh a signed-in approved Grafana tab; confirm the correct version, DevTools policy, and that the code was pasted once. |
| Need to search by customer name in Grafana | The Grafana customer name can be Redacted. Ask a GitLab-authorized SME to resolve the customer name to LCAAS or Cortex/XDR ID. |
| Tenant found but Run Investigation disabled | Review the displayed datasource/access/compatibility reason. Don't bypass the guards. |
| Incomplete cross-region search | Verify Grafana permissions and failed-region details; do not infer a complete no-match result. |
| CLCS shows No series returned | No matching metric was returned; this is **not** proof of no subscription. Check exact tenant, region, query and range semantics in Grafana. |
| A field says Redacted | Source deliberately masked it; do not reconstruct from other IDs. |
| HTML report shows stale/different observations | Reports are immutable collection-time snapshots. Run a new investigation when current evidence is needed. |
| Clipboard button doesn't work | The portal shows a manual select-and-copy dialog if browser APIs deny clipboard access. |
| Can't open .md files from portal | Markdown links require the ZIP/repo directory structure, not only the standalone HTML. The HTML itself still includes quick instructions. |

For bugs, capture tool name, version, data-source region, a sanitized error message and steps to reproduce. Preserve restricted raw reports only in approved systems.
