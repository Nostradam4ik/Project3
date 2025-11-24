## Infrastructure & automatisation

- `docker/` : docker-compose pour Gateway, MidPoint, Apache DS, Odoo, Keycloak.
  - `docker-compose.midpoint.yml` : stack MidPoint + Postgres + ApacheDS + Odoo + DB Intranet.
- `scripts/` : scripts PowerShell/Bash (`setup_midpoint.ps1` / `.sh`) pour lancer/arrêter l’environnement.
- `iac/` : manifests Terraform/Ansible (optionnels) pour déployer l’environnement démo multi-VM.

Livrables attendus :
1. Script d’installation MidPoint + Apache DS via Docker (Partie 2 Étape 1).
2. Documentation architecture MidPoint (Étape 2) avec captures (stockées dans `media/`).
3. Scripts/configs pour synchronisation CSV, connecteurs LDAP/Odoo/PostgreSQL.

