# Secrets — Joint Task Force Draugr

This directory holds Docker Secret files for JFTD's bots. These files are **never committed to git**.

## Required Secrets

| File | Description | Source |
|------|-------------|--------|
| `ratatoskr_fluxer_token` | Fluxer bot token for Ratatoskr | Fluxer Developer Portal |

---

## Setup: Fluxer Bot Token

1. Obtain a bot token from the Fluxer Developer Portal for Ratatoskr
2. Create the secret file:
   ```bash
   printf "YOUR_RATATOSKR_TOKEN_HERE" > ./secrets/ratatoskr_fluxer_token
   ```

---

## Deploying Secrets

After creating the secret file, set permissions:

```bash
chmod 600 ./secrets/ratatoskr_fluxer_token
```

## Security Reminders

- Secret files are referenced by `docker-compose.yml` and mounted at `/run/secrets/`
- Bots read them via the `load_secret()` pattern in `config_manager.py`
- Never commit these files — only this README is tracked
- Rotate secrets periodically and after any suspected exposure
- The `secrets/` directory is gitignored in this repository

---

*For the fallen and the worthy* ⚔️
