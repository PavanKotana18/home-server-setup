Home Server Setup Plan

This document describes the actual plan for building my home server using an old HP laptop.

The goal is to run a few useful self-hosted services while learning Linux, Docker, and networking.

---

Hardware

Laptop: HP old laptop

RAM: 12 GB
Storage:

- 256 GB SSD
- 1 TB HDD

Planned Storage Usage

SSD (256 GB)

- Linux operating system
- Docker
- Application containers

HDD (1 TB)

- Nextcloud data
- Media files
- Documents
- Backups

---

Operating System

Planned OS: Ubuntu Server (LTS)

Reasons:

- Stable and widely supported
- Good Docker support
- Large community and documentation
- Lightweight compared to desktop OS

---

Core Services

The following services will run on the server:

Pi-hole

Network-wide DNS ad blocker.

Purpose:

- Block ads across all devices in the home network
- Reduce tracking domains

---

Unbound

Local recursive DNS resolver.

Purpose:

- Provide private DNS resolution
- Avoid using third-party DNS providers

---

Nextcloud

Self-hosted cloud storage.

Purpose:

- Store personal files
- Backup phone photos
- Synchronize files between devices

---

Tailscale

VPN for remote access.

Purpose:

- Access the home server securely from outside the network
- Avoid exposing services directly to the internet

---

Jellyfin

Media server.

Purpose:

- Stream movies and shows from the home server
- Access media across devices

---

Vaultwarden

Self-hosted password manager.

Purpose:

- Store passwords securely
- Sync passwords across devices

---

Uptime Kuma

Service monitoring tool.

Purpose:

- Monitor server services
- Detect if any service goes offline

---

Container Management

Applications will run inside Docker containers.

Benefits:

- Easy installation
- Isolated services
- Simple updates
- Clean removal of applications

---

Planned Installation Steps

1. Install Ubuntu Server on the SSD
2. Update the system
3. Install Docker
4. Install Docker Compose
5. Mount HDD storage directory
6. Deploy containers using docker-compose

Planned container order:

1. Pi-hole
2. Unbound
3. Nextcloud
4. Tailscale
5. Jellyfin
6. Vaultwarden
7. Uptime Kuma

---

Storage Layout

HDD directory structure:

/storage
 ├── nextcloud
 ├── media
 │    ├── movies
 │    └── series
 ├── documents
 └── backups

---

Backup Plan

Primary storage: Server HDD

Backup strategy:

- Local backup folder on HDD
- Optional external HDD backup
- Automated backups using scheduled tasks

---

Security Plan

Basic security measures:

- Use strong passwords
- Enable two-factor authentication where possible
- Keep system updated regularly
- Do not expose services directly to the internet
- Use Tailscale VPN for remote access

---

Current Status

Planning stage.

Server setup will be implemented in the future using the above architecture.
