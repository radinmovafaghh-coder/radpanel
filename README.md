<div align="center">

<img src="./media/radpanel-light.png" alt="RadPanel" width="320">

### RadPanel

**A modern, minimal web control panel for Xray-core — install in one command, manage from any device.**

[![Release](https://img.shields.io/github/v/release/radinmovafaghh-coder/radpanel?style=flat-square&color=7c3aed)](https://github.com/radinmovafaghh-coder/radpanel/releases)
[![Build](https://img.shields.io/github/actions/workflow/status/radinmovafaghh-coder/radpanel/release.yml?style=flat-square&label=build)](https://github.com/radinmovafaghh-coder/radpanel/actions)
[![License](https://img.shields.io/badge/license-GPL--3.0-7c3aed?style=flat-square)](https://www.gnu.org/licenses/gpl-3.0.en.html)
[![Downloads](https://img.shields.io/github/downloads/radinmovafaghh-coder/radpanel/total?style=flat-square&color=7c3aed)](https://github.com/radinmovafaghh-coder/radpanel/releases)
[![Languages](https://img.shields.io/badge/i18n-13%20languages-7c3aed?style=flat-square)](#supported-languages)

</div>

---

## What is RadPanel?

RadPanel is a self-hosted control panel for [Xray-core](https://github.com/XTLS/Xray-core).
It gives you a clean web UI to create inbounds, hand out clients, watch traffic, and run
several servers from one dashboard — without hand-editing JSON.

It is a **GPL-3.0 fork of [3x-ui](https://github.com/MHSanaei/3x-ui)** by MHSanaei. RadPanel
keeps the same licence and keeps the upstream copyright notices intact (see [NOTICE](NOTICE));
what it changes is the branding, the theme, and the installer target.

> [!IMPORTANT]
> For personal use. Do not use it for illegal purposes or in a production environment.

## Why RadPanel?

- **One command to install.** `bash <(curl -Ls .../install.sh)` and you are in.
- **Lightweight and clean.** A focused UI that stays out of your way.
- **Works everywhere.** Linux (amd64, arm64, armv7, armv6, armv5, 386, s390x) and Windows.
- **13 languages**, light / dark / ultra-dark themes.
- **SQLite by default**, PostgreSQL when you need it.
- **Fully open.** GPL-3.0, source included, no telemetry.

## Features

- **Multi-protocol inbounds** — VLESS, VMess, Trojan, Shadowsocks, WireGuard, AmneziaWG, TUIC v5, Hysteria2, MTProto, HTTP, SOCKS (Mixed), Dokodemo-door / Tunnel, and TUN.
- **Modern transports & security** — TCP (Raw), mKCP, WebSocket, gRPC, HTTPUpgrade, and XHTTP, secured with TLS, XTLS, and REALITY.
- **AmneziaWG built in** — DPI-resistant WireGuard runs inside the panel on a userspace network stack, with no kernel module, DKMS, or extra packages to install.
- **TUIC v5 sidecar** — High-performance QUIC-based proxy with native UDP relay traffic metering, 0-RTT handshakes, and BBR congestion control.
- **MTProto proxies** — per-client FakeTLS secrets, ad-tags, and quotas, applied live without dropping existing connections.
- **Fallbacks** — serve multiple protocols on a single port (e.g. VLESS and Trojan on 443) using Xray's fallback support.
- **Per-client management** — traffic quotas, expiry dates, IP limits with trusted-address exemptions, HWID device limits, scheduled renewal cycles, live online status, and one-click share links, QR codes, and subscriptions.
- **Traffic statistics** — per inbound, per client, and per outbound, with reset controls.
- **Multi-node support** — manage and scale across multiple servers from a single panel, including cloning inbounds onto other nodes.
- **Outbound & routing** — WARP, NordVPN, PIA, custom routing rules, load balancers with balancer-to-balancer fallback, and outbound proxy chaining. Bundled geosite and geoip categories are browsable straight from the rule editor.
- **Built-in subscription server** — raw, JSON, and Clash output, auto-selected from the client's User-Agent, plus [custom page templates](docs/custom-subscription-templates.md).
- **Telegram and Discord bots** for remote monitoring and management.
- **RESTful API** with scoped, optionally expiring tokens and an in-panel API reference.
- **Installable panel (PWA)** — pin RadPanel to a desktop or phone home screen.
- **Flexible storage** — SQLite (default) or PostgreSQL.
- **13 UI languages** with dark and light themes.
- **Fail2ban integration** for enforcing per-client IP limits.

## Screenshots

<details>
<summary>Click to expand</summary>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./media/01-overview-dark.png">
  <img alt="Overview" src="./media/01-overview-light.png">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./media/02-add-inbound-dark.png">
  <img alt="Inbounds" src="./media/02-add-inbound-light.png">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./media/03-add-client-dark.png">
  <img alt="Add client" src="./media/03-add-client-light.png">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./media/05-add-nodes-dark.png">
  <img alt="Configs" src="./media/05-add-nodes-light.png">
</picture>

</details>

## Quick Start

```bash
bash <(curl -Ls https://raw.githubusercontent.com/radinmovafaghh-coder/radpanel/master/install.sh)
```

To install a specific version, append its tag (e.g. `v3.7.0`):

```bash
bash <(curl -Ls https://raw.githubusercontent.com/radinmovafaghh-coder/radpanel/master/install.sh) v3.7.0
```

To install the rolling **dev** build (latest per-commit pre-release from `main`, not a stable release), pass `dev-latest`:

```bash
bash <(curl -Ls https://raw.githubusercontent.com/radinmovafaghh-coder/radpanel/master/install.sh) dev-latest
```

During installation a random username, password, and access path are generated. After installation, run `radpanel` to open the management menu, where you can start/stop the service, view or reset your login credentials, manage SSL certificates, and more.

Every release asset is published with a `.sha256` sum next to it. Both `install.sh` and the updater verify the archive against that sum and abort on a mismatch.

Documentation for the panel lives in the [docs/](docs/) folder of this repo. The upstream project's docs at docs.sanaei.dev also largely apply, since RadPanel shares its core.

### Unattended install

The installer also runs **non-interactively** for cloud-init.
Set `XUI_NONINTERACTIVE=1` (or pipe with no TTY) and it installs end-to-end with
zero prompts, generating random credentials and writing them to
`/etc/radpanel/install-result.env`. See [`deploy/`](deploy/) for:

- [Cloud-init user-data](deploy/cloud-init/) — unattended install on any cloud (Hetzner/AWS/DO/Vultr/GCP/Azure/Oracle)
- [Hetzner Cloud notes](deploy/marketplace/hetzner/) — cloud-init deployment on Hetzner

## Supported Platforms

**Operating systems:** Ubuntu, Debian, Armbian, Fedora, CentOS, RHEL, AlmaLinux, Rocky Linux, Oracle Linux, Amazon Linux, Virtuozzo, Arch, Manjaro, Parch, openSUSE (Tumbleweed / Leap), Alpine, and Windows.

**Architectures:** `amd64` · `386` · `arm64` (aarch64) · `armv7` · `armv6` · `armv5` · `s390x`.

## Database Options

RadPanel supports two backends, chosen during the install:

- **SQLite** (default) — a single file at `/etc/radpanel/radpanel.db`. Zero setup, ideal for small and medium deployments.
- **PostgreSQL** — recommended for high client counts or multi-node setups. The installer can install PostgreSQL locally for you, or accept a DSN to an existing server.

At runtime the backend is selected via environment variables (the installer writes these to `/etc/default/radpanel` for you):

```
XUI_DB_TYPE=postgres
XUI_DB_DSN=postgres://xui:password@127.0.0.1:5432/xui?sslmode=disable
```

### Migrating an existing SQLite install to PostgreSQL

```bash
radpanel migrate-db --dsn "postgres://xui:password@127.0.0.1:5432/xui?sslmode=disable"
# then set XUI_DB_TYPE and XUI_DB_DSN in /etc/default/radpanel and restart:
systemctl restart radpanel
```

The source SQLite file is left untouched; remove it manually once you have verified the new backend.

### Docker

The default `docker compose up -d` keeps using SQLite. To run with the bundled PostgreSQL service, uncomment the two `XUI_DB_*` env lines in `docker-compose.yml` and start with the profile:

```bash
docker compose --profile postgres up -d
```

The image bundles Fail2ban (enabled by default) to enforce per-client **IP limits**. Fail2ban bans offenders with `iptables`, which requires the `NET_ADMIN` capability. `docker-compose.yml` already grants it via `cap_add`; if you start the container with `docker run` instead, add the capabilities yourself, otherwise bans are logged but never applied:

```bash
docker run -d --cap-add=NET_ADMIN --cap-add=NET_RAW ... ghcr.io/radinmovafaghh-coder/radpanel
```

## Environment Variables

| Variable | Description | Default |
| --- | --- | --- |
| `XUI_DB_TYPE` | Database backend: `sqlite` or `postgres` | `sqlite` |
| `XUI_DB_DSN` | PostgreSQL connection string (when `XUI_DB_TYPE=postgres`) | — |
| `RADPANEL_DB_FOLDER` | Directory for the SQLite database file | `/etc/radpanel` |
| `XUI_DB_MAX_OPEN_CONNS` | Maximum open connections (PostgreSQL pool) | — |
| `XUI_DB_MAX_IDLE_CONNS` | Maximum idle connections (PostgreSQL pool) | — |
| `XUI_INIT_WEB_BASE_PATH` | The initial URI path for the web panel | `/` |
| `XUI_ENABLE_FAIL2BAN` | Enable Fail2ban-based IP-limit enforcement | `true` |
| `XUI_LOG_LEVEL` | Log verbosity (`debug`, `info`, `warning`, `error`) | `info` |
| `XUI_DEBUG` | Enable debug mode | `false` |
| `XUI_TUNNEL_HEALTH_MONITOR` | Enable the tunnel health monitor (probes a URL and restarts xray after repeated failures; a restart drops all clients) | `false` |
| `XUI_TUNNEL_HEALTH_PROXY` | Proxy the probe is sent through; point it at a local xray inbound so the probe tests the tunnel (e.g. `socks5://127.0.0.1:1080`). Empty means the probe only checks host connectivity | — |
| `XUI_TUNNEL_HEALTH_URL` | URL probed for tunnel health | `https://www.cloudflare.com/cdn-cgi/trace` |
| `XUI_TUNNEL_HEALTH_INTERVAL` | Interval between probes | `30s` |
| `XUI_TUNNEL_HEALTH_TIMEOUT` | Per-probe timeout | `10s` |
| `XUI_TUNNEL_HEALTH_FAILURES` | Consecutive failures before a restart is triggered | `3` |
| `XUI_TUNNEL_HEALTH_COOLDOWN` | Minimum delay between consecutive restarts | `5m` |
| `NODE_TOKEN_ENCRYPTION` | Encryption at rest for node API tokens: `off`, `migration`, or `required` (note: no `XUI_` prefix) | `off` |
| `XUI_NODE_TOKEN_KEY_FILE` | JSON keyring (mode `0600`) holding the active key id and its base64 32-byte keys | `/etc/radpanel/node_token_key.json` |
| `XUI_NODE_TOKEN_KEY` | A single base64 32-byte key, used only when the key file cannot be loaded | — |

The complete list is on the [environment variables reference](https://github.com/radinmovafaghh-coder/radpaneldocs/reference/env-vars).

## Supported Languages

The panel UI is available in 13 languages:

English · فارسی · العربية · 中文（简体） · 中文（繁體） · Español · Русский · Українська · Türkçe · Tiếng Việt · 日本語 · Bahasa Indonesia · Português (Brasil)

## Contributing

Contributions are welcome. Please read the [Contributing Guide](/CONTRIBUTING.md) before opening an issue or pull request.

## A Special Thanks to (upstream)

- [alireza0](https://github.com/alireza0/) — upstream 3x-ui contributor

## Acknowledgment

- [Iran v2ray rules](https://github.com/chocolate4u/Iran-v2ray-rules) (License: **GPL-3.0**): _Enhanced v2ray/xray and v2ray/xray-clients routing rules with built-in Iranian domains and a focus on security and adblocking._
- [Russia v2ray rules](https://github.com/runetfreedom/russia-v2ray-rules-dat) (License: **GPL-3.0**): _This repository contains automatically updated V2Ray routing rules based on data on blocked domains and addresses in Russia._

## Community Tools

Tools and integrations from the upstream 3x-ui community (may work with RadPanel).

- [terraform-provider-radpanel](https://github.com/batonogov/terraform-provider-threexui) (License: **MIT**): _Manage inbounds, clients, panel settings, and Xray configuration as code with Terraform / OpenTofu._
- [RadPanel Manager](https://github.com/yukh975/RadPanel-Manager) (License: **MIT**): _Native Android client for radpanel — dashboard, inbounds, clients with QR sharing, nodes and multi-panel management. Available on F-Droid._

## Credits

RadPanel is a fork of [3x-ui](https://github.com/MHSanaei/3x-ui) and would not exist without it.
All credit for the original panel goes to **MHSanaei** and the 3x-ui contributors.
If you want to support the upstream project, star it and use its own channels.

## Support this fork

Questions, bugs and ideas about RadPanel itself: open an [issue](https://github.com/radinmovafaghh-coder/radpanel/issues).

## Star History

<a href="https://www.star-history.com/?repos=mhsanaei%2Fradpanel&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=radinmovafaghh-coder/radpanel&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=radinmovafaghh-coder/radpanel&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=radinmovafaghh-coder/radpanel&type=date&legend=top-left" />
 </picture>
</a>

<p align="center">
 <a href="https://www.star-history.com/radinmovafaghh-coder/radpanel">
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=rank&theme=dark" /><source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=rank" /><img alt="Star History Rank" src="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=rank" /></picture> <picture><source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=trending&theme=dark" /><source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=trending" /><img alt="GitHub Trending Repository of the Day" src="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=trending" /></picture>
 </a>
</p>
