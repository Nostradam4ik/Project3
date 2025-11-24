## Rapport d’implémentation

### 1. Stack technique
- Backend : Python 3.11, FastAPI, SQLModel, Celery/RQ, Redis.
- UI : React 18 + Vite, Tailwind.
- IA : OpenAI GPT-4o ou DeepSeek-R1 via API, fallback local (llama.cpp) optionnel.

### 2. Organisation du code
- `gateway/api` : endpoints REST, schémas Pydantic.
- `gateway/rules` : moteur (chargement YAML, sandbox Jinja2, macros métiers).
- `gateway/connectors` : pattern adapter + interface `execute()/rollback()`.
- `gateway/workflow` : états, transitions, notifications.
- `infra/docker` : docker-compose MidPoint/ApacheDS/Odoo + gateway.

### 3. Processus CI/CD
- Git branching : `main`, `develop`, `feature/*`.
- GitHub Actions : `lint-test.yml`, `build-docker.yml`.
- Sécurité : SAST (Bandit), dépendances (pip-audit), Trivy sur images.
- Déploiement : push image sur registry, `docker stack deploy` ou k8s helm chart.

### 4. Guide développeur
1. `python -m venv .venv && pip install -r requirements.txt`.
2. `cp .env.example .env` puis renseigner secrets (Keycloak, OpenAI).
3. `uvicorn gateway.main:app --reload`.
4. Lancer workers (`celery -A gateway.worker worker -l info`).
5. Tests : `pytest`.

### 5. Points d’attention
- Transactions distribuées : utilisation de pattern saga; chaque connecteur fournit compensation.
- Sandbox IA : limiter prompts, journaliser les suggestions appliquées.
- Données sensibles : chiffrer au repos (PostgreSQL TDE, Secrets Vault).

_Co-auteurs : <votre nom>, achibani@gmail.com_

