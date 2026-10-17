# ha-addons — Home Assistant Add-on Repository

Home Assistant add-on repository. Add it **once** to Home Assistant and every add-on in the catalog shows up in the Add-on Store.

## Available add-ons

| Add-on | Description | Version |
|---|---|---|
| [RSS-Tracker](./rss-tracker) | Lightweight Discord RSS bot (MonitoRSS alternative) — posts new articles to your Discord channels | [![Version](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2Fjonthekiller%2Fha-addons%2Fmain%2Frss-tracker%2Fconfig.json&query=%24.version&label=version)](./rss-tracker/config.json) |
| [JDownloader](./jdownloader) | JDownloader 2 with web UI and MyJDownloader integration (jlesage image) | [![Version](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2Fjonthekiller%2Fha-addons%2Fmain%2Fjdownloader%2Fconfig.json&query=%24.version&label=version)](./jdownloader/config.json) |
| [OmniTools](./omnitools) | Self-hosted collection of online tools (images, videos, text, …) | [![Version](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2Fjonthekiller%2Fha-addons%2Fmain%2Fomnitools%2Fconfig.json&query=%24.version&label=version)](./omnitools/config.json) |
| [Stirling PDF](./stirling_pdf) | Locally hosted web application for various PDF operations | [![Version](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2Fjonthekiller%2Fha-addons%2Fmain%2Fstirling_pdf%2Fconfig.json&query=%24.version&label=version)](./stirling_pdf/config.json) |
| [Vert](./vert) | Next-generation file converter, fully local | [![Version](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2Fjonthekiller%2Fha-addons%2Fmain%2Fvert%2Fconfig.json&query=%24.version&label=version)](./vert/config.json) |
| [Fast Note Sync Service](./fast_note_sync_service) | Self-hosted note synchronization service (Obsidian plugin backend) | [![Version](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2Fjonthekiller%2Fha-addons%2Fmain%2Ffast_note_sync_service%2Fconfig.json&query=%24.version&label=version)](./fast_note_sync_service/config.json) |

## Installing in Home Assistant

1. **Settings → Add-ons → Add-on Store**
2. Bottom right: **⋮ → Repositories**
3. Add the URL: `https://github.com/jonthekiller/ha-addons`
4. The catalog add-ons appear in the store — install, then configure.

> Docker images are prebuilt and published to Docker Hub by GitHub Actions: nothing is compiled on your Home Assistant instance. Most add-ons pull the official upstream image directly (the add-on version is the upstream Docker tag); only Vert is a thin wrapper pinning the upstream digest, rebuilt by CI.

## Automatic updates

- **`update-upstream.yml`** runs daily: for each add-on declared in [`.github/addons-update.json`](./.github/addons-update.json) it resolves the newest upstream version (Docker Hub tag, GitHub release or GHCR digest for Vert) and commits the bump when it changes. "Update" then appears in the Home Assistant add-on store.
- **`docker-publish.yml`** rebuilds and pushes the Vert wrapper image (`jonthekiller/vert-addon-{amd64,aarch64}`) whenever its pinned digest or version changes.
- **`sync-addon.yml`** syncs self-developed add-ons (e.g. rss-tracker) from their source repository on release.
- **`validate.yml`** validates every add-on (`config.json` required keys, version format, icons) on every push and PR.

## Secrets

| Secret | Used by |
|---|---|
| `DOCKERHUB_USERNAME` / `DOCKERHUB_TOKEN` | `docker-publish.yml` (Vert image push) |
| `ADDONS_REPO_PAT` (optional) | `sync-addon.yml` / `update-upstream.yml` (private source repos) |
