## Plan Partie #2 – Installation & implémentation MidPoint

### Étape 1 – Scripts Docker
- Créer `infrastructure/docker/docker-compose.midpoint.yml` avec services : `midpoint`, `postgres`, `openldap` (Apache DS), `odoo`, `pgapp`.
- Script `scripts/setup_midpoint.ps1` / `.sh` pour `docker compose up -d`, génération certificats, comptes admin.

### Étape 2 – Architecture MidPoint
- Documenter modules (UI, Model, Repo, Task Manager). Captures d’écran stockées dans `media/midpoint`.
- Lister bases supportées (H2, PostgreSQL, MariaDB, Oracle) et modèle repository.

### Étapes 3-12 – Guides pratiques
- **Et3** : Console Apache DS (Apache Directory Studio) – captures fonctions, structure DIT.
- **Et4-5** : Définition source CSV, job d’import (Task `Import from CSV`), config XML stockée dans `infrastructure/midpoint/resources/hr-csv.xml`.
- **Et6-7** : Resource LDAP, connecteur `ConnId LDAP`. Scripts d’export config `midpoint-ninja` (CLI) vers `infrastructure/midpoint/resources/ldap-resource.xml`.
- **Et8-9** : Rôles, policy rules, conditions ABAC (ex. `employeeType = 'Intern'`).
- **Et10-11** : Connecteur Odoo (REST custom) + rôle Agent Commercial CRM.
- **Et12** : Connecteur PostgreSQL, rôle Application Intranet, exécution de la politique globale.

### Artefacts à committer
- Fichiers XML/JSON de ressources et rôles exportés.
- Captures d’écran (références dans README).
- Scripts d’automatisation.

_Co-auteurs : <votre nom>, achibani@gmail.com_

