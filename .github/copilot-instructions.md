# Copilot instructions

## Commands

The README's environment setup is:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

`requirements.txt` is currently empty; the README separately lists `pytest>=8.0.0`. Install pytest with `pip install "pytest>=8.0.0"` before running tests.

Run pytest from the repository root with:

```bash
python -m pytest
```

To run one test, use pytest's node selector:

```bash
python -m pytest tests/test_module.py::test_name
```

The repository does not yet contain test modules or configured build/lint commands.

## Architecture

The project is intended to take threat intelligence from OSINT sources through collection, normalization, and query:

- `collectors/` fetches raw data from AbuseIPDB, VirusTotal, and Shodan.
- `normalizer/` converts provider JSON into STIX 2.1 objects.
- `api/` is the FastAPI service intended to expose threat intelligence endpoints.
- `detections/` is intended for Sigma rules mapped to MITRE ATT&CK for Containers.

These boundaries come from the README. The current Python packages contain only their initializers, so treat this as the target architecture rather than assuming the pipeline is implemented.

## Repository-specific conventions

- Python packages live directly at the repository root; run project and pytest commands from that root.
- Provider credentials are named `ABUSEIPDB_API_KEY`, `VIRUSTOTAL_API_KEY`, and `SHODAN_API_KEY`, as shown in `.env.example`.
- Keep credentials in the ignored local `.env`; use `.env.example` for placeholder names and never put real keys in tracked files.
- Keep provider-specific ingestion in `collectors/`, provider-independent STIX conversion in `normalizer/`, and HTTP exposure in `api/`, consistent with the documented pipeline.
