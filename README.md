# Homelab Media Stack

This is a Docker Compose setup for running a self-hosted media automation suite on Ubuntu Server or Desktop.

## Services

- **Jellyfin** – Media server (port 8096)
- **Radarr** – Movie downloader & organizer (port 7878)
- **Jackett** – Torrent indexer proxy (port 9117)
- **qBittorrent** – Torrent client with Web UI (port 8080)

## Setup

1. Clone this repo
2. Configure `.env` file with your `PUID` and `PGID`
3. Run:

```bash
docker compose up -d
# JellyJackRad-Docker
