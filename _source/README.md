# Hermes University — disaster-recovery backup (RFC-011)
This folder is the durable backup that rides the vault's git remote.
- `courses/<CODE>/` — authored course sources (course.yaml + research dossier).
- `secrets.tar.gz.enc` — profile.yaml, config.env, ~/.hermes/{.env,config.yaml,cron/jobs.json,auth.json},
  Google-Calendar token — AES-256 encrypted. Decrypt only with your passphrase (~/.hermes/backup.key).
To restore on a fresh droplet: run `bootstrap.sh <code-repo> <vault-repo>`.
