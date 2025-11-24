## Planning des sprints

| Sprint | Durée | Objectifs clés | Livrables |
| --- | --- | --- | --- |
| Sprint 0 – Cadrage | Semaine 1 | Finaliser l’état de l’art, définir la politique IAM cible, préparer les exports RH/systèmes | Rapport état de l’art, exports CSV nettoyés, matrice d’habilitations v1 |
| Sprint 1 – Fondations | Semaines 2-3 | Mettre en place l’API Gateway (squelette FastAPI), moteur de règles dynamique, base en mémoire, pipeline CI minimal | Service gateway v0, module de règles, base audit en mémoire, tests unitaires |
| Sprint 2 – Connecteurs & Workflow | Semaines 4-5 | Ajouter connecteurs AD/LDAP mock, SQL, Odoo (simulateur), workflow d’approbation configurable, cache d’état | Connecteurs mock, orchestrateur workflow (pré/post), documentation API |
| Sprint 3 – Interface & IA | Semaines 6-7 | Construire l’interface web d’édition des règles, intégrer agent IA (LLM) pour suggestions de mapping, logs vectoriels | UI React/Flask, agent IA (OpenAI/DeepSeek), base vectorielle des opérations |
| Sprint 4 – MidPoint & Recette | Semaines 8-9 | Scénarios d’intégration MidPoint, scripts Docker MidPoint+ApacheDS, réconciliation, rapport final, supports marketing | Scripts d’installation, scénarios de recette, présentations, vidéos |

Chaque sprint se conclut par une démo incluant : run des tests, exécution d’un scénario de provisionnement, export du rapport de recette.

