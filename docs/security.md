# API Keys & Security

## API Keys

Your API key (`vscars_...`) is generated in **Settings → API Key → Generate**.

- Keys are shown **once** at generation. Store it securely.
- You can revoke and regenerate at any time from Settings.
- The key is used only by the CLI to authenticate with the relay. It never touches your filesystem directly.

## How authentication works

1. You log in to the web app with your email + password → get a JWT session token
2. The CLI authenticates with your API key → gets a long-lived WebSocket connection
3. Every tool call from the app goes through your JWT-authenticated session → relay → CLI WebSocket

The relay only forwards messages between authenticated sessions. It never stores your files or command output.

## What the CLI can access

The CLI runs as **your user** on your machine — same permissions as you at the keyboard. It can read, write, and execute anything you can. Keep this in mind:

- Don't run `vscars start` as root
- Don't leave it running on machines with sensitive credentials if you don't trust your network

## Command blocklist

The relay and CLI both reject patterns like `rm -rf /`, fork bombs, and `/etc/passwd` overwrites. This is a safety net, not a sandbox — treat CLI access as equivalent to SSH access.

## Transport security

All traffic between your browser and the relay is HTTPS (via Cloudflare Tunnel). All traffic between the relay and your CLI is WSS (WebSocket Secure).

## Responsible disclosure

Found a vulnerability? Email **security@latenightstack.com**. We respond within 48 hours and don't pursue legal action against good-faith researchers.
