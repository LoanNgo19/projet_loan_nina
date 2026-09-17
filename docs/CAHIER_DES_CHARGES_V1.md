# Cahier des charges - VoyagePlanner V1

## 1. Présentation du projet

VoyagePlanner est une application web et mobile qui centralise la préparation et le suivi des voyages de vacances. Elle permet à un utilisateur de regrouper dans un même espace son voyage, son budget, ses réservations, ses documents, ses activités et sa checklist de départ.

## 2. Objectifs de la V1

- Créer et gérer un ou plusieurs voyages.
- Visualiser rapidement les informations principales d’un voyage.
- Définir un budget et suivre les dépenses.
- Enregistrer les réservations et les documents associés.
- Planifier les activités et les tâches avant le départ.
- Disposer d’une interface utilisable sur ordinateur et mobile.

## 3. Périmètre fonctionnel

### 3.1 Authentification

L’utilisateur doit pouvoir :

- créer un compte ;
- se connecter et se déconnecter ;
- accéder uniquement à ses propres voyages et données.

### 3.2 Gestion des voyages

L’utilisateur doit pouvoir :

- créer un voyage ;
- renseigner son nom, sa destination, ses dates et son type de séjour ;
- modifier les informations du voyage ;
- supprimer un voyage ;
- définir le statut : en préparation, en cours ou terminé ;
- gérer plusieurs destinations dans un même voyage ;
- consulter la liste de ses voyages.

### 3.3 Tableau de bord et recherche

Le tableau de bord doit afficher :

- les voyages en cours et à venir ;
- les dates et destinations principales ;
- le budget consommé et le montant restant ;
- les prochaines activités ou tâches à réaliser.

L’utilisateur doit pouvoir rechercher et filtrer ses voyages par nom, destination ou statut.

### 3.4 Budget et dépenses

L’utilisateur doit pouvoir :

- définir un budget total pour un voyage ;
- ajouter une dépense avec un montant, une catégorie, une date et une note facultative ;
- utiliser les catégories transport, hébergement, restauration et loisirs ;
- modifier ou supprimer une dépense ;
- consulter le total dépensé ;
- consulter le montant restant.

Le montant restant est calculé ainsi :

**Budget restant = Budget total - Total des dépenses**

### 3.5 Réservations et documents

L’utilisateur doit pouvoir :

- ajouter une réservation de transport, d’hébergement ou de location de voiture ;
- renseigner le prestataire, les dates, le numéro de réservation et une note ;
- associer un document ou une confirmation à une réservation ;
- enregistrer un document avec un nom, un type et une date ;
- consulter et supprimer ses documents.

Les types de documents prévus sont : pièce d’identité, billet, assurance, visa ou note personnelle.

### 3.6 Activités et checklist

L’utilisateur doit pouvoir :

- ajouter une activité avec un titre, un lieu, une date et une description ;
- consulter les activités dans l’ordre chronologique ;
- ajouter une tâche à la checklist ;
- marquer une tâche comme terminée ;
- modifier ou supprimer une tâche.

La checklist V1 peut contenir notamment les vérifications des bagages, documents et réservations.

## 4. Fonctionnalités hors périmètre V1

Les fonctionnalités suivantes sont reportées après la V1 :

- partage d’un voyage avec plusieurs utilisateurs ;
- synchronisation avec un calendrier externe ;
- notifications avancées ;
- suggestions automatiques de destinations ;
- export PDF ;
- journal de voyage avec photos et souvenirs ;
- intégrations avec des plateformes de réservation.

## 5. Utilisateurs et rôles

### Utilisateur standard

Il peut créer, consulter, modifier et supprimer ses voyages ainsi que les données associées.

### Gestionnaire de voyage

Dans la V1, ce rôle dispose des mêmes droits fonctionnels que l’utilisateur standard. La gestion collaborative pourra être ajoutée dans une version ultérieure.

### Administrateur

Le rôle administrateur est hors périmètre de la V1, sauf besoin technique pour administrer les comptes et les données.

## 6. Règles métier principales

- Un voyage appartient à un seul utilisateur dans la V1.
- Un voyage doit avoir un nom, une destination et une date de départ.
- La date de retour ne peut pas être antérieure à la date de départ.
- Le montant d’une dépense doit être supérieur à zéro.
- Une dépense est obligatoirement rattachée à un voyage.
- La suppression d’un voyage supprime ou archive ses données associées selon le choix technique retenu.
- Les données d’un utilisateur ne doivent pas être visibles par un autre utilisateur.

## 7. Écrans attendus

1. Page de connexion et de création de compte.
2. Tableau de bord.
3. Liste des voyages.
4. Formulaire de création et de modification d’un voyage.
5. Détail d’un voyage.
6. Onglet budget et dépenses.
7. Onglet réservations et documents.
8. Onglet activités et checklist.

## 8. Exigences non fonctionnelles

- Interface claire et responsive sur ordinateur, tablette et mobile.
- Navigation simple avec des temps de réponse courts.
- Validation des formulaires et messages d’erreur compréhensibles.
- Protection des données personnelles et contrôle d’accès par utilisateur.
- Sauvegarde persistante des données.
- Compatibilité avec les navigateurs récents.
- Code organisé pour permettre l’ajout ultérieur du partage et des notifications.

## 9. Orientation technique

La stack sera confirmée lors de la phase d’architecture. L’orientation proposée est :

- frontend : React ou Next.js ;
- backend : Node.js / Express ou API intégrée Next.js ;
- base de données : PostgreSQL ;
- authentification : Firebase ou JWT ;
- stockage des documents : stockage cloud sécurisé.

## 10. Critères d’acceptation de la V1

La V1 est considérée comme acceptable lorsque :

- un utilisateur peut créer un compte et se connecter ;
- il peut créer, modifier et supprimer un voyage ;
- il peut ajouter des dépenses et voir le budget restant calculé ;
- il peut enregistrer une réservation et un document ;
- il peut ajouter une activité et gérer sa checklist ;
- ses données restent accessibles après reconnexion ;
- les parcours principaux fonctionnent sur ordinateur et mobile ;
- les erreurs principales sont signalées clairement ;
- aucun utilisateur ne peut consulter les données d’un autre utilisateur.

## 11. Priorisation du backlog

| Priorité | Fonctionnalité |
|---|---|
| Must have | Authentification |
| Must have | Création et gestion des voyages |
| Must have | Tableau de bord |
| Must have | Budget et dépenses |
| Must have | Réservations |
| Must have | Documents |
| Must have | Activités et checklist |
| Should have | Recherche et filtres |
| Should have | Gestion de plusieurs destinations |
| Could have | Notes personnelles avancées |
| Hors V1 | Partage, notifications avancées, export PDF et journal photo |