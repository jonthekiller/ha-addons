# ha-addons — Home Assistant Add-on Repository

Home Assistant add-on repository. Add it **once** to Home Assistant and every
add-on in the catalog shows up in the Add-on Store.

## Available add-ons

| Add-on | Description | Version |
|---|---|---|
| [RSS-Tracker](./rss-tracker) | Lightweight Discord RSS bot (MonitoRSS alternative) — posts new articles to your Discord channels | [![Version](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2Fjonthekiller%2Fha-addons%2Fmain%2Frss-tracker%2Fconfig.json&query=%24.version&label=version)](./rss-tracker/config.json) |

## Installing in Home Assistant

1. **Settings → Add-ons → Add-on Store**
2. Bottom right: **⋮ → Repositories**
3. Add the URL:
   ```
   https://github.com/jonthekiller/ha-addons
   ```
4. The catalog add-ons appear in the store — install, then configure.

> Docker images are prebuilt and published to Docker Hub by GitHub Actions:
> nothing is compiled on your Home Assistant instance.
