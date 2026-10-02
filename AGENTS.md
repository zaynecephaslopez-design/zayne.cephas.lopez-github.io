# Base44 Dev Environment

## Overview
This is a static single-page site (`index.html`) — Zayne's Airplane Control Tower. No build step, no backend, no dependencies, no external credentials.

## Running
```
docker compose -f docker-compose.base44.yml up -d
```
Serves `index.html` via nginx:alpine on host port 3000. Source is bind-mounted read-only, so edits to `index.html` appear on refresh (no rebuild needed). A custom `nginx.conf` runs the worker as `root` because the sandbox bind-mount produces `0700` directories that nginx's default `nginx` user cannot traverse.

## Health
`GET /` returns 200 with the HTML page.

## Secrets
None required.
