# Cortex TAC — About Info Explorer

**Host:** internal GitLab. **Current script:** `v23-Fixes` (taken without modification from the supplied bookmarklet).

Purpose: find the customer and read the **desired-state** tenant configuration from the existing GitLab `tenants-config-prod` repository and, when resolvable, frontend-version mapping.

Provides customer and Support Account identifiers; project/LCAAS/Cortex ID; serial and tenant URL; product and licence configuration; MSSP/METRO relationship; cloud region, quota, feature flags, image build tags; version mappings; and dashboard links.

If you do not have access to the GitLab repository, **contact a Cortex TAC SME**. The bookmarklet does not grant permissions.

[Installation portal](../index.html) · [User guide](USER-GUIDE.md) · [Security notes](../docs/SECURITY-AND-ACCESS.md)

**Security:** Original script attempts a public-CDN load of js-yaml and interpolates configuration values into HTML. Treat as an internal review item before broad release.
