## Méthodologie Partie #1 (TP MidPoint)

1. **Installation Odoo & export RH**
   - Utiliser image Docker officielle (`odoo:17`) + Postgres.
   - Activer module RH, charger données démo.
   - Script Python (`datasets/scripts/export_odoo.py`) pour extraire employés → CSV.
   - Étapes d’épuration : anonymisation partielle, sélection attributs (id, prénom, nom, email pro, département, job, manager, date entrée).

2. **Extraction droits systèmes cibles**
   - Apache DS : utiliser `ldapsearch` pour exporter utilisateurs, groupes, ACL → CSV.
   - Odoo : export utilisateurs + rôles par module (CRM, RH, Facturation).
   - Intranet PostgreSQL : script SQL `COPY (SELECT ...) TO CSV`.
   - VPN : fichier YAML simulant profils.

3. **Matrice d’habilitations**
   - Fusion via Google Sheets (PowerQuery/Sheets query) → colonnes : Identité, Fonction, Système, Ressource, Droit, Mode auth, Canal.

4. **Étude RBAC / ABAC / Mixte**
   - Créer 3 feuilles dédiées avec colonnes spécifiques (Roles, Permissions, Conditions attributaires).
   - Documenter hypothèses (ex : Comptable → accès Facturation + RH lecture).

5. **Conclusion**
   - Critères d’évaluation : flexibilité, traçabilité, facilité d’implémentation MidPoint.
   - Recommandation : modèle hybride (RBAC de base + règles ABAC sur attributs sensibles).

_Co-auteurs : <votre nom>, achibani@gmail.com_

