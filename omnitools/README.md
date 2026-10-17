# OmniTools

[OmniTools](https://omnitools.app/) — self-hosted collection of online tools (images, videos, text, …), using the official [`iib0011/omni-tools`](https://github.com/iib0011/omni-tools) Docker image (pulled directly from Docker Hub, multi-architecture).

## Access

Open the web UI via the "Open Web UI" button in the add-on page (`http://<host>:8082`).

## Configuration

No options: the image runs as-is with sensible defaults.

## Versions

The add-on version is the exact Docker tag of the upstream image; the Supervisor pulls `iib0011/omni-tools:<version>`. A GitHub Action in this repository bumps the version automatically when a new release is published — "Update" then appears in the Home Assistant add-on store.
