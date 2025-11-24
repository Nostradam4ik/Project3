## Backlog produit (extrait)

| ID | Epic | User Story | Priorité | Estimation |
| --- | --- | --- | --- | --- |
| EP1 | Fondation Gateway | En tant qu’administrateur MidPoint, je veux exposer une API REST unique pour créer/modifier/supprimer des comptes afin d’orchestrer les cibles hétérogènes. | Must | 13 pts |
| EP1-US1 | | L’API doit valider les requêtes MidPoint via JWT/OAuth2. | Must | 5 pts |
| EP1-US2 | | L’API doit persister chaque opération dans une base en mémoire et permettre un rollback. | Must | 8 pts |
| EP2 | Moteur de règles dynamique | En tant qu’ingénieur IAM, je veux éditer des règles (YAML/JSON) pour calculer logins/emails afin d’éviter de re-déployer l’application. | Must | 8 pts |
| EP3 | Connecteurs multi-cibles | En tant qu’équipe IAM, je veux provisionner AD, SQL, Odoo, GLPI, Keycloak, Firebase via transactions atomiques. | Must | 21 pts |
| EP4 | Workflow & validation | En tant que manager sécurité, je veux un workflow d’approbation pré/post avec N niveaux pour valider les accès critiques. | Should | 13 pts |
| EP5 | UI d’administration | En tant qu’analyste, je veux une interface pour éditer les règles, lancer des tests de provisionnement et consulter l’historique. | Should | 13 pts |
| EP6 | IA Assistée | En tant qu’ingénieur intégration, je veux qu’un agent IA propose des mappings et scripts de connecteurs pour réduire le temps d’adaptation. | Could | 8 pts |
| EP7 | Observabilité & logs vectoriels | En tant qu’auditeur, je veux rechercher les opérations passées via similarité sémantique. | Could | 5 pts |
| EP8 | Intégration MidPoint | En tant que consultant, je veux des scripts d’installation MidPoint/ApacheDS/Odoo et des scénarios de réconciliation automatisés. | Must | 13 pts |

