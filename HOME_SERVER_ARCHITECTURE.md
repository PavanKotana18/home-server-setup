Home Server Architecture

This document describes the planned architecture of my home server setup.

The goal is to run multiple self-hosted services on a single machine using Docker containers.

---

Network Architecture

The server will be connected to the home router and will provide services to devices inside the network.

Internet
   ↓
Router
   ↓
Home Network
   ├── Phone
   ├── Laptop
   ├── Smart TV
   └── Home Server

The home server will run multiple services for the network.

---

Server Architecture

The laptop server will run Linux as the base operating system.

Applications will run inside Docker containers.

HP Laptop Server
   ↓
Ubuntu Server (Linux)
   ↓
Docker
   ↓
Containers
   ├── Pi-hole
   ├── Unbound
   ├── Nextcloud
   ├── Jellyfin
   ├── Vaultwarden
   ├── Tailscale
   └── Uptime Kuma

Each service runs inside its own container, making the system easier to manage.

---

DNS Flow

DNS queries from devices will pass through Pi-hole and Unbound.

Device
   ↓
Pi-hole
   ↓
Unbound
   ↓
Global DNS Servers

This setup provides ad blocking and private DNS resolution.

---

Remote Access

Remote access will be handled through Tailscale VPN.

Phone outside home
   ↓
Encrypted VPN connection
   ↓
Home server

This allows secure access to server services without exposing them directly to the internet.

---

Storage Layout

The laptop has two storage drives.

SSD (256 GB)

Used for:

- Operating system
- Docker
- Containers

HDD (1 TB)

Used for:

- Nextcloud data
- Media files
- Documents
- Backups

Example structure:

/storage
 ├── nextcloud
 ├── media
 ├── documents
 └── backups

---

Monitoring

Server health will be monitored using Uptime Kuma.

This will track the status of all running services and notify if any service stops working.

---

Summary

This architecture allows multiple services to run on a single home server using containerization while keeping the system organized and manageable.
