## Architecture technique

### 1. Composants majeurs
- **Gateway API (FastAPI + Python)** : endpoints `/provision`, `/rules`, `/workflow`, `/reconcile`.
- **Rule Engine** : interprète YAML/JSON avec expressions Jinja2 + fonctions Python sandboxées; support versioning Git.
- **Connectors layer** : adaptateurs modulaires (AD/LDAP, SQLAlchemy, Odoo XML-RPC, GLPI REST, Keycloak REST, Firebase Admin SDK). Pattern `Command` pour rollback.
- **Workflow Service** : orchestrateur pré/post avec état persistant (Redis/SQLite) + file d’attente (RQ/Celery).
- **Audit & Cache** : base en mémoire (SQLite+SQLModel) pour journaliser, plus `redis` pour cache d’état cibles.
- **Vector Log Store** : Qdrant/FAISS pour recherche sémantique sur résumés d’opérations.
- **Admin UI** : React + FastAPI backend (mêmes services) authentifiés via Keycloak (OIDC).
- **IA Agent** : wrapper OpenAI/DeepSeek (function calling) exposé via `/ai/assist`.

### 2. Flux principal
1. MidPoint appelle `/provision`.
2. Gateway valide JWT, charge règles selon `policyId`.
3. Rule Engine calcule attributs par cible, enrichit payload.
4. Workflow pré si actif → attente approbations.
5. Transaction orchestrée : connecteurs exécutent commandes; en cas d’échec, rollback inverse.
6. Audit: enregistrement + indexation vectorielle.
7. Réponse consolidée renvoyée à MidPoint.

### 3. Sécurité
- Authentification via Keycloak → tokens pour MidPoint et UI.
- Chiffrement secrets (Vault/Azure Key Vault option).
- Hardening : validation schéma Pydantic, sandbox Jinja2, quotas IA.

### 4. Déploiement
- Docker Compose : `gateway`, `redis`, `postgres/audit`, `qdrant`, `keycloak`.
- Pipelines CI (GitHub Actions) : tests, lint, build images, scan SAST (Bandit, Trivy).

_Co-auteurs : <votre nom>, achibani@gmail.com_

