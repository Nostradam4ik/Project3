## Fonctionnement de MidPoint & Provisionnement

1. **Architecture logique**
   - UI Admin (Angular) ↔ MidPoint Core (Java, Spring) ↔ Repository (PostgreSQL/MySQL/H2) ↔ Connecteurs ConnId.
   - Objets principaux : `User`, `Role`, `Org`, `Service`, `Resource`, `Task`.
   - Modèle repository : schéma relationnel optimisé pour requêtes XML (Native repository en 4.8+).

2. **Provisionnement**
   - Connecteurs ConnId (OpenICF) pour LDAP/AD, DB, CSV, REST, SCIM; configuration en XML (`resource` objects).
   - Processus : Source (e.g., CSV) → Ingestion (Tasks + Mappings) → Object Synchronization → Connecteurs cibles.
   - Support de `reconciliation`, `live synchronization`, `clockwork` engine orchestrant `projector` & `change execution`.

3. **Règles & mappings**
   - Mappings d’attributs (inbound/outbound) utilisant expressions Groovy, XPath, expressions MidPoint.
   - Support RBAC/ABAC via `RoleType` + `PolicyRules`; conditions sur assignments, `ObjectTemplate`.

4. **Workflow**
   - Basé sur `Activiti` (jusqu’à v4.4) puis `Flowable`. Possibilité de définir processus d’approbation custom.

5. **Audit & logs**
   - Table `m_audit_event`, `m_audit_item`, `m_audit_delta`.
   - Logs applicatifs dans fichiers (Logback) ou Syslog; possible redirection ELK.

6. **Interop Gateway**
   - MidPoint enverra requêtes REST à notre gateway (scénario resource REST/SCIM custom ou `Generic REST Connector`).
   - Notre gateway gérera la transaction multi-cibles, transformations dynamiques et retour JSON consolidé.

_Co-auteurs : <votre nom>, achibani@gmail.com_

