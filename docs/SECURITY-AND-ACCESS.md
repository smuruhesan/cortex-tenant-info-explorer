# Security and Access — Cortex TAC Tenant Info Explorer

**Internal confidential.** Keep this repository private within approved company systems. Do not publish on public GitHub/GitHub Pages or on uncontrolled cloud infrastructure.

## Trust boundaries

- `index.html` is a static/offline distribution and documentation portal. It embeds original scripts as inert JSON data. Merely opening the page does not run either script or contact internal/external systems.
- GitLab About Info runs on the exact internal GitLab hostname with the engineer's existing GitLab session. Access is subject to GitLab permissions.
- Grafana Tenant Investigator runs only in an approved Grafana tab, reads tenant-scoped telemetry through the existing authenticated Grafana session and must retain datasource, identity and scope guards.
- The tools do not share authentication state or copy credentials between systems.

## Findings needing review before broad distribution

1. **External dependency in GitLab bookmarklet.** The submitted script attempts to load `js-yaml@4.1.0` from `cdnjs.cloudflare.com` when `jsyaml` isn't already available. This is an external third-party script executed in the authenticated internal GitLab page. Verify company policy, SRI, dependency governance and CSP compatibility; prefer an approved internal, version-pinned, independently validated distribution in a later code-reviewed update. Do not silently modify the current script because it changes parsing behavior.
2. **DOM output sanitization in GitLab tool.** Several strings originating from GitLab YAML data are concatenated into `innerHTML`. Although some paths escape markup, not all output paths are consistently escaped. This creates a potential HTML-injection/XSS risk if repository values are malicious. Require comprehensive output encoding / safe DOM construction prior to general rollout.
3. **Identity, licence and internal telemetry data.** Both tools process confidential information. The Grafana HTML reports embed evidence (including response bodies and PromQL); they MUST NOT be committed to this repository.
4. **CSP and browser bookmarklet policy.** Company-managed Chrome may disallow `javascript:` bookmarklets, clipboard access or DevTools pasting. Don't bypass browser/security controls. Use an approved installation path or consult internal IT/security.

## Safe repository policy

- Publish only verified tool binaries and human-reviewed documentation in an approved **private** internal repo.
- Do not commit tenant reports, exports, raw Grafana results, Slack snapshots, CLCS associations, access tokens, passwords, cookies or sensitive API credentials.
- Do not use public cloud CDNs or npm dependencies in the installation portal; it is intentionally self-contained.
- Retain SHA-256 checks and immutable version folders. For subsequent signed releases, build version metadata from the authoritative source and rerun the full test suite; this distribution was packaged from supplied compiled assets.
- Test installation and relevant regional workflows in managed Chrome before a wider rollout.

## Access escalation

- No GitLab access → contact a Cortex TAC SME.
- No Grafana access → request through the normal company approval process.
- Do not change datasource allowlists or relax tenant identity guards to work around denied access.
