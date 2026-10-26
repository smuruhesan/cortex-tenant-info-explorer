# Cortex TAC — Tenant Investigator

**Host:** approved internal Grafana. **Included candidate:** `v1.0.0-rc.7` — not yet production-certified.

Find a tenant across eligible regional Prometheus datasources, then execute a tenant-bound, read-only diagnostic plan. The known run includes **49 diagnostic contracts / 67 Prometheus requests**, plus live identity and metadata collection. The report distinguishes genuine missing telemetry from healthy results and links the source PromQL/evaluation datasource.

- The provided rc.7 standalone launcher has SHA-256 `92c14bab34455e967f52340b5e57beaddec48a1d3ea60db75db8e83eb977df0a`.
- The provided rc.7 installer embeds the exact same launcher.
- The attached rc.7 Indonesia report shows fields such as Customer `Redacted`, support/account metadata and no CLCS series; an absent CLCS metric **is not proof there is no subscription**.
- Do not commit restricted reports or raw Grafana API responses into this repository.

[Installation portal](../index.html) · [User guide](USER-GUIDE.md) · [Release notes/status](../docs/RELEASE-STATUS.md)
