<!-- markdownlint-disable -->

# Hardening Report: rajatjindal--krew-release-bot/v0.0.51

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **rajatjindal--krew-release-bot/v0.0.51** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The action.yml uses a Docker image reference with a mutable tag instead of a SHA digest. The image `docker://ghcr.io/rajatjindal/krew-release-bot:v0.0.50` uses the tag `v0.0.50`, which can be silently replaced by a different (potentially malicious) image without any change to the action definition. It should be pinned to an immutable SHA digest, e.g. `docker://ghcr.io/rajatjindal/krew-release-bot@sha256:<64-hex-char-digest>`.

Locations:

- `action.yml:6`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned the Docker image reference in action.yml from `docker://ghcr.io/rajatjindal/krew-release-bot:v0.0.50` to `docker://ghcr.io/rajatjindal/krew-release-bot:v0.0.50@sha256:6932be48286bacb7a7e45d375ded48a97e7edc36959cd693473b8d08730d62ba`. The docker:// scheme and tag are preserved inline with the digest appended for immutability.

