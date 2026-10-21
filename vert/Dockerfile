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

ARG VERT_DIGEST=sha256:51edb89e7c57197b0281ba8427fb27eea63730a3683b10d422061afab2708a49
FROM ghcr.io/vert-sh/vert@${VERT_DIGEST}
