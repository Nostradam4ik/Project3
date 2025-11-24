## Code de la passerelle IAM

Ce dossier accueillera le code source (FastAPI) de la gateway :

- `api/` : routes REST, schémas, auth.
- `rules/` : moteur de règles, parsers, versions.
- `connectors/` : intégrations vers AD/LDAP, SQL, Odoo, GLPI, Keycloak, Firebase.
- `workflow/` : gestion des approbations et transactions.
- `storage/` : couche persistance (SQLModel, Redis, Qdrant).

Un squelette sera généré lors du Sprint 1. Pour l’instant, se référer aux documents `docs/03_architecture`.

