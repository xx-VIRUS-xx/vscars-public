# CLI Reference

## Installation

```bash
pip install vscars-cli
```

## Commands

### `vscars init`

Connect this machine to your VSCARS account.

```bash
vscars init --api-key vscars_<your_key>
```

Saves config to `~/.vscars/config.json`. Run once per machine.

Options:
- `--api-key` — your API key from Settings (required on first run)
- `--relay` — relay URL (default: `https://vscars.latenightstack.com`)
- `--name` — display name for this machine (default: hostname)

---

### `vscars start`

Start the agent and connect to the relay.

```bash
vscars start
```

Keeps running in the foreground. The machine shows as **Online** in the app while this is running. Reconnects automatically on disconnect with exponential backoff.

---

### `vscars status`

Check connection status and config.

```bash
vscars status
```

---

### `vscars logout`

Remove config and disconnect this machine.

```bash
vscars logout
```

---

## Config file

`~/.vscars/config.json`

```json
{
  "relay_url": "https://vscars.latenightstack.com",
  "api_key": "vscars_...",
  "machine_name": "my-macbook"
}
```

## Logs

Logs are written to `~/.vscars/vscars.log` when running in the background.
