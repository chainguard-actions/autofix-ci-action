<!-- markdownlint-disable -->

# Hardening Report: autofix-ci--action/v1.3.4

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **autofix-ci--action/v1.3.4** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

Two `uses:` references in .github/workflows/autofix.yml are pinned to mutable version tags instead of full 40-character commit SHAs, making the workflow vulnerable to supply-chain attacks if those tags are moved:
- `actions/checkout@v4` (line 14) — should be pinned to a full SHA
- `actions/setup-node@v4` (line 16) — should be pinned to a full SHA

The third reference (`autofix-ci/action@d3e591514b99d0fca6779455ff8338516663f7cc`) is correctly pinned.

Locations:

- `.github/workflows/autofix.yml:14`
- `.github/workflows/autofix.yml:16`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned both mutable tag references in .github/workflows/autofix.yml:
- `actions/checkout@v4` → `actions/checkout@11d5960a326750d5838078e36cf38b85af677262 # v4`
- `actions/setup-node@v4` → `actions/setup-node@49933ea5288caeca8642d1e84afbd3f7d6820020 # v4`

The third reference (`autofix-ci/action@d3e591514b99d0fca6779455ff8338516663f7cc`) was already correctly pinned and left unchanged.

