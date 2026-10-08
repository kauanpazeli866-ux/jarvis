# AGENTS.md

## Project Overview
Jarvis is a static PWA (Progressive Web App) — a Portuguese-language voice assistant. No build step, no backend, no package.json. All logic is in `index.html` (embedded JS/CSS), with `manifest.json`, `sw.js` (service worker), and two icon files.

## Running in the Sandbox
- `docker-compose.base44.yml` uses `nginx:alpine` to serve the static files from the repo root on port 3000.
- No dependencies to install; no build step.
- If you get a 403, the repo root directory may have restrictive permissions — run `chmod 755 .` to fix.

## Credentials
- No external credentials are required at boot. The app stores API keys (Gemini, Groq) in the browser's localStorage via the in-app Settings > APIs screen. The user enters them at runtime.
- A "Superagent" backend mode is available by default and requires no local keys.
