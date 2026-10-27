# Cortex TAC Tenant Info Explorer

**Version 1.0.0.0 · Internal Cortex TAC team**

Open **[index.html](index.html)** to choose the **GitLab About Info Explorer** or **Grafana Tenant Investigator**. Each tool has a Bookmark Install tab, a Direct JS tab, and More Info. The HTML portal does not run either tool or query a tenant when opened.

## Which tool should I use?

| Tool | When to use | Access |
|---|---|---|
| **About Info Explorer (GitLab)** | Identify customers and inspect configured tenant/licence/module/image/deployment information | GitLab project access required; otherwise contact a **Cortex TAC SME** |
| **Tenant Investigator (Grafana)** | Discover tenants and inspect operational metrics, CLCS identifiers, health diagnostics, source queries and offline reports | Authorized Grafana access |

The tools are independent. Do not paste one tool's code into the other application's website. **The Query Launcher is a separate Marvel workstream and is not included here.**

## Minimal repository layout

```text
cortex-tac-tenant-info-explorer/
├── index.html
├── README.md
├── SHA256SUMS
├── about-info-explorer-gitlab/
│   ├── about-info-explorer.js
│   └── about-info-explorer.bookmarklet.txt
├── tenant-investigator-grafana/
│   ├── tenant-investigator.js
│   └── tenant-investigator.bookmarklet.txt
└── docs/
    ├── ABOUT-INFO-EXPLORER.md
    ├── TENANT-INVESTIGATOR.md
    ├── SECURITY-AND-ACCESS.md
    ├── TROUBLESHOOTING.md
    ├── RELEASE-STATUS.md
    └── PUBLISHING-CHECKLIST.md
```

- The `.js` files are the executable console/DevTools scripts. Direct links: [GitLab JavaScript](about-info-explorer-gitlab/about-info-explorer.js) and [Grafana JavaScript](tenant-investigator-grafana/tenant-investigator.js).
- The `.bookmarklet.txt` files contain complete `javascript:` bookmark URLs; paste the whole string into a browser bookmark's URL field if drag-and-drop is unavailable.
- The **Grafana bookmarklet is very large (~655 KB)** and may be blocked or truncated by managed Chrome. For Grafana, **Direct JS / DevTools Snippets is the reliable path**.
- `index.html` contains script payloads for **offline installation**, so its Copy/Download buttons still work when opened directly from a downloaded folder. The four tool files are kept separately for version control and direct use. When changing a tool script later, also regenerate the corresponding portal payload and bookmarklet file to avoid drift.
- Do not commit raw tenant reports, Grafana query responses, customer identifiers, tokens or secrets.

## How to publish

Use an approved private internal GitHub repository. Open or download `index.html` from that repository; ordinary GitHub file previews are not a substitute for hosting the interactive page. For security and integrity checks, read [Publishing Checklist](docs/PUBLISHING-CHECKLIST.md) and [Security and Access](docs/SECURITY-AND-ACCESS.md).

From the repository root, verify the published files with:

```bash
shasum -a 256 -c SHA256SUMS
```
