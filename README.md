#OSINT-CTI-lab

A personal learning lab for open-source intelligence (OSINT) and cyber threat
intelligence (CTI): collection, analysis, and reporting from public sources only.

> **Status:** early development / learning project. Not production software.

## Purpose

I'm building this to develop practical OSINT and CTI skills by producing both
**code** (collectors, enrichment, STIX normalisation) and **analytic products**
(reports, actor profiles, structured analyses). Every component should trace back
to a question in [`tradecraft/pirs.md`](tradecraft/pirs.md).

## Goals (12 months)

| Goal | Measure |
|---|---|
| Build a working pipeline: ingest, normalise to STIX 2.1, enrich, report | End-to-end run documented in `docs/` |
| Produce written analytic products | 10+ reports, profiles, or ACH analyses |
| Practise OSINT pivoting on public cases | 5+ documented case write-ups |
| Measure indicator shelf life | 3+ months of IOC backtest data |
| Deploy on Kubernetes | Manifests + CI in `k8s/` |

## Scope

**In scope**
- Public, legally accessible sources (feeds, advisories, vendor research, CT logs, passive DNS, public registries)
- Infrastructure and organisation-level analysis
- Threat actor and campaign analysis from published reporting
- Public exercises and CTFs (e.g. Trace Labs)

**Out of scope**
- Private individuals, doxxing, or personal-data aggregation
- Breach or leaked data, paywall or authentication bypass
- Active scanning or exploitation of systems I don't own
- Anything involving my employer's data, systems, or tooling

See [`ETHICS.md`](ETHICS.md) for the rules I follow.

## Repository layout

```
tradecraft/    PIRs, collection plan, source-grading approach
analysis/      ACH analyses, timelines, assessments
profiles/      Threat actor profiles + ATT&CK Navigator layers
reports/       Finished BLUF-format reports
osint-notes/   Case studies and pivot write-ups
pipeline/      ingest/, normalise/, enrich/, tests/
detections/    Sigma and YARA rules derived from public intel
docs/          Architecture, decisions (ADRs), lessons
```

## Methodology

- Sources are graded with the Admiralty system (reliability A-F, credibility 1-6)
- Judgments use stated confidence (low / moderate / high) and list assumptions
- Findings are mapped to MITRE ATT&CK where relevant
- Structured analytic techniques (e.g. ACH) are used on contested questions

## Current status

Status | [not started / in progress / done]

| Component | Status |
|---|---|
| PIRs and collection plan | [not started] |
| CISA KEV + URLhaus collectors | [not started] |
| STIX 2.1 normalisation | [not started] |
| Enrichment | [not started] |
| Kubernetes deployment | [not started] |

## Limitations

- Single-author learning project; data quality and coverage are limited
- Free-tier API rate limits restrict collection volume
- Scoring and confidence methods are my own simplifications, not validated models
- Outputs are not intelligence advice and should not be used for operational decisions

## Lessons and decisions

See [`docs/LESSONS.md`](docs/LESSONS.md) and [`docs/adr/`](docs/adr/).

## Licence

[MIT / Apache-2.0]. See `LICENSE`.

## Contact
Gotaki