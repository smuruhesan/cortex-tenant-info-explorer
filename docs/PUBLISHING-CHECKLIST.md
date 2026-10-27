# Private GitHub Publishing Checklist

- [ ] Use an approved **private internal** repository named `cortex-tac-tenant-info-explorer`.
- [ ] Verify `shasum -a 256 -c SHA256SUMS` from the repository root.
- [ ] Open `index.html` and check GitLab/Grafana selection, bookmark install, Direct JS and More Info.
- [ ] Confirm each tool loads on its intended authenticated site, with no access bypasses.
- [ ] Test the Grafana launcher in managed Chrome with a known authorized tenant in each region you plan to use.
- [ ] Check the GitLab YAML dependency and HTML output sanitization against internal application-security requirements.
- [ ] Verify no tenant reports, customer identifiers, API results, credentials or secrets have been committed.
- [ ] Share GitLab installation only with engineers with repository access; otherwise direct them to TAC SMEs.
- [ ] Keep Query Launcher in the separate Marvel workstream.

## Git commands

```bash
shasum -a 256 -c SHA256SUMS
git init
git add .
git commit -m "Publish Cortex TAC Tenant Info Explorer 1.0.0.0"
# Add and push to your company-approved private GitHub remote.
```
