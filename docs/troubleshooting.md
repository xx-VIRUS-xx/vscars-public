# Troubleshooting

## Machine shows as Offline

The CLI isn't running or lost its connection. On your machine:

```bash
vscars start
```

If it was running and disconnected, check logs:

```bash
cat ~/.vscars/vscars.log
```

Common causes:
- Network interruption (the CLI reconnects automatically, but may need a restart)
- API key revoked — regenerate in Settings and re-run `vscars init`
- Relay unreachable — check [vscars.latenightstack.com/api/health](https://vscars.latenightstack.com/api/health)

---

## `vscars: command not found`

The CLI isn't on your PATH. If you installed with pip:

```bash
# Find where pip installs scripts
python3 -m site --user-base
# Add /bin to your PATH, or use the full path:
~/.local/bin/vscars start
```

Or use the one-liner installer which handles PATH automatically:

```bash
curl -fsSL https://vscars.latenightstack.com/install.sh | bash
```

---

## `websockets` connection error on start

Make sure you're running Python 3.10+:

```bash
python3 --version
```

If below 3.10, upgrade Python or use pyenv.

---

## AI chat returns "No AI provider configured"

You need to add your own API key. Go to **Settings → AI Keys** in the app and paste your `ANTHROPIC_API_KEY` or `OPENAI_API_KEY`.

---

## Permission denied on file operations

The CLI runs as your user. If it can't read/write a file, check the actual file permissions:

```bash
ls -la /path/to/file
```

---

## Still stuck?

Open an issue at [github.com/latenightstack/vscars](https://github.com/latenightstack/vscars/issues) or email **support@latenightstack.com**.
