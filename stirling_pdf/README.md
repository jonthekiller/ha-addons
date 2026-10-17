# Stirling PDF

[Stirling PDF](https://www.stirlingpdf.com/) — locally hosted web application for various PDF operations, using the official [`stirlingtools/stirling-pdf`](https://github.com/Stirling-Tools/Stirling-PDF) Docker image (pulled directly from Docker Hub, multi-architecture amd64/arm64).

## Access

Open the web UI via the "Open Web UI" button in the add-on page (`http://<host>:8080`).

## Configuration

No add-on options: Stirling PDF 3.x is configured from its own web UI (account management, security, settings) and its `settings.yml`.

The container's `/configs` directory is persisted in the add-on configuration folder, so your settings, database and custom files survive restarts and updates.

## Notes

- The upstream image manages its own user switch (`PUID`/`PGID`, set to `0` here so it can write the config folder managed by Home Assistant).
- Only `amd64` and `arm64` architectures are published upstream, hence the add-on architectures.

## Versions

The add-on version is the exact Docker tag of the upstream image; the Supervisor pulls `stirlingtools/stirling-pdf:<version>`. A GitHub Action in this repository bumps the version automatically when a new release is published — "Update" then appears in the Home Assistant add-on store.
