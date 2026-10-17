# JDownloader

[JDownloader 2](https://www.jdownloader.org/) in Home Assistant, using the [`jlesage/jdownloader-2`](https://github.com/jlesage/docker-jdownloader-2) Docker image (pulled directly from Docker Hub, multi-architecture).

The add-on is exposed through the Home Assistant **ingress** (sidebar panel "JDownloader") — no port needs to be open for the web UI.

## Configuration

| Option | Description |
|---|---|
| `MYJDOWNLOADER_EMAIL` | MyJDownloader account e-mail (optional: leave empty for local-only use) |
| `MYJDOWNLOADER_PASSWORD` | MyJDownloader account password |
| `MYJDOWNLOADER_DEVICE_NAME` | Device name shown in MyJDownloader (default: `HomeAssistant`) |
| `DARK_MODE` | `1` = dark web UI, `0` = light |

These options are passed to the container as environment variables (`legacy: true`), as expected by the jlesage image. `USER_ID`/`GROUP_ID` are baked to `0` so the container can write to the mapped folders.

## Folders

- `/share`, `/media`, `/config` are mapped read-write: put your download targets in `/media` or `/share` and configure the download folder from the JDownloader UI.

## Ports

- `3128/tcp`: JDownloader proxy port (exposed on the host).

## Icon

The icon is the official JDownloader logo (GPL, via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Jdownloader.png)).

## Versions

The add-on version is the exact Docker tag of the upstream image (e.g. `v26.09.1`); the Supervisor pulls `jlesage/jdownloader-2:<version>`. A GitHub Action in this repository bumps the version automatically when a new stable tag is published — "Update" then appears in the Home Assistant add-on store.
