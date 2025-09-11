# 📑 Business Requirements Document (BRD)

**Projet : Build de connecteurs marketing & data (CM, DB, Adobe, DataHub)**

---

## 1. 🎯 Objectifs du projet

* Standardiser et automatiser la **gestion des campagnes marketing cross-canal**.
* Développer des connecteurs propriétaires pour **Campaign Manager (CM360)** et **base de données interne (DB)**.
* Assurer l’**export des métadonnées et tracking codes** dans des formats adaptés pour Email et Content.
* Mettre en place des **intégrations outbound** vers **Adobe Experience Cloud** et un **DataHub (Horizon)**.
* Garantir une **gouvernance forte des métadonnées marketing** et une meilleure qualité de données.
* Réduire la dépendance aux outils SaaS externes (minimiser le lock-in type Claravine).

---

## 2. 📌 Portée du projet

### Inclus :

* Ingestion automatique des campagnes depuis CM et DB.
* Génération et validation des CIDs selon des **nomenclatures standardisées**.
* Mise en place d’un **workflow de validation (pending → validated → active → archived)**.
* Export des données vers Adobe & Horizon via API/ETL/ELT.
* Gouvernance centralisée : dictionnaire de taxonomies, audit trail, RBAC.
* Interfaces utilisateurs (UI/UX) pour **Media team** et **Content team**.

### Exclus (out of scope, phase ultérieure) :

* Connecteurs supplémentaires (TikTok, Amazon Ads, LinkedIn).
* Mise en place d’un Data Lake ou CDP complet (hors périmètre immédiat).
* Automatisation de reporting avancé (BI/AI).

---

## 3. 👥 Acteurs et parties prenantes

* **Équipes Média** : créent et gèrent les campagnes CM/Facebook.
* **Équipes Content & Email** : configurent les campagnes email, bannières, landing pages.
* **Équipe DataOps** : maintiennent les pipelines de données et intégrations.
* **Équipe Sécurité/Conformité** : garantissent GDPR, IAM/SSO, audit.
* **Architectes IT & Solution** : conçoivent l’architecture technique.
* **Comité de gouvernance data** : valide les taxonomies, les nomenclatures et la qualité.

---

## 4. ✅ Exigences fonctionnelles

1. **Connecteurs Inbound**

   * CM360 : ingestion auto des campagnes live.
   * DB interne : import de référentiels (produits, segments, partenaires).

2. **Génération & validation de CIDs**

   * Règles de nomenclature (soc\_, ema\_, cont\_, pat\_, dis\_, etc.).
   * Détection de doublons et incohérences.

3. **Workflow de gouvernance**

   * Soumission → revue → validation → export.
   * Rôles différenciés (créateur, validateur, administrateur).

4. **Exports / Connecteurs Outbound**

   * Formats Email/Content standardisés.
   * Adobe Experience Cloud : synchronisation tracking & métadonnées.
   * DataHub Horizon : export structuré (CSV/JSON/Parquet).

5. **UI/UX Marketing**

   * Tableau de bord campagne.
   * Alertes sur anomalies (champ manquant, tracking invalide).

---

## 5. ⚙️ Exigences non-fonctionnelles

* **Sécurité** : RBAC, SSO, IAM centralisé, chiffrement TLS/AES-256.
* **Conformité** : GDPR/CCPA (gestion consentement, minimisation des données personnelles).
* **Scalabilité** : traitement de milliers de campagnes actives, millions d’événements.
* **Disponibilité** : SLA 99,9 % uptime, ingestion < 5 minutes après création.
* **Interopérabilité** : ETL/ELT compatible (Airflow, dbt, Talend).
* **Observabilité** : monitoring, logging, alerting centralisé.

---

## 6. ⚠️ Risques identifiés

* **CAPEX/OPEX élevé** par rapport à un SaaS clé-en-main (Claravine).
* **Complexité technique** (APIs évolutives de Google, Facebook, Adobe).
* **Charge de gouvernance** : nécessité d’un comité data actif.
* **Risque de lock-in** si les connecteurs ne sont pas modulaires et API-first.

---

## 7. 📊 KPI de succès

* 95 % des campagnes conformes aux standards (vs < 60 % aujourd’hui).
* Réduction de 50 % du temps de mise en ligne d’une campagne.
* Zéro doublon de CID détecté en production.
* SLA ingestion & export respecté à 99 %.
* Adoption > 80 % par les équipes Marketing & DataOps dans 6 mois.

---

---

Veux-tu que je te prépare aussi une **version en “Solution Design” technique** (diagrammes d’architecture, flux de données, choix technologiques possibles) pour compléter ce BRD, comme dans une grande entreprise ?
