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

- TLP markings are preserved end-to-end — nothing gets re-shared past its handling label
- Feed health is monitored; a stale or dead feed alerts instead of silently going quiet
- Every indicator keeps its source lineage so analysts can judge reliability, not just trust a score

## Status

- Actively maintained — next up is automated feed-quality scoring.

---

*Part of the [devsecforge](https://github.com/devsecforge/devsecforge) open security program — framework-mapped, hands-on, and actively growing.*
