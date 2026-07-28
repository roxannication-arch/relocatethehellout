# relocatethehellout

## Cursor Cloud specific instructions

This repo is a single static page (`index.html`) — a Russian-language landing site ("ВЫЕЗД") with an in-browser relocation route-builder quiz. There is no backend, database, build step, package manager, or dependency install.

### Run (development)

Serve the repo root over HTTP and open `index.html`. Any static server works; e.g.:

```bash
python3 -m http.server 8080 --directory /workspace
```

Then open `http://localhost:8080/`. Editing `index.html` and refreshing the browser is the full dev loop (no hot reload, no watcher).

### Notes / gotchas

- Opening `index.html` via `file://` mostly works, but serving over HTTP is closer to production. Vercel Analytics (`/_vercel/insights/script.js`) 404s locally — harmless, ignore it.
- No lint/test/build tooling exists in this repo. There is nothing to install, so the startup update script is effectively a no-op.
- Core functionality to smoke-test: scroll to the "Собери черновик маршрута" builder, answer all 8 questions (click an option, then "Дальше"), then click "Показать маршрут" to render the personalized draft.
- External payment links (Whop, Telegram bot) are out of scope for local testing.
