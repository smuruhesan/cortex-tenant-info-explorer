# Private Repository Publishing Checklist

- [ ] Create company-approved **private** repository `cortex-tac-tenant-info-explorer`.
- [ ] Confirm this ZIP has no actual restricted tenant report, Grafana response body or private customer sample identifiers.
- [ ] Confirm both uploaded original binaries are present without modification; run `shasum -a 256 -c SHA256SUMS`.
- [ ] Open `index.html` locally; confirm all download/copy buttons and GitLab bookmarklet drag/manually-copy fallback.
- [ ] Review GitLab bookmarklet external CDN (`js-yaml`) and `innerHTML` data-escaping issues with internal application/security owners before broad rollout.
- [ ] Confirm company policy permits bookmarklets/DevTools scripts in the intended managed browser environment.
- [ ] Complete real Chrome acceptance and regional compatibility checks before marking Grafana rc.7 production.
- [ ] Do not expose via public GitHub Pages, public package registries or customer portals.
- [ ] Assign maintenance ownership, release notes, changelog and incident reporting contact (prefer team alias over personal email).
- [ ] Grant GitLab tool access only via existing GitLab authorization; direct other users to Cortex TAC SMEs.
- [ ] Retain independent versions for About Info and Tenant Investigator; do not auto-load one from the other.
- [ ] Keep Query Launcher in its separate Marvel-linked project.

## Git command example (run within approved enterprise environment)

```bash
cd cortex-tac-tenant-info-explorer
shasum -a 256 -c SHA256SUMS
git init
git add .
git commit -m "Add internal Cortex TAC Tenant Info Explorer portal and tool guides"
# Then set the approved private enterprise remote and push under company policy.
```
