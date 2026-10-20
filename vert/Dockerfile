# syntax=docker/dockerfile:1

# Wrapper around the upstream Vert image (ghcr.io/vert-sh/vert). Upstream only
# publishes `latest`, `main` and `sha-*` tags — never a version — while the
# Home Assistant Supervisor pulls exactly `<image>:<addon version>`.
#
# This wrapper pins a digest (kept up to date by .github/workflows/
# update-upstream.yml) and is rebuilt/pushed by .github/workflows/
# docker-publish.yml as jonthekiller/vert-addon-{amd64,aarch64}:<version>.
#
# The base index is multi-arch (amd64/arm64): buildx resolves the matching
# platform layer for each build.

ARG VERT_DIGEST=sha256:bc87b98aa386b796b59c305083fe4897f2e50b4f76e29653f45141b7c128afe7
FROM ghcr.io/vert-sh/vert@${VERT_DIGEST}
