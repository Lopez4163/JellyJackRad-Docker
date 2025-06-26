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


# 📦 Basic Stack Lifecycle

# Start all services in the background
docker compose up -d

# Stop all services (containers only)
docker compose down

# Stop and remove all containers + volumes (⚠️ permanent data loss!)
docker compose down -v

# Restart all services
docker compose restart

# Rebuild containers without using cache (force fresh build)
docker compose build --no-cache
docker compose up -d

# Build containers without starting them
docker compose build

# Show logs for all services (live)
docker compose logs -f

# Show logs for a specific service
docker compose logs -f jellyfin
docker compose logs -f radarr
docker compose logs -f jackett
docker compose logs -f qbittorrent

# 🔧 Single Container Management

# Stop a single container
docker stop jellyfin

# Remove a single container
docker rm jellyfin

# Restart a single container
docker restart radarr

# Open a terminal session inside a running container
docker exec -it jellyfin bash

# Inspect container details (ports, mounts, etc.)
docker inspect jackett

# 🧼 Cleanup & System Maintenance

# View all running containers
docker ps

# View all containers (running or not)
docker ps -a

# Remove all stopped containers
docker container prune

# Remove all unused Docker data (⚠️ careful)
docker system prune -af

# Remove unused volumes only
docker volume prune

# 🔐 Permissions Fix (on host machine)
sudo chown -R $USER:$USER ~/media-stack ~/JellyfinMedia

# 🧠 .env Support

# Show your UID and GID for use in .env
id -u   # PUID
id -g   # PGID
