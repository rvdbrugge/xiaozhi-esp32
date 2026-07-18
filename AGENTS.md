# AGENTS.md

## Purpose
- This repository contains XiaoZhi ESP32 firmware and tooling.
- Keep changes minimal, scoped, and aligned with existing code style (Google C++).

## Project Layout
- `main/`: firmware source code and board definitions.
- `docs/`: developer and protocol documentation.
- `scripts/`: release/build helper scripts and Python tests.
- `.github/workflows/build.yml`: CI build and test workflow.

## Development Prerequisites
- ESP-IDF v6.0.x is the preferred SDK (v6.0.2 recommended).
- ESP-IDF v5.5.x is retained only for legacy compatibility paths.
- Build tooling expects `idf.py` to be available in the environment (`source $IDF_PATH/export.sh`).

## Validation Commands
- Run release-tool tests:
  - `python -m unittest discover -s scripts/tests -v`
- Build a specific board variant (requires ESP-IDF environment):
  - `python scripts/release.py <board> --name <variant>`
- Optional direct IDF build path is defined in CI (`.github/workflows/build.yml`).

## Change Guidelines
- Prefer surgical changes over broad refactors.
- Do not modify unrelated boards or assets.
- Update documentation when behavior, configuration, or workflows change.
- Preserve CI expectations in `scripts/release.py` and board config naming/uniqueness rules.

## Security and Safety
- Never commit credentials, tokens, or private keys.
- Validate new or changed logic for input handling and network-facing safety.
- Keep dependencies aligned with existing project tooling and ESP-IDF compatibility requirements.
