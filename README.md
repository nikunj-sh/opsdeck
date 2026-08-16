# OpsDeck — Terminal & DevOps Cheat-Sheet & Command Generator

A sleek, **single-file**, 100% client-side DevOps cheat-sheet and interactive CLI command generator.
No backend, no build step, no telemetry — open `index.html` and go. Works fully offline.

**🌐 Live:** [opsdeck.nikunjvasava.me](https://opsdeck.nikunjvasava.me) · **Repo:** [nikunj-sh/opsdeck](https://github.com/nikunj-sh/opsdeck)

![stack](https://img.shields.io/badge/stack-Tailwind%20%C2%B7%20Alpine.js%20%C2%B7%20Fuse.js-10b981)

## Features

### 🔎 Global keyboard navigation & search
- `⌘K` / `Ctrl+K` or `/` focuses the omni-search bar, `Esc` clears it.
- Fuzzy search (Fuse.js) across titles, commands, descriptions, categories and tags, with match highlighting.
- Category filter pills: **All · Kubernetes · Linux/SysAdmin · Docker & Containers · Git · Networking & SSL**.

### 🛠️ Interactive command builders
Toggle options and get a copy-ready one-liner:
- **Kubernetes Debugger** — exec, ephemeral `debug` container (`--image=busybox`), streaming logs (`--tail`/`--follow`), and multi-port-forwarding.
- **Chmod Visualizer** — R/W/X matrix → live octal (`755`), symbolic (`u=rwx,go=rx`) and full `chmod` command, plus presets and `-R`.
- **Rsync & Archive Generator** — dry-run, `-avzP`, `--delete`, over-SSH, and repeatable `--exclude` entries.
- **K8s Secret & Base64 Tool** — encode/decode strings or decode a whole Secret `data:` block, **entirely in-memory** (nothing is uploaded).
- **OpenSSL / TLS Inspector** — remote expiry check, read cert details, key↔CSR↔cert match, full chain, and CSR generation.

### 📋 Curated snippet vault
High-value, one-click-copy commands for Linux I/O & process triage, Docker housekeeping, advanced Git, Kubernetes and Networking/SSL. Copy strips a leading `$` and shows a "Copied!" transition + toast.

### ⭐ Custom snippets
Add your own commands — saved to `localStorage`, private to your browser, and included in search.

## Run it

Just open the file:

```bash
open index.html          # macOS
```

Or serve it (recommended so CDN fonts/icons load cleanly):

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Tech
Single `index.html` using CDN-hosted **Tailwind CSS**, **FontAwesome**, **Alpine.js** (+ collapse plugin) and **Fuse.js**. JetBrains Mono / Fira Code for code blocks.

> Note: CDNs require a network on first load; after that the browser cache keeps it working offline. For a truly air-gapped copy, vendor the CDN assets locally.
