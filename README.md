# Caddy 2.7 with Cloudflare

![Docker Cloud Build Status](https://img.shields.io/github/actions/workflow/status/ManfredRichthofen/caddy-cloudflare/docker-publish.yml)

Prebuilt Caddy v2 docker image with Cloudflare module [caddy-dns/cloudflare](https://github.com/caddy-dns/cloudflare). 

```sh
version: "3.7"

services:
  caddy:
    image: ghcr.io/manfredrichthofen/caddy-cloudflare:main
    restart: unless-stopped
    ports:
      - "80:80"
      - "443:443"
      - "443:443/udp"
    volumes:
      - $PWD/Caddyfile:/etc/caddy/Caddyfile
      - $PWD/site:/srv
      - caddy_data:/data
      - caddy_config:/config

volumes:
  caddy_data:
    external: true
  caddy_config:
```
