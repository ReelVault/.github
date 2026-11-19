<div align="center">

<img src="assets/banner.png" alt="ReelVault — your media, on your hardware" width="1200">

# ReelVault

**Your media, on your hardware.**

[![Latest release](https://img.shields.io/github/v/release/ReelVault/reelvault?style=for-the-badge&color=00E676)](https://github.com/ReelVault/reelvault/releases)
[![Docs](https://img.shields.io/badge/docs-reelvault.org-00E676?style=for-the-badge)](https://reelvault.org)
[![License](https://img.shields.io/badge/license-GPL--3.0-blue?style=for-the-badge)](https://github.com/ReelVault/reelvault/blob/main/LICENSE)
[![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20Linux%20%7C%20Docker-00E676?style=for-the-badge)](https://github.com/ReelVault/installer)

[Docs](https://reelvault.org) · [Install](#get-started) · [Why ReelVault](#why-reelvault) · [Repositories](#repositories) · [Contribute](#contribute)

</div>

ReelVault is a **self-hosted media server**. You run it on a computer you own — a NAS, a mini PC or an old desktop — point it at your movie and TV folders, and then watch that library in a browser on any screen at home. It fills in posters and descriptions, picks up subtitle files and remembers where you left off. Your files and watch history stay on your hardware.

<div align="center">

<img src="https://reelvault.org/screenshots/dashboard.webp" alt="The ReelVault dashboard" width="900">

</div>

## Why ReelVault

| What you get | What it means for you |
|---|---|
| 🎬 **A library from your own files** | Point ReelVault at your folders. It finds the titles, adds posters and descriptions, and remembers where you stopped in each one. |
| ▶ **Playback without the guesswork** | If your device can play a file as-is, that's what it gets — no re-encoding, no quality loss. If it can't, the server converts it on the fly, using your graphics card when it can. You set the quality limits; it handles the rest. |
| 👨‍👩‍👧 **Room for everyone** | One account, several viewers. Each profile keeps its own continue-watching list, watchlist and preferences, and you can lock a profile with a PIN. |
| 🧩 **Extras when you want them** | Add posters from TMDB or OMDb, community skip markers, requests, webhooks and notifications — all as plugins. Install them from the admin panel; they load straight away, with no restart. |
| 🔒 **Everything stays yours** | Your media and watch history live on your machine. You choose which plugins, if any, can reach outside services. |
| 🛠️ **Room to build** | A typed SDK and a plugin system let you write your own app or add whatever's missing. |

## Get started

Docker is the quickest way to get started. Run these commands in a folder of your choice:

```bash
mkdir reelvault && cd reelvault
curl -fsSLO https://raw.githubusercontent.com/ReelVault/installer/main/docker-compose.yml
docker compose up -d
```

Open **http://localhost:3030**, create your admin account, then follow [Adding your media](https://reelvault.org/guide/libraries) to tell the server where your movies and shows are.

No Docker? The [installers](https://github.com/ReelVault/installer#install) do the same thing in one command on Windows or Linux. If you're new here, [What is ReelVault?](https://reelvault.org/guide/introduction) and the [FAQ](https://reelvault.org/guide/faq) are good starting points.

## Repositories

| Repository | What it is | Go here if… |
|---|---|---|
| [🖥️ **reelvault**](https://github.com/ReelVault/reelvault) | The server: library, streaming and plugins | You want to run, configure or contribute to the server |
| [🌐 **website**](https://github.com/ReelVault/website) | The web and desktop app | You want to change the interface you see in the browser |
| [📦 **sdk**](https://github.com/ReelVault/sdk) | The typed TypeScript SDK, `@reelvault/sdk` | You want to call the API or build tooling around it |
| [🧩 **plugins**](https://github.com/ReelVault/plugins) | Official plugins and their catalog | You want to install or publish an extension |
| [🚀 **plugin-template**](https://github.com/ReelVault/plugin-template) | A starting point for a new plugin | You want to write your first plugin |
| [⚙️ **installer**](https://github.com/ReelVault/installer) | Installers and the Docker setup | You want an easy install or a release bundle |
| [📚 **reelvault.org**](https://github.com/ReelVault/reelvault.org) | The documentation site | You want to improve the docs |

## Contribute

New here? Read [CONTRIBUTING.md](https://github.com/ReelVault/.github/blob/main/CONTRIBUTING.md). Found a security problem? Report it privately — [SECURITY.md](https://github.com/ReelVault/.github/blob/main/SECURITY.md) tells you how. Everyone is expected to follow the [Code of Conduct](https://github.com/ReelVault/.github/blob/main/CODE_OF_CONDUCT.md).

ReelVault is free software, licensed under GPL-3.0.
