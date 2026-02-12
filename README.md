# Minecraft + Dynmap via Cloudflare Tunnel

A production game server with a live web map, hosted on my homelab and securely exposed
to the internet via **Cloudflare Tunnel**. Served an active community of 10+ players
with full server operations, moderation, and community management.

---

## What I'm Hosting

- **Minecraft server** running on a Linux VM in Proxmox VE
- **Dynmap** plugin providing a live, web-based map of the world
- **Public access** at `https://batmap.win/` via Cloudflare Tunnel

---

## Infrastructure

Cloudflare Tunnel routes external traffic to the homelab without opening any ports:

- Players and browsers connect via hostname, not the home IP
- Cloudflare handles DNS, HTTPS, and DDoS protection
- Services can be migrated between machines without changing how users connect

---

## Community Management

Running a server for 10+ active players required more than just infrastructure:

- **Moderation:** Enforcing rules, resolving player disputes, managing permissions and bans
- **Leadership:** Coordinating events, onboarding new players, maintaining an active community
- **Server Operations:** Performance monitoring, plugin configuration, backup scheduling, and uptime management
- **Troubleshooting:** Diagnosing lag, resolving plugin conflicts, and handling player-reported issues in real time

---

## Skills Demonstrated

- Linux server administration
- Networking (ports, DNS, reverse proxy configuration)
- Cloudflare Tunnel for secure service exposure
- Community leadership and moderation at scale
- Incident response and real-time troubleshooting
