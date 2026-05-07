# Getting Started

## 1. Create an account

Go to [vscars.latenightstack.com](https://vscars.latenightstack.com) and register. During beta, all accounts are free.

## 2. Get your API key

After logging in, open **Settings → API Key → Generate**. Copy the key — it's shown once.

## 3. Install the CLI

```bash
pip install vscars-cli
```

Or use the one-liner:

```bash
curl -fsSL https://vscars.latenightstack.com/install.sh | bash
```

## 4. Connect your machine

```bash
vscars init --api-key vscars_<your_key>
vscars start
```

The CLI connects to the relay over WebSocket and your machine appears in the **Machines** tab.

## 5. Start using it

From [vscars.latenightstack.com](https://vscars.latenightstack.com) on any device:

- **Terminal** — type a command, see output stream live
- **Files** — browse your filesystem, open and edit files
- **Git** — see status, stage changes, generate an AI commit message, push
- **AI Chat** — ask questions, get code — uses your own API key

## Add your AI key

Go to **Settings → AI Keys** and paste your `ANTHROPIC_API_KEY` or `OPENAI_API_KEY`. During beta you get 5 requests/day without a key using the shared pool.

## Keep the CLI running

To keep your machine connected after closing the terminal, run the CLI in the background:

**macOS / Linux:**
```bash
nohup vscars start > ~/.vscars/vscars.log 2>&1 &
```

**Or as a systemd service (Linux):**
```bash
vscars install-service   # sets up and enables systemd unit
```
