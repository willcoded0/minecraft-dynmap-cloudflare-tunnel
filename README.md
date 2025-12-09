# Minecraft + Dynmap via Cloudflare Tunnel

This repo documents how I host a Minecraft server and Dynmap web map
on my homelab, and make them accessible over the internet using
**Cloudflare Tunnel** instead of opening ports on my router.

--

## 🕹️ What I'm Hosting

- **Minecraft server** running on a Linux VM / container.
- **Dynmap** plugin providing a live web-based map of the world.
- Both services run on my Proxmox-based homelab server.

---

## 🌐 How It’s Exposed to the Internet

I use **Cloudflare Tunnel** to route external traffic to my homelab:

- Cloudflare Tunnel connects my server to Cloudflare’s network.
- I point a hostname (in my case, `https://batmap.win/`)
  at the tunnel.
- Players and browsers connect via the hostname, not my home IP.

This lets me:

- Avoid opening Minecraft/Dynmap ports on my router.
- Use Cloudflare’s DNS and HTTPS features.
- Move services between machines or change local IPs without
  changing how people connect.

---

## 🧪 What I Learned

From this setup I gained hands-on experience with:

- Running a game server on Linux.
- Basic networking (ports, internal IPs, services).
- Using **Cloudflare Tunnel** to expose internal services safely.
- Treating a personal homelab like a small production environment.
