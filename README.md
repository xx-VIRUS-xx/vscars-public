<div align="center">

<img src="https://img.shields.io/badge/VSCARS-Your%20Dev%20Machine%20in%20Your%20Pocket-7c3aed?style=for-the-badge&labelColor=070711" alt="VSCARS"/>

# VSCARS

### Your dev machine, from anywhere.

Run commands, edit files, chat with AI, and ship code — from your phone, tablet, or any browser, anywhere on the planet.

[![Live App](https://img.shields.io/badge/Live%20App-vscars.latenightstack.com-7c3aed?style=flat-square)](https://vscars.latenightstack.com)
[![Beta](https://img.shields.io/badge/status-beta-06b6d4?style=flat-square)]()
[![Python 3.10+](https://img.shields.io/badge/CLI-python%203.10+-f59e0b?style=flat-square)](https://www.python.org)

[**Sign Up**](https://vscars.latenightstack.com) · [**How It Works**](#how-it-works) · [**CLI Install**](#install-the-cli) · [**FAQ**](#faq)

</div>

---

## What is VSCARS?

VSCARS is a **cloud relay** that connects your development machine to a mobile-first web app. Install the CLI on your machine, connect it to the relay, and control everything from your phone — no SSH, no port forwarding, no VPN.

Your machine runs the tools. The relay just passes messages.

---

## How It Works

```
📱 Phone / Browser
       │  HTTPS + JWT
       ▼
🌐 VSCARS Relay  (vscars.latenightstack.com)
       │  WebSocket + API Key
       ▼
💻 vscars CLI  (running on YOUR machine)
       │  executes locally
       ▼
📁 Your filesystem · terminal · git
```

1. **Sign up** at [vscars.latenightstack.com](https://vscars.latenightstack.com)
2. **Install the CLI** on your machine (`pip install vscars-cli`)
3. **Run `vscars start`** — your machine appears in the app
4. **Control it** from any browser on any device

Nothing executes on the relay server. Your files, your terminal, your machine.

---

## Features

- **Terminal** — run commands, stream output live to your phone
- **File manager** — browse, create, read, edit, delete files
- **Git panel** — status, diff, stage, AI-generated commit messages, push
- **AI chat** — bring your own Anthropic or OpenAI key; 5 free requests/day during beta
- **Saved workflows** — one-tap shortcuts for your common commands
- **Idea vault** — capture thoughts on the go, tag and resolve later
- **Multi-machine** — connect more than one machine to your account

---

## Install the CLI

**Requires Python 3.10+**

```bash
pip install vscars-cli
```

Or use the one-liner install script:

```bash
curl -fsSL https://vscars.latenightstack.com/install.sh | bash
```

After installing:

```bash
vscars init --api-key YOUR_API_KEY   # get your key from Settings in the app
vscars start                          # connects your machine to the relay
```

Your machine will appear in the **Machines** tab. Done.

---

## Beta Plan

During beta, all accounts are free:

| Feature | Beta (Free) |
|---|:-:|
| Machine access (terminal, files, git) | ✅ |
| AI chat | ✅ 5 requests/day (your key) |
| Machines | 1 |
| Daily command limit | unlimited |

Bring your own `ANTHROPIC_API_KEY` or `OPENAI_API_KEY` — configure it in **Settings** inside the app.

---

## Docs

- [Getting Started](docs/getting-started.md)
- [CLI Reference](docs/cli-reference.md)
- [API Keys & Security](docs/security.md)
- [Troubleshooting](docs/troubleshooting.md)

---

## FAQ

**Does my laptop have to be on?**
Yes — the CLI runs on your machine and the relay proxies to it. The app shows your machine as offline if the CLI isn't running.

**Is it safe to expose my machine?**
All traffic is HTTPS (via Cloudflare Tunnel), authenticated with rotating JWTs. The CLI runs as your user — same permissions as you sitting at the keyboard. Don't run it as root.

**Do I need a GitHub Copilot subscription?**
No. VSCARS uses the Anthropic and OpenAI APIs directly. Paste your key in Settings.

**What happens if the relay goes down?**
Your machine still runs normally — only the remote control is unavailable. The CLI reconnects automatically when the relay comes back.

**Can I use this on Windows / Linux?**
Yes. The CLI is pure Python and runs on macOS, Linux, and Windows (WSL recommended).

---

## Security

Found a bug or vulnerability? Email **founder@latenightstack.com** — we respond within 48 hours.

---

## License

The VSCARS relay is proprietary software. The CLI (`vscars-cli`) is MIT licensed.

© 2026 Late Night Stack
