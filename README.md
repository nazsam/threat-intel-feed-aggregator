# 🛰️ Threat Intel Feed Aggregator

*By S. Naz · Cybersecurity, Cloud & AI Security Leader*

A pipeline that pulls threat intel feeds into one normalized, deduplicated IOC store SOC teams can actually query.

![STIX/TAXII](https://img.shields.io/badge/STIX/TAXII-005571?style=flat-square) ![Python](https://img.shields.io/badge/Python-3776AB&logo=python&logoColor=white?style=flat-square) ![MISP](https://img.shields.io/badge/MISP-1F4E79?style=flat-square) ![Threat Intel](https://img.shields.io/badge/Threat_Intel-D22730?style=flat-square)

## What's Inside

- Ingestion connectors for STIX/TAXII 2.1 feeds, MISP instances, and open OSINT IOC lists
- Normalization layer that maps every indicator to a common schema (type, confidence, TLP, first/last seen)
- Deduplication and confidence scoring before indicators hit the SOC-facing store
- Export jobs that push curated IOC sets into SIEM watchlists on a schedule

## Key Practices

- TLP markings are preserved end-to-end, so nothing gets re-shared past its handling label
- Feed health is monitored; a stale or dead feed alerts instead of silently going quiet
- Every indicator keeps its source lineage so analysts can judge reliability, not just trust a score

## Status

- Actively maintained. Next up is automated feed-quality scoring.

## ☁️ Delivering intel to Microsoft Sentinel

- **Watchlists:** curated IOC sets exported as Sentinel watchlist CSV. The `secops ioc` command in
  **[azure-secops-toolkit](https://github.com/nazsam/azure-secops-toolkit)** extracts, refangs and deduplicates indicators from a report into that format.
- **Threat intelligence tables:** STIX 2.1 indicators delivered through the Sentinel TAXII or upload API
  connectors, so they land in the workspace's threat intelligence tables.
- **Matching:** the toolkit's [threat intelligence IP hunt](https://github.com/nazsam/azure-secops-toolkit/blob/main/hunting/threat-intel-ip-match.kql) joins
  active indicators against sign-in and network telemetry; the
  [IP enrichment playbook](https://github.com/nazsam/azure-secops-toolkit/tree/main/playbooks) adds reputation to every new incident.

---

*Maintained by **Sam Naz**, Cybersecurity and AI Architect · [LinkedIn](https://www.linkedin.com/in/samicybersecurity) · Azure implementation: [azure-secops-toolkit](https://github.com/nazsam/azure-secops-toolkit)*
