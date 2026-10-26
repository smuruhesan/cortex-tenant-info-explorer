# Versions and Release Status

| Component | Version in supplied material | Confidence / status |
|---|---|---|
| About Info Explorer | `v23-Fixes` | Existing GitLab bookmarklet, syntax checked, not live tested by this packaging process; security review noted |
| Tenant Investigator | `v1.0.0-rc.7` | Internal TAC Global Release Candidate; 520/520 Node tests per development handoff; selected live regional testing and final production approval pending |
| Query Launcher | separate Marvel workstream | Not bundled in this repository |

## Files

**About Info:** original bookmarklet SHA-256 `93456b693f0e7c930c826efec8a7c0c570baad3deb9f378c124dc7903eaaf852`. Console `.js` has the same code minus its `javascript:` prefix; the checksum therefore differs.

**Grafana launcher:** original SHA-256 `92c14bab34455e967f52340b5e57beaddec48a1d3ea60db75db8e83eb977df0a`. Its original installer embeds the same content.

No raw tenant HTML report or response bodies are included. The attached rc.7 Indonesia report was used only to confirm the report metadata and behavior (not to populate sample identities in this package).

Before renaming rc.7 as production, execute real Chrome acceptance for each region supported in your deployment, verify regional datasource routing, report evidence, CLCS semantics, download and offline viewing, and complete corporate security review.
