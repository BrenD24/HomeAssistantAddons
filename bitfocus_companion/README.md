# Bitfocus Companion Home Assistant Add-on

This add-on wraps the Docker image `brend24/companion:latest` and runs it as a Home Assistant add-on with:

- Host networking
- Persistent configuration
- Simple updates via Docker Hub

## Features

- Uses `brend24/companion:latest` from Docker Hub
- Host network mode (accesses the LAN directly)
- Companion config stored in `/config` inside the container, mapped to Home Assistant's `/config` directory

## Ports

- TCP 8000 – Companion Web UI
- TCP 16622 – Companion TCP control port

## Install

1. In Home Assistant, go to **Settings → Add-ons → Add-on Store**.
2. Click the **⋮** menu (top-right) → **Repositories**.
3. Add this repo URL:  
   `https://github.com/BrenD24/BitfocusCompanionHomeAssistant`
4. The repository `Bitfocus Companion Home Assistant Add-ons` should appear.
5. Install **Bitfocus Companion** add-on.
6. Start it, then click **OPEN WEB UI** or go to `http://<HA_IP>:8000`.

## Notes

- Updates: push a new `brend24/companion:latest` image to Docker Hub, then in Home Assistant:
  - Click **Rebuild** or
  - Bump `"version"` in `config.json` and update the repo – HA will show an update available.
