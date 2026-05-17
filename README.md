# SecureGraph

![Status](https://img.shields.io/badge/status-private%20demo-0f766e)
![Python](https://img.shields.io/badge/backend-FastAPI-009688)
![React](https://img.shields.io/badge/frontend-React-61dafb)
![Neo4j](https://img.shields.io/badge/graph-Neo4j-4581c3)
![License](https://img.shields.io/badge/license-proprietary-red)

SecureGraph is a proprietary vulnerability intelligence platform that turns dependency findings into graph-grounded attack paths and patch ROI.

Instead of saying "you have 847 CVEs," SecureGraph answers: "these vulnerabilities can reach your payment database, and these patches remove the most risk."

## Why It Exists

Security teams do not need another long list of CVEs. They need to know which vulnerabilities matter to their infrastructure, which ones can reach sensitive systems, and which fixes reduce the most risk.

SecureGraph connects:

- Vulnerabilities
- Packages
- Services
- Runtime infrastructure
- Business-critical data
- Exploit likelihood
- Remediation priority

## Product Preview

### Attack Surface Command Center

![SecureGraph dashboard](screenshots/dashboard.png)

### Global Attack Graph

![Global attack graph](screenshots/global-attack-graph.png)

### Repo-Specific Attack Graph

![Repo-specific attack graph](screenshots/repo-attack-graph.png)

### Graph-Grounded Patch ROI

![Patch ROI query](screenshots/patch-roi.png)

### Biggest Attack Path

![Biggest attack path query](screenshots/biggest-attack-path.png)

## High-Level Architecture

```mermaid
flowchart LR
    Repo["GitHub Repo / Manifest"] --> Scanner["Dependency Scanner"]
    Scanner --> CVE["CVE Matching"]
    CVE --> Graph["Neo4j Attack Graph"]
    Data["NVD / EPSS / OSV / GitHub Advisories"] --> Graph
    Graph --> Risk["Risk + Attack Path Engine"]
    Risk --> LLM["Graph-Grounded AI Analyst"]
    Graph --> UI["React Dashboard"]
    LLM --> UI
    Risk --> Report["Executive PDF Report"]
```

## Core Capabilities

- Repository dependency scanning
- CVE-to-package matching
- Attack path graph generation
- Exploit likelihood and risk scoring
- Patch ROI ranking
- Graph-grounded natural language Q&A
- Repo-specific attack graph visualization
- Executive report generation
- Private-by-design deployment

## What Makes SecureGraph Different

| Category | Traditional scanners | SecureGraph |
| --- | --- | --- |
| Output | CVE lists | Business attack paths |
| Prioritization | Severity-first | Exploitability + reachability + data impact |
| AI | Generic explanation | Graph-grounded answers |
| Remediation | Patch available | Patch ROI and blast-radius reduction |
| Visualization | Findings table | CVE -> package -> service -> data graph |

## Positioning

SecureGraph complements developer security tools by adding graph-based business context.

Snyk and similar tools identify vulnerable dependencies. SecureGraph explains which vulnerable dependencies can reach critical business data and which patches remove the most risk.

## Technology

| Layer | Stack |
| --- | --- |
| Backend | Python, FastAPI |
| Frontend | React, TypeScript, D3 |
| Knowledge Graph | Neo4j |
| Data Store | PostgreSQL |
| Cache / Queue | Redis |
| AI | Groq LLM with graph-grounded context |
| Vulnerability Data | NVD, EPSS, OSV, GitHub Advisories |
| Packaging | Docker Compose |

## Access

SecureGraph is proprietary software. The full source code, backend logic, AI prompts, graph schema implementation, data ingestion pipeline, and deployment configuration are private.

Private technical demo access is available by request for serious acquisition, investment, or partnership discussions.

## Contact

Built by Mohammed Saif, MS CS student at Seattle University.

Email: smohammed8@seattleu.edu

GitHub: [Mohammed-Saif-07](https://github.com/Mohammed-Saif-07)

## License

Copyright (c) 2026 Mohammed Saif. All rights reserved.

This repository is for public product preview only. No source code license is granted.
