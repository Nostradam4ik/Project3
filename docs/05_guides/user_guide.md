## Guide utilisateur (résumé)

1. **Connexion**
   - Accéder à l’URL de l’interface d’administration.
   - S’authentifier via Keycloak (OIDC). Les rôles UI déterminent les sections visibles.

2. **Gestion des règles**
   - Menu « Règles » → sélectionner la politique → modifier champs YAML via éditeur.
   - Utiliser le bouton « Tester » pour simuler un payload MidPoint avant publication.
   - Chaque sauvegarde crée une nouvelle version historisée.

3. **Lancement d’un provisionnement manuel**
   - Menu « Opérations » → cliquer « Nouvelle requête ».
   - Coller le JSON source (MidPoint) ou importer un fichier.
   - Suivre le statut en temps réel; possibilité d’annuler/rollback.

4. **Workflow d’approbation**
   - Approbateurs reçoivent notification (email + mobile).
   - Interface légère affiche les détails, commentaires obligatoires lors d’un rejet.

5. **Audit & recherche**
   - Onglet « Historique » → filtres par système, statut, utilisateur.
   - Bar de recherche sémantique (powered by vecteurs) pour retrouver cas similaires.

6. **Bouton rouge**
   - Accessible aux rôles `OpsAdmin`. Coupe tout nouveau provisioning, seules les opérations de rollback restent possibles.

_Co-auteurs : <votre nom>, achibani@gmail.com_

