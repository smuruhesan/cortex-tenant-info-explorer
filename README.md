# Cortex TAC About infor & Tenant Info Explorer

**Version 1.0.0.0 | Internal Cortex TAC Team**

Two complementary tools help TAC engineers find customer tenants, understand their configuration, and investigate operational issues.

| Tool | Platform | Primary purpose |
|---|---|---|
| **About Info Explorer** | GitLab | What is **configured** for the customer? |
| **Tenant Investigator** | Grafana | What is **running or observed** in the tenant? |

**Quick guidance:** Use GitLab to identify customers and their tenant configurations. Use Grafana to investigate tenant health, metrics, versions, and operational behavior.

---

## 1. What can I search?

This is the most important difference between the two tools.

| Search requirement | GitLab — About Info Explorer | Grafana — Tenant Investigator |
|---|---|---|
| **Customer / Account Name** | ✅ Supported | ❌ Not supported |
| **Serial Number** | ✅ Supported when recorded in GitLab | ❌ Not supported |
| **All tenants under a customer / account name** | ✅ Supported | ❌ Not supported by name |
| **LCAAS ID** | ✅ Supported when indexed | ✅ Supported |
| **Project / Tenant ID** | ✅ Supported when indexed | ✅ Supported |
| **Cortex / XDR ID** | Available if indexed | ✅ Supported |
| **Support Account ID / CSP ID** | Available if indexed | ✅ Supported |
| **Search across regions** | Searches accessible GitLab configuration | ✅ Searches accessible regional Grafana datasources |

### Which should I use?

| If you need to... | Use |
|---|---|
| Find a tenant using its customer name | **GitLab** |
| Search for a tenant using a serial number | **GitLab** |
| Find all tenants associated with one customer | **GitLab** |
| Find a tenant using its LCAAS ID | **Either tool** |
| Find a tenant using its Cortex/XDR ID | **Grafana** |
| Identify a tenant's configured settings | **GitLab** |
| Investigate why a tenant is experiencing problems | **Grafana** |

**Important notes:**

- GitLab searches the tenant configuration records accessible to your account. Search results depend on repository content and indexing.
- Grafana currently does **not** support searching by customer name or serial number.
- Customer names in Grafana metrics may appear as **Redacted**.
- Searching by Support Account ID in Grafana does not replace GitLab's customer-name-based tenant inventory.

---

## 2. What information is available in each tool?

### Configured vs. Running / Observed

| Information | GitLab — Configured State | Grafana — Running / Observed State |
|---|---|---|
| **Customer name** | ✅ Available when configured | ❌ Redacted or unavailable |
| **Customer/account mapping** | ✅ Tenant-to-account relationships | Limited account identifiers |
| **All tenants belonging to a customer** | ✅ Search by customer/account name | Not available by customer name |
| **Tenant identifiers** | ✅ Configured IDs and references | ✅ Observed LCAAS, Project and Cortex/XDR IDs |
| **Serial number** | ✅ When present in configuration | ❌ Not available |
| **Product / License** | ✅ Configured product and entitlement | ✅ Available telemetry-based licence details |
| **Enabled features / modules** | ✅ Intended configuration | Observed status where metrics exist |
| **Region** | ✅ Configured region | ✅ Actual matched Grafana region/datasource |
| **Deployment configuration** | ✅ Configured deployment details | Available operational/deployment signals |
| **Component versions** | Configured/intended versions | ✅ Observed backend, frontend and XSOAR versions |
| **Container image tags** | Configured image versions | ✅ Observed image tags |
| **CLCS ID / Subscription ID** | When present in configuration | ✅ Retrieved from CLCS telemetry where available |
| **Provisioning status** | Configured lifecycle information | ✅ Observed status where metrics exist |
| **Agents / Brokers** | Configuration references | ✅ Operational metrics and diagnostics |
| **Data ingestion** | Not a live health view | ✅ Ingestion diagnostics |
| **Performance** | Not a live health view | ✅ Performance and capacity evidence |
| **Detection / Alerts** | Configuration references where present | ✅ Operational diagnostic evidence |
| **Infrastructure / Engineering health** | Configuration references | ✅ Diagnostic checks and telemetry |
| **Grafana evidence links** | ❌ | ✅ Direct links to supporting queries |
| **Downloadable investigation report** | Configuration summary/export | ✅ Detailed HTML diagnostic report |

### Key difference

**GitLab — Desired / Configured State**

Shows how the customer and tenant are configured, including available identity, licensing, deployment, feature and image configuration records.

**Grafana — Actual / Observed State**

Shows what the monitoring system can observe, including tenant identity signals, operational metrics, component versions, CLCS information, diagnostic findings and supporting Grafana queries.

A configured value and an observed value may differ. Missing Grafana telemetry should not automatically be interpreted as a tenant failure.

---

## 3. Which tool should I start with?

| Scenario | Recommended workflow |
|---|---|
| I only know the customer's name | **GitLab** → Find the customer and tenant IDs |
| I only have a serial number | **GitLab** → Identify the associated tenant |
| A customer has multiple tenants | **GitLab** → List the tenants → **Grafana** to investigate the required tenant |
| I have an LCAAS ID | **Grafana** for live investigation; **GitLab** for configuration |
| I have a Cortex/XDR ID | **Grafana** → Find and investigate the matching tenant |
| I need licence or configuration information | **GitLab** for configured values; **Grafana** for observed licence metadata |
| A tenant is experiencing an issue | **Grafana** → Run Tenant Investigator |
| I need to verify the running component versions | **Grafana** |
| I need the intended deployment or configuration | **GitLab** |

---

## 4. Access requirements

| Tool | Access required | If you do not have access |
|---|---|---|
| **About Info Explorer — GitLab** | Internal GitLab access to the relevant tenant configuration repositories | **Contact a Cortex TAC SME** |
| **Tenant Investigator — Grafana** | Internal Grafana access and permission to query the relevant regional datasource | Contact your TAC SME or the appropriate internal access owner |

Both tools use your existing authenticated browser session. They do not provide additional permissions.

---

## 5. How to install or run

Both tools are available from a single installation page.

### [Open the Installer — index.html](index.html)

1. Download the repository or its `index.html` installation page and open it in **Google Chrome**.
2. Select **GitLab** or **Grafana**.
3. Choose your preferred installation method:

   | Method | Instructions |
   |---|---|
   | **Bookmark Install** | Drag the bookmark button from the installer to your Chrome bookmarks bar, then click it on the relevant authenticated page |
   | **Direct JS** | Copy or download the JavaScript, then execute it from Chrome DevTools on the relevant authenticated page |
   | **More Info** | Read the tool's features, limitations and additional instructions |

4. Follow the selected tool's on-screen instructions.

If your managed browser restricts bookmarklets, use an approved Direct JS method. Grafana's larger script may work more reliably through Direct JS.

---

## 6. Tool-specific guides

| Tool | Source | Documentation |
|---|---|---|
| **About Info Explorer — GitLab** | [JavaScript](about-info-explorer-gitlab/about-info-explorer.js) · [Bookmarklet](about-info-explorer-gitlab/about-info-explorer.bookmarklet.txt) | [GitLab User Guide](docs/ABOUT-INFO-EXPLORER.md) |
| **Tenant Investigator — Grafana** | [JavaScript](tenant-investigator-grafana/tenant-investigator.js) · [Bookmarklet](tenant-investigator-grafana/tenant-investigator.bookmarklet.txt) | [Grafana User Guide](docs/TENANT-INVESTIGATOR.md) |

### About Info Explorer — GitLab

Use the GitLab tool to search for customer accounts, find their configured tenants, review tenant/account mappings, and inspect available deployment and licence configuration.

**GitLab access is required. Engineers without access should contact a Cortex TAC SME.**

### Tenant Investigator — Grafana

Use the Grafana tool to find a tenant across accessible regions, collect its observed information, run 49 diagnostic checks, and review supporting Grafana evidence.

The tool provides an organized Overview and operational diagnostic sections, with **Copy Overview**, Grafana query links and downloadable HTML investigation reports.

---

## 7. Security, disclaimer and support

**Before using these tools, please review the following documents:**

| Document | What it covers |
|---|---|
| [Security & Access](docs/SECURITY-AND-ACCESS.md) | Authentication, permissions, internal data handling and safe usage |
| [Disclaimer](DISCLAIMER.md) | Tool limitations, interpretation of results and user responsibilities |
| [Support](SUPPORT.md) | How to obtain help or report issues |
| [Troubleshooting](docs/TROUBLESHOOTING.md) | Installation, browser, access and execution problems |

Both tools are intended for **internal Cortex TAC use only**. Do not share customer or internal diagnostic information externally without appropriate authorization.

---

*Cortex TAC Query Launcher is maintained separately for Marvel integration and is not part of this repository.*