# SQLReady — Changelog

All notable changes to this project will be documented in this file.

The format is based on [Semantic Versioning](https://semver.org/).

---

## [1.0.0] — 2026-09-26
### Added
- Initial public release of SQLReady.
- Core upgrade readiness engine (`SQLReady.sql`).
- PRE/POST baseline capture and delta comparison.
- Migration blocker detection module.
- Deprecated feature and compatibility-level checks.
- Performance impact module (CE changes, memory grants, regression indicators).
- BI stack compatibility module (SSIS, SSRS, SSAS).
- Configuration drift and unsupported settings module.
- Availability posture checks (AG/cluster).
- Security posture checks (authentication, encryption, configuration).
- SQLReady repository schema (`CreateRepository.sql`).
- Reporting views and helper stored procedures.
- Sample PRE/POST baseline scripts.
- Initial README.md with full product documentation.
- MIT License.

### Notes
This is the first stable release of SQLReady, intended for use in defence, finance, and government SQL Server estates.  
All modules run in **read‑only** mode and are safe for Citrix‑hosted SSMS environments.

---

## [Unreleased]
### Planned
- SQLReadyBI standalone module.
- SQLReadyPerfStore (Query Store analysis module).
- PBIRS paginated report templates.
- Grafana/Telegraf integration queries.
- Automated PRE/POST HTML report generator.
- Estate‑wide orchestration support.
