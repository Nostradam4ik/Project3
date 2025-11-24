## Rapport CI/CD

### 1. Pipeline CI
- **Étapes** :
  1. `setup-python` + cache pip.
  2. `ruff` + `black --check`.
  3. `pytest --cov`.
  4. `bandit -r gateway`.
  5. `pip-audit`.
- **Triggers** : PR vers `develop` et `main`, push tags release.

### 2. Pipeline CD
- Build image Docker multi-stage (FastAPI + connectors).
- Scan image via Trivy.
- Publication sur GitHub Container Registry.
- Déploiement :
  - Environnement test : `docker compose` sur VM.
  - Environnement demo : cluster k3s (Helm chart).

### 3. Observabilité pipeline
- Notifications Slack/Teams.
- Rétention artefacts 14 jours.
- Politique de secrets : GitHub Encrypted secrets + Vault pour runtime.

_Co-auteurs : <votre nom>, achibani@gmail.com_

