# OSINT & CTI Threat Intelligence Engine

An automated cyber threat intelligence pipeline designed for OSINT ingestion, STIX 2.1 data normalization, and IoC query automation.

## Architecture
- `collectors/`: Modules for fetching raw data from AbuseIPDB, VirusTotal, and Shodan.
- `normalizer/`: Engine converting raw API JSON into STIX 2.1 Domain Objects.
- `api/`: FastAPI microservice exposing actionable threat endpoints.
- `detections/`: Sigma detection rules mapped to MITRE ATT&CK for Containers.

## Quickstart
bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
git add .
git commit -m "feat: initialize repository layout, python environment, and base docs"
uvicorn>=0.28.0
pytest>=8.0.0
