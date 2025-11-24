## Cahier de recette par sprint

### Sprint 0
- **CR-0.1** : Vérifier la complétude des exports RH et cibles (validation manuelle de 10 lignes).
- **CR-0.2** : Contrôler la cohérence de la matrice d’habilitations (roles vs systèmes).

### Sprint 1
- **CR-1.1** : Appeler l’API `/provision` avec payload MidPoint type « create » et vérifier la réponse consolidée.
- **CR-1.2** : Forcer une erreur sur un connecteur mock pour vérifier le rollback et les logs audit.

### Sprint 2
- **CR-2.1** : Scénario complet AD+SQL+Odoo simulé avec workflow pré et post (1 approbateur).
- **CR-2.2** : Validation de la mise à jour du cache d’état pour un compte existant (réconciliation delta).

### Sprint 3
- **CR-3.1** : Éditer une règle via l’UI, déclencher un test de provisionnement, vérifier la mise à jour live.
- **CR-3.2** : Interroger l’agent IA pour générer une règle de calcul d’email et l’appliquer.

### Sprint 4
- **CR-4.1** : Déployer MidPoint+ApacheDS via scripts Docker, synchroniser un CSV RH et provisionner un compte test.
- **CR-4.2** : Exécuter la réconciliation vers Odoo et vérifier les rapports JSON + logs vectoriels.

