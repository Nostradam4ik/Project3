## Architecture des données & modèles

### 1. Modèles principaux
- `ProvisioningRequest` : id, source (`midpoint`), opération, cibles, statut, timestamps.
- `CalculatedAttributes` : par système cible, version des règles utilisées.
- `WorkflowInstance` : niveaux, approbateurs, décisions, horodatages.
- `SystemStateCache` : snapshot des comptes cibles (clé composite system+account).
- `AuditLog` : résumé textuel + embeddings vectoriels.

### 2. Stockage
- **SQLite/SQLModel** pour prototypage (migration vers PostgreSQL possible).
- **Redis** pour cache + files.
- **Qdrant** pour embeddings (dimension 1536, modèle `text-embedding-3-large`).
- **MinIO** pour stockage de configuration versionnée (option Git bare repo).

### 3. Gouvernance config
- Fichier `ruleset.yaml` par policy, signé (hash). Historique via Git + métadonnées (auteur, date, justification).
- API `/rules/:id` permet CRUD avec audit.

### 4. Réconciliation
- Tâches planifiées (APScheduler) qui comparent `SystemStateCache` avec inventaire MidPoint → anomalies (missing, orphan, drift).
- Résultats stockés dans table `ReconciliationReport`.

_Co-auteurs : <votre nom>, achibani@gmail.com_

