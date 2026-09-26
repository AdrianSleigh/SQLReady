# SQLReady
SQLReady
SQL Server upgrade readiness engine with diagnostics, migration blockers, BI checks, perf‑impact analysis, and PRE/POST baselines.

SQLReady is a read‑only, SC‑cleared‑friendly upgrade readiness framework designed for SQL Server estates in defence, finance, and government environments. It performs deep diagnostics, identifies migration blockers, evaluates BI stack compatibility, highlights performance‑impact risks, and produces structured PRE/POST baseline reports suitable for CAB and cyber review.

SQLReady is built for clarity, auditability, and repeatability — providing a single, consistent workflow for assessing SQL Server upgrade readiness across large estates.

⭐ Key Features
Upgrade Readiness
Detects migration blockers

Identifies deprecated features

Highlights version‑specific risks

Evaluates compatibility level issues

Performance Impact Analysis
Cardinality Estimator changes

Memory grant risk signals

Plan regression indicators

Query Store state and readiness

BI Stack Compatibility
SSIS package format checks

SSRS catalog version checks

SSAS model compatibility

Configuration & Availability
Config drift detection

Unsupported settings

Availability posture checks

Security posture indicators

PRE/POST Baseline Engine
Capture PRE‑upgrade baseline

Capture POST‑upgrade baseline

Automatic delta comparison

CAB‑ready evidence output

Enterprise‑Friendly
Read‑only execution

No engine hooks

No intrusive actions

Works in Citrix environments

Suitable for SC‑cleared estates

📦 Repository Structure
Code
/SQLReady
    SQLReady.sql                -- Main engine
    SQLReadyBI.sql              -- BI module (optional)
    README.md                   -- This file
    CHANGELOG.md                -- Version history
    VERSION.txt                 -- Current version

/modules
    migration/                  -- Migration blockers & DMA-style rules
    diagnostics/                -- Core diagnostic modules
    performance/                -- Perf-impact checks
    config/                     -- Config drift & unsupported settings
    availability/               -- HA/DR posture checks
    security/                   -- Security posture checks
    bi/                         -- SSIS/SSRS/SSAS compatibility

/repository
    CreateRepository.sql        -- SQLReady repository schema
    Views.sql                   -- Reporting views
    StoredProcedures.sql        -- Helper procedures

/reports
    HTMLTemplates/              -- Optional HTML report templates
    GrafanaQueries/             -- Telegraf/Grafana integration queries
    PBIRS-RDL/                  -- PBIRS paginated report templates

/samples
    PREBaseline.sql             -- Example PRE baseline
    POSTBaseline.sql            -- Example POST baseline
    ExampleOutput/              -- Sample reports
🚀 Getting Started
1. Deploy the SQLReady repository
Run:

Code
/repository/CreateRepository.sql
This creates the tables used for findings, facts, baselines, and reporting.

2. Run SQLReady
Execute:

Code
SQLReady.sql
This performs:

diagnostics

migration checks

BI checks

perf-impact analysis

config drift detection

availability & security posture checks

Findings are written to the SQLReady repository.

3. Capture PRE baseline
Before upgrading:

Code
EXEC SQLReady_CaptureBaseline 'PRE';
4. Perform upgrade
Use your standard upgrade workflow (SSMS migration tool, setup.exe, automation, etc.).

5. Capture POST baseline
After upgrading:

Code
EXEC SQLReady_CaptureBaseline 'POST';
6. Generate delta report
SQLReady automatically compares PRE vs POST and writes deltas to the repository.

📊 Optional Integrations
Grafana + Telegraf
SQLReady outputs can be visualised using Telegraf custom SQL queries and Grafana dashboards.

PBIRS (Power BI Report Server)
Paginated RDL reports can be built using the /reports/PBIRS-RDL templates.

🔒 Security & Safety
SQLReady is designed for secure environments:

Read‑only execution

No writes to system objects

No configuration changes

No plan forcing

No engine hooks

Safe for Citrix‑hosted SSMS sessions

📄 License
This project is licensed under the MIT License.

👤 Author
Adrian Sleigh  
SQL Server Consultant — Defence, Finance & Government
Creator of SQLReady
