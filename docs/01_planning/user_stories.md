## User Stories clés

### Administrateur MidPoint
- **US-ADM-01** : En tant qu’admin MidPoint, je veux envoyer une requête de provisionnement `create/update/delete` au gateway et recevoir un statut consolidé pour orchestrer plusieurs cibles simultanées.
- **US-ADM-02** : En tant qu’admin MidPoint, je veux re-exécuter une opération échouée avec un rollback automatique pour garantir la cohérence.

### Ingénieur IAM
- **US-IAM-01** : Je veux définir des règles de calcul d’attributs en YAML (expressions JMESPath/Jinja2) pour générer logins, emails et rôles sans modifier le code.
- **US-IAM-02** : Je veux versionner les configurations et conserver l’historique (audit trail) pour savoir qui a changé quoi et quand.
- **US-IAM-03** : Je veux déclencher une réconciliation périodique pour aligner l’état de MidPoint avec les systèmes cibles.

### Manager sécurité / Approbat eur
- **US-SEC-01** : Je veux un workflow pré-provisionnement configurable (jusqu’à 3 niveaux) pour approuver les accès sensibles.
- **US-SEC-02** : Je veux une application web/mobile simple pour approuver/rejeter avec justification.

### Opérateur Support
- **US-OPS-01** : Je veux consulter un tableau de bord temps réel des opérations, filtrer par système cible et lancer un rollback manuel.
- **US-OPS-02** : Je veux accéder à une recherche vectorielle des logs pour retrouver des incidents similaires.

### Agent IA
- **US-IA-01** : En tant qu’utilisateur avancé, je veux interroger un agent IA pour générer des esquisses de règles ou de connecteurs spécifiques (ex : nouveau SaaS).

### Utilisateur final
- **US-END-01** : Je veux recevoir un email ou notification lorsque mon compte est créé ou modifié pour assurer la traçabilité.

