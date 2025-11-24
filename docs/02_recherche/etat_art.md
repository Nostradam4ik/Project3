## Rapport d’état de l’art — IGA & MidPoint

### 1. Modèles de contrôle d’accès
- **RBAC (Role-Based Access Control)** : attribution d’autorisations via des rôles pré-définis; simple à gouverner mais rigide pour des contextes dynamiques.
- **ABAC (Attribute-Based Access Control)** : décisions basées sur attributs (identité, ressource, contexte). Flexible mais nécessite gouvernance des règles.
- **MLS (Multi-Level Security)** : hiérarchisation stricte (niveaux/classifications) avec compartimentation; adapté aux environnements sensibles défense.

### 2. IAM vs IGA
- **IAM** se concentre sur l’authentification, l’autorisation et le provisioning opérationnel.
- **IGA** ajoute la gouvernance : campagnes de revue, SoD, certification des accès, reporting conformité.
- **Panorama marché (2024)** :
  - France : Evidian IGA, Atos DirX, Ilex Sign&go.
  - Europe : Evolveum MidPoint (open-source), Omada Identity, OneIdentity IGA.
  - Monde : SailPoint, Saviynt, Okta Identity Governance.
  - Sources : Gartner MQ 2023, KuppingerCole Leadership Compass 2024 (à citer dans version finale).

### 3. Fiche MidPoint
- **Fonctions clés** : provisioning multi-systèmes via connecteurs ConnId, modèles d’objets (Users, Roles, Orgs, Services), workflows, SoD, reporting.
- **Forces** : open-source, extensible, support RBAC/ABAC, scripting Groovy, connecteurs standards (LDAP, AD, DB, REST, SCIM).
- **Limites** : interface moins moderne, nécessite expertise pour connecteurs avancés.
- **Usage projet** : MidPoint servira de source orchestratrice; notre gateway agit comme connecteur intelligent adaptatif (ajout IA, règles dynamiques côté gateway).

_Co-auteurs : <votre nom>, achibani@gmail.com_

