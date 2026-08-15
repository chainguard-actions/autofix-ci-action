<!-- markdownlint-disable -->

# Hardening Report: autofix-ci--action/v1.3.3

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **autofix-ci--action/v1.3.3** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

Two `uses:` references in `.github/workflows/autofix.yml` are pinned to mutable version tags rather than immutable 40-character commit SHAs. This exposes the workflow to supply-chain attacks if the upstream action tag is moved or the repository is compromised.

Failing references:
- `uses: actions/checkout@v4` (line 13) — should be pinned to a full SHA, e.g. `actions/checkout@11bd71901bbe5b1630ceea73d27597364c9af683 # v4`
- `uses: actions/setup-node@v4` (line 15) — should be pinned to a full SHA, e.g. `actions/setup-node@39370e3970a6d050c480ffad4ff0ed4d3fdee5af # v4`

The third reference (`autofix-ci/action@d3e591514b99d0fca6779455ff8338516663f7cc`) is correctly pinned to a full SHA.

Locations:

- `.github/workflows/autofix.yml:13`
- `.github/workflows/autofix.yml:15`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned two mutable tag references in .github/workflows/autofix.yml:
- actions/checkout@v4 → actions/checkout@34e114876b0b11c390a56381ad16ebd13914f8d5 # v4
- actions/setup-node@v4 → actions/setup-node@49933ea5288caeca8642d1e84afbd3f7d6820020 # v4
The third reference (autofix-ci/action@d3e591514b99d0fca6779455ff8338516663f7cc) was already pinned to a full SHA and required no changes.

