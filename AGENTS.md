# Base44 Dev Environment

## Project Overview
Static HTML/CSS personal profile page (no build step, no backend, no dependencies).

## Running the App
```
docker compose -f docker-compose.base44.yml up -d
```
Serves via nginx:alpine on host port 3000. Source is bind-mounted read-only into the container.

## Key Notes
- The main HTML file is `Index.html` (capital **I**). An nginx config (`nginx.default.conf`) sets `index Index.html` because nginx defaults to lowercase `index.html`.
- The host directory must be world-traversable (chmod 755) or nginx's worker user cannot read the bind-mounted files and returns 403.
- No external credentials or secrets are required.
- Edits to HTML/CSS are visible on browser refresh (no live-reload dev server; static files are read from disk per request).
