# minecraft-dynmap-cloudflare-tunnel

Minecraft server with a Dynmap live web map, running on my homelab and accessible at [batmap.win](https://batmap.win) via Cloudflare Tunnel. No open router ports.

## Stack

- Minecraft server on a Linux VM in Proxmox VE
- Dynmap plugin for the live browser map
- Cloudflare Tunnel handling all external access

## How the tunnel works

`cloudflared` on the host connects outbound to Cloudflare's network. DNS for `batmap.win` points at the tunnel, so players connect by hostname and never see my home IP. Moving the server to a different machine or changing its local IP doesn't break anything for players.

## Community

Ran this server for 10+ active players. Beyond the infrastructure side — plugin configs, backups, performance tuning — I handled moderation, resolved disputes, coordinated events, and kept the community actually active. Learned a lot about what makes multiplayer servers work (or not) at a small scale.
