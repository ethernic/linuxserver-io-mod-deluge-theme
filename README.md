# linuxserver-io-mod-deluge-theme
[Deluge Web Dark](https://github.com/joelacus/deluge-web-dark-theme) theme mod for LinuxServer.io's qBittorrent container

## Usage
Add an environment variable called `DOCKER_MODS` with the value `ethernic/linuxserver-io-mod-deluge-theme` when creating the container.

Example: `docker-compose.yml`
```yml
---
version: "2.1"
services:
  deluge:
    image: ghcr.io/linuxserver/deluge
    container_name: deluge
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Europe/London
      - DELUGE_LOGLEVEL=error #optional
      - DOCKER_MODS=ethernic/linuxserver-io-mod-deluge-theme
    volumes:
      - /path/to/deluge/config:/config
      - /path/to/your/downloads:/downloads
    ports:
      - 8112:8112
      - 6881:6881
      - 6881:6881/udp
    restart: unless-stopped
```

## Sources
- [Theme Repo](https://github.com/joelacus/deluge-web-dark-theme)
- [LinuxServer's qBittorrent on Docker Hub](https://hub.docker.com/r/linuxserver/deluge)

