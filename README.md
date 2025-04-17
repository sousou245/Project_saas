# TP - SaaS de gestion de projet

## Contexte du projet

### Présentation générale

Le produit est une **plateforme SaaS de gestion de projets**, destinée à :

- Des étudiants qui réalisent des travaux pratiques en groupe (TP, projets longs).
- Des petites équipes souhaitant un espace collaboratif en ligne pour gérer leurs tâches, suivre l’avancement et échanger des fichiers.

### Objectifs du SaaS

1. **Permettre la création et la gestion de projets** (possibilité de créer plusieurs projets, d’ajouter des membres, des tâches, etc.).
2. **Gérer les rôles et autorisations** : administrateur, chef de projet, contributeur.
3. **[BONUS] Proposer une facturation**.
4. **Offrir un système de logs d’audit** pour tracer les actions.
5. **Faciliter la collaboration** (commentaires sur les tâches, statut de tâches).

---

## Périmètre fonctionnel

### Gestion des utilisateurs et rôles

- **Rôles distincts** :
  - **Administrateur** : gère l’ensemble de la plateforme (utilisateurs, paiements, configuration).
  - **Chef de projet** : crée des projets, gère les membres du projet, assigne les tâches.
  - **Contributeur** : participe à un projet, crée/édite des tâches, commente.
- **Cycle de vie d’un utilisateur** :
  - Inscription (formulaire).
  - Authentification (JWT ou session).
  - Accès à une interface selon son rôle (tableau de bord, projets auxquels il appartient, etc.).

### [BONUS] Gestion des abonnements et paiements

- **Plan d’abonnement** **payant** : uniquement pour le chef de projet.
- **Système de paiement** : intégration de l’API Stripe en sandbox pour le développement.

### Création et gestion de projets

- **Projets** : chaque projet contient un ensemble de tâches, de membres et un état d’avancement.
- **Tableaux de tâches** : statut des tâches (à faire, en cours, terminé, etc.).
- **Attribution des rôles au sein du projet** (Chef de projet, Contributeur).
- **Commentaires** : ajout de commentaires sur une tâche.
- **[BONUS] Fonctionnalités avancées** :
  - Dates d’échéance, priorités, étiquettes (tags).
  - Fichiers attachés (photos, PDF).
  - Commentaires.

### Historisation et logs d’audit

- **Actions loggées** :
  - Création/suppression d’un projet, ajout/suppression de membres.
  - Création/suppression/modification d’une tâche.
  - [BONUS] Paiements, changements de plan d’abonnement.
- **Stockage et consultation** :
  - Logs consultables dans une interface d’administration.
  - Possibilité de filtrer par date et utilisateur.

### Administration de la plateforme

- **Tableau de bord** : statistiques globales (nombre de chefs de projet, nombre d’utilisateurs, nombres de projets).
- **Gestion des utilisateurs** : création/suspension de comptes, réinitialisation de mots de passe.

---

## Exigences techniques

### Architecture et stack technologique

- **Backend** : Node.js (Express).
- **Base de données** :
  - **SQL** (MySQL)
- **Frontend** : HTML/CSS/Js.
- **[BONUS] API de paiement** : Stripe (sandbox).
- **Authentification** : JWT ou sessions gérées par Passport.js (Node) ou le système d’auth Django.
- **Déploiement** : Heroku, Railway, Render, AWS, Tiiny.host ou _Vercel_.

### Sécurité

- **Gestion stricte des rôles** : contrôles d’accès dans le backend pour éviter qu’un user normal puisse accéder aux fonctions Admin.
- **Stockage des mots de passe** : hachage (bcrypt ou autre).
- **[BONUS] Protection** : contre les injections SQL, XSS, CSRF.
- **[BONUS] Certificat SSL** pour sécuriser les échanges (idéalement).

### Journalisation et logs

- **Stockage dédié** (table SQL).

---

## Installation

1. Clonez ce repository :
   ```bash
   git clone [https://github.com/marc-awad/project-manager-saas.git](https://github.com/sousou245/Project_saas/blob/main/project-manager-saas-main.zip)
   ```
2. Installez les dépendances :
   ```bash
   npm install
   ```
3. Configurez votre base de données et variables d’environnement (voir `.env`).
   ```SQL
   CREATE DATABASE project_db;
   ```
4. Lancez le serveur :
   ```bash
   node .\backend\src\server.js
   ```

---

## Contribution

Les contributions sont les bienvenues ! Pour contribuer, suivez ces étapes :

1. Fork ce repository.
2. Créez une nouvelle branche (`git checkout -b feature-branch`).
3. Commitez vos changements (`git commit -am 'Ajout de nouvelle fonctionnalité'`).
4. Poussez la branche (`git push origin feature-branch`).
5. Ouvrez une Pull Request.

---

## Équipe de développement

Ce projet est développé par l'équipe suivante :

- Adrien 📏
- Marc 😎
- Martin 📈
- Soualiho 🏀
