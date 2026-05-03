# minecraft-dynmap-cloudflare-tunnel

Minecraft server infrastructure running on my homelab with a public Dynmap live web map and a custom companion dashboard.

- **Resume-safe live dashboard:** [https://db.batmap.win/resume](https://db.batmap.win/resume)
- **Dynmap:** [map.batmap.win](https://map.batmap.win)
- **Public access:** Cloudflare Tunnel, no open router ports

## What this project covers

This started as a Minecraft + Dynmap + Cloudflare Tunnel setup, then grew into a small live ops dashboard for the server. The dashboard gives players a cleaner web view than raw Dynmap alone and gives me a central place to expose useful server state.

## Stack

- Minecraft server running in a Linux container/VM on Proxmox VE
- Dynmap for the live browser world map
- Custom Python dashboard served at `db.batmap.win`, with the recruiter-safe public view at `/resume`
- Cloudflare Tunnel for HTTPS public access without port forwarding
- Systemd services for dashboard/process management

## Resume-safe dashboard at db.batmap.win/resume

The resume-safe dashboard wraps the live map and shows server-specific features without exposing live chat content:

- Embedded Dynmap centered on the main city/base area
- Live player list parsed from server logs
- Browser-local 12-hour timestamps, so CST/PST/etc. display correctly for each visitor
- Chat-free recruiter/resume view; the private friends view has live chat and web-to-game `tellraw`
- Playtime leaderboard calculated from current and archived Minecraft logs
- Season display for the modded server by reading `seasons.dat`

## How the tunnel works

`cloudflared` connects outbound from the homelab to Cloudflare's network. DNS records for the public hostnames route through the tunnel, so players and website visitors never see my home IP address.

Because the tunnel is hostname-based, I can move services between containers/VMs or change local IPs without breaking public links. Cloudflare handles HTTPS at the edge, while the tunnel forwards traffic to the correct internal service.

## Operational work

Beyond the basic hosting setup, this project includes real server operations work:

- Plugin/config management for a modded Minecraft server
- Dynmap defaults and map centering
- Backup-aware debugging and recovery procedures
- FTB Quests progress restore from timestamped backup ZIPs
- Serene Seasons desync investigation and repeatable sync runbook
- Screen/systemd process control
- Community support for a server with 10+ active players

## Community

Ran this server for 10+ active players. Beyond the infrastructure side, I handled plugin configs, backups, performance tuning, moderation, dispute resolution, events, and general server upkeep. It taught me a lot about running small public services where reliability and user experience both matter.
