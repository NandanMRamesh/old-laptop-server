# old-laptop-server
My Journey turning an old laptop into a self-hosted server.
# Old Laptop → Home Server (Ubuntu Server + Docker)

Repurposed an HP Laptop 15-bs series into a small home server.  
Current scope: headless Ubuntu Server, wired-only networking, Docker runtime, safe power behavior (no sleep on lid close), and automatic screen blanking after inactivity.

---

## ✅ What’s implemented

- Ubuntu Server 22.04 LTS installed
- OpenSSH server enabled for remote admin
- Docker Engine installed and verified
- Wired Ethernet as the only network path (Wi-Fi disabled to avoid instability)
- “Lid closed” does **not** suspend/shutdown
- Screen blanks after 5 minutes of inactivity (server keeps running)

---

## Hardware / Network

- **Host:** HP Laptop 15-bs series, Intel i3, 8 GB RAM, 1 TB HDD
- **Network:** LAN via Ethernet (interface: `eno1`)
- **Router:** DHCP reservation used so the server keeps the same IP (e.g., `192.168.1.12`)

---

## Installation & Configuration Notes

### 1) Base OS
Standard Ubuntu Server install (no desktop). During setup:
- Enabled **OpenSSH** for remote access.
- Left **Ubuntu Pro** disabled (can be enabled later).

### 2) configure netplan
enabled only the ethernet port, no wifi as it give me trouble.
![netplan.yaml](images/netplan-yaml.png)

### 3) installed docker
installed docker
![docker-hello-world](images/docker-hello-world.png)

### 4)Nextcloud Setup Progress 🚀

- Installed Ubuntu Server on old laptop
- Installed Docker
- Disabled Wi-Fi, using Ethernet only
- Configured laptop to not sleep when lid closed (screen off after 5 min)
- Installed Docker Compose
- Tested Docker with Nginx playground
- ✅ Deployed Nextcloud with MariaDB in Docker
- Fixed DB connection/authentication issues
- Accessing Nextcloud locally at `http://192.168.1.99:8080`
- Login successful with admin account
- Mobile access confirmed (via HTTP, HTTPS requires proxy setup later)