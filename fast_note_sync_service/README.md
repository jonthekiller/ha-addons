# Fast Note Sync Service

[Fast Note Sync](https://github.com/haierkeys/fast-note-sync-service) — self-hosted note synchronization service (Obsidian plugin backend), using the official [`haierkeys/fast-note-sync-service`](https://github.com/haierkeys/fast-note-sync-service) Docker image (pulled directly from Docker Hub).

## Ports

- `9000/tcp`: Fast Note Sync API / web
- `9001/tcp`: secondary port

## Folders

- `/fast-note-sync/config` — service configuration (persisted in the add-on configuration folder).
- `/fast-note-sync/storage` — note storage (persisted in the add-on data folder).

## Versions

The add-on version is the exact Docker tag of the upstream image; the Supervisor pulls `haierkeys/fast-note-sync-service:<version>`. A GitHub Action in this repository bumps the version automatically when a new release is published — "Update" then appears in the Home Assistant add-on store.
