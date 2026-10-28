# Support

**Cortex TAC Tenant Info Explorer · Version 1.0.0.0**

These are internal TAC workflow tools. For questions, defects or enhancement requests, contact the internal tool maintainer or your Cortex TAC SME through the team's approved support channel. This repository does not establish a formal product support SLA.

## Where to get help

| Situation | Recommended next step |
|---|---|
| No access to GitLab or the tenant configuration project | **Contact a Cortex TAC SME.** The Explorer cannot grant access. |
| Grafana datasource is inaccessible / region cannot be investigated | Check the error shown and follow the standard internal Grafana access process. Do not bypass restrictions. |
| GitLab tool fails to parse configuration | Confirm the page/session and source permissions; ask an SME/maintainer to check YAML parser availability and source format. |
| Grafana shows missing or unknown tenant metadata | Check the selected region, datasource, source evidence and query semantics; do not assume missing telemetry means the tenant has no configuration. |
| Bookmarklet will not install or run | Try the **Direct JS** instructions in `index.html`, if allowed by company browser policy. |
| Incorrect values, UI problem or report issue | Report a reproducible, sanitized example to the maintainer. |

## What to include in a bug report

Please provide:

1. **Tool:** About Info Explorer (GitLab) or Tenant Investigator (Grafana).
2. **Version:** 1.0.0.0 and the browser/OS used.
3. **Action:** Search type or screen/function that failed (without exposing sensitive identifiers unnecessarily).
4. **Expected vs actual result:** What should have happened and what appeared.
5. **Context:** Region/datasource for Grafana, or the general GitLab configuration view, only as needed to reproduce.
6. **Sanitized evidence:** Error message and relevant console output, after removing sensitive data.

Do **not** paste raw tenant reports, CLCS IDs, customer mappings, authentication tokens, cookies or full Grafana responses into public or broadly visible GitHub issues. Use approved internal channels when restricted diagnostic evidence is necessary.

## Related resources

- [Start / Install](index.html)
- [About Info Explorer guide](docs/ABOUT-INFO-EXPLORER.md)
- [Tenant Investigator guide](docs/TENANT-INVESTIGATOR.md)
- [Troubleshooting](docs/TROUBLESHOOTING.md)
- [Security & Usage](docs/SECURITY_AND_USAGE.md)
- [Disclaimer](DISCLAIMER.md)

**Query Launcher support is separate:** The Marvel-integrated Query Launcher is not part of this repository.
