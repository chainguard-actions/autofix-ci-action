<!-- markdownlint-disable -->

# Hardening Report: autofix-ci--action/v1.3.2

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **autofix-ci--action/v1.3.2** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The workflow file uses tag-based (mutable) references instead of pinned SHA commits for two actions: `actions/checkout@v4` (line 14) and `actions/setup-node@v4` (line 16). Tags can be moved by the upstream repository owner, enabling supply-chain attacks. These should be pinned to their full 40-character commit SHAs (e.g., `actions/checkout@11bd71901bbe5b1630ceea73d27597364c9af683 # v4`). Note: `autofix-ci/action@d3e591514b99d0fca6779455ff8338516663f7cc` is correctly pinned to a SHA.

Locations:

- `.github/workflows/autofix.yml:14`
- `.github/workflows/autofix.yml:16`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned two mutable tag references in hardened/action/.github/workflows/autofix.yml: `actions/checkout@v4` → `actions/checkout@11d5960a326750d5838078e36cf38b85af677262 # v4` and `actions/setup-node@v4` → `actions/setup-node@49933ea5288caeca8642d1e84afbd3f7d6820020 # v4`. The already-pinned `autofix-ci/action@d3e591514b99d0fca6779455ff8338516663f7cc` was left unchanged.

