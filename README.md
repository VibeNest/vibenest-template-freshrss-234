# VibeNest Template: FreshRSS

This is a thin VibeNest-ready deploy adapter for [FreshRSS](https://github.com/FreshRSS/FreshRSS).

It does not fork or modify FreshRSS. The repo only provides explicit Docker defaults:

- official image: `freshrss/freshrss:latest`
- app port: `80` (`80:80` in compose so Coolify can bind the VibeNest domain to the service)
- persistent data and extensions volumes
- feed refresh cron enabled
- no container-level healthcheck; the FreshRSS setup flow can make simple path checks misleading, so VibeNest validates readiness through the public URL smoke.

## VibeNest notes

One-click deploy stays disabled until smoke confirms the public URL opens the FreshRSS setup/login UI and memory use is acceptable for the free tier.

## Upstream

- Product: https://github.com/FreshRSS/FreshRSS
- Image: https://hub.docker.com/r/freshrss/freshrss
- Docker compose example: https://github.com/FreshRSS/FreshRSS/blob/edge/Docker/freshrss/docker-compose.yml
