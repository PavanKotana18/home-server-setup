🏠 My Home Server Setup

This repository contains my personal notes on building a small home server using an old laptop.

The goal of this project is simple:
Instead of depending on many external services, I want to run some useful services at home and learn how self-hosting works.

This is not a production project or a professional setup.
It is mainly a personal experiment and a learning project.

---

Idea Behind This Project

Most of the time we depend on external platforms such as:

- Google Drive for storing files
- Browser extensions for ad blocking
- Cloud services for data storage

Instead of relying completely on these services, it is possible to run similar services at home.

This concept is called self-hosting.

In self-hosting, a small computer inside the home network runs different services such as:

- ad blocking
- private cloud storage
- file storage
- media streaming
- remote access

That computer becomes the home server.

---

Hardware Used

The server in this project is simply an old HP laptop.

Laptop Specifications

- RAM: 12 GB
- Storage:
  - 256 GB SSD
  - 1 TB HDD

Old laptops are actually very useful for home servers because they already include:

- built-in battery (acts like a small UPS)
- WiFi and Ethernet
- low power consumption
- enough processing power for lightweight services

The laptop will remain connected to the router and run continuously.

Estimated power consumption:

15W – 40W

Monthly electricity cost is roughly around:

₹40 – ₹120

---

Network Structure

In a typical home network, the router connects all devices.

Example devices:

- phones
- laptops
- smart TVs

The home server is also connected to the same router.

Simple structure:

Internet
↓
Router
↓
Home Devices
↓
Home Server

The server provides services to all devices inside the network.

---

Core Services

The home server can run multiple services.
Some of the main ones planned for this setup are:

- Pi-hole – network-wide ad blocking
- Unbound – private DNS resolver
- Nextcloud – personal cloud storage
- Tailscale / WireGuard – VPN access

Each of these services has a specific role.

---

Pi-hole

Pi-hole blocks ads for the entire home network.

When a device requests a website, it first performs a DNS lookup.

Pi-hole intercepts these DNS requests and blocks domains that belong to advertising or tracking services.

Example:

Device → request for ads server
Pi-hole → block

Device → request for normal website
Pi-hole → allow

Because of this, ads are blocked across all devices in the network.

---

Unbound

Normally DNS queries are sent to public providers like:

- Google DNS
- Cloudflare DNS
- ISP DNS

Unbound allows the server to resolve DNS queries directly using the global DNS system.

Request flow becomes:

Device
↓
Pi-hole
↓
Unbound
↓
Internet DNS servers

This improves privacy and reduces dependency on third-party DNS services.

---

Nextcloud

Nextcloud works like a private version of Google Drive.

Instead of storing files on external cloud servers, the files are stored on the home server.

Possible uses:

- storing documents
- automatic phone photo backup
- file synchronization between devices
- sharing files inside the home network

This keeps personal data under full control.

---

VPN Access

When outside the house, devices normally cannot reach the home server.

A VPN creates a secure tunnel between devices.

Tools such as:

- Tailscale
- WireGuard

allow secure remote access.

Example connection:

Phone outside home
↓
Encrypted VPN tunnel
↓
Home server

This allows access to files and services even when away from home.

---

Docker

Instead of installing applications directly on the system, Docker will be used to run services inside containers.

Each container runs one application.

Example container setup:

- Pi-hole
- Nextcloud
- Jellyfin
- Vaultwarden
- WireGuard
- Uptime Kuma

Containers help keep services isolated and easier to manage.

---

Storage Layout

The laptop has two storage drives:

256 GB SSD
1 TB HDD

The idea is to use them for different purposes.

SSD

Used for:

- Linux operating system
- Docker
- application containers

HDD

Used for storing data:

- Nextcloud files
- photos
- media
- documents
- backups

Example structure:

storage

- nextcloud-data
- media
- documents
- backups

---

Monitoring

To monitor whether services are running properly, tools like Uptime Kuma can be used.

This allows the server to display the status of different services in a dashboard.

Example:

Nextcloud – online
Pi-hole – online
Jellyfin – online

If a service stops working, notifications can be triggered.

---

Backup Strategy

Important data should never exist in only one location.

This setup follows a simple backup approach.

Main storage:

server HDD

Backup storage:

external drive or backup folder

Backups can be automated using scheduled tasks.

---

Why I Built This

This project is mainly about:

- learning how self-hosting works
- understanding networking and DNS
- running personal services at home
- keeping control over personal data

It is also a good way to experiment with Linux, Docker, and server management.

---

Future Plans

Possible improvements:

- add Jellyfin media server
- improve automated backups
- create a service dashboard
- add monitoring and alerts
- expand storage

---

Final Note

A home server does not need expensive hardware.

Even an old laptop can become a powerful personal server capable of running multiple useful services.

This repository documents the idea, structure, and learning process behind building that system.
