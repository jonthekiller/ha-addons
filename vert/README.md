# Vert — Home Assistant add-on wrapper

[Vert](https://vert.sh/) — next-generation file converter, fully local — packaged for Home Assistant from the official [`ghcr.io/vert-sh/vert`](https://github.com/vert-sh/vert) image.

## Why a wrapper?

The upstream image publishes **no version tags** (only `latest`, `main` and `sha-*` tags), while the Home Assistant Supervisor pulls exactly `<image>:<add-on version>`. This folder therefore contains a minimal Dockerfile that **pins the digest** of `ghcr.io/vert-sh/vert:latest` (`ARG VERT_DIGEST`). A workflow rebuilds the image `jonthekiller/vert-addon-{amd64,aarch64}` whenever the digest changes and publishes it under a clean version (the build date, e.g. `2026.10.16`).

## Access

Open the web UI via the "Open Web UI" button on the add-on page (`http://<host>:8083`).

## Configuration

- `PUB_DISABLE_ALL_EXTERNAL_REQUESTS: "1"` — no external requests (100% local conversion), set in `config.json`.

## Versions

Updates are automatic: the daily bot detects the new upstream digest, updates the Dockerfile + version, which triggers the CI build — "Update" then shows up in the Home Assistant add-on store.
