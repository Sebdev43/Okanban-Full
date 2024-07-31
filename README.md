# Okanban

## Description du projet

Okanban est une application inspirée de Trello, conçue pour offrir une gestion de projets visuelle et intuitive via des tableaux de type Kanban. L'application permet aux utilisateurs de créer des cartes et de les organiser dans des listes, offrant ainsi une flexibilité maximale pour la gestion des tâches et des projets.

## Fonctionnalités principales

- Création de listes : Les utilisateurs peuvent créer autant de listes qu'ils le souhaitent. Chaque liste dispose d'un nom unique pour faciliter l'organisation.
- Création de cartes : Chaque liste peut contenir plusieurs cartes. Une carte dispose des propriétés suivantes :
  - Titre : Un titre descriptif pour la carte.
  - Position : La position de la carte au sein de la liste, permettant de les ordonner.
  - Couleur (optionnelle) : Une couleur personnalisée pour identifier visuellement les cartes.
  - Labels (optionnels) : Un ou plusieurs labels pour catégoriser les cartes.

## Modèle Logique de Données (MLD)

Le MLD de l'application Okanban est structuré autour de trois entités principales : `List`, `Card`, et `Tag`, avec une table de liaison pour gérer les relations entre les cartes et les labels.

- List

  - `id` : Identifiant unique de la liste.
  - `title` : Titre de la liste.
  - `position` : Position de la liste dans l'ordre d'affichage.
  - `created_at` : Date de création de la liste.
  - `updated_at` : Date de dernière mise à jour de la liste.

- Card

  - `id` : Identifiant unique de la carte.
  - `content` : Contenu de la carte.
  - `position` : Position de la carte dans la liste.
  - `color` : Couleur de la carte.
  - `list_id` : Identifiant de la liste à laquelle appartient la carte.
  - `created_at` : Date de création de la carte.
  - `updated_at` : Date de dernière mise à jour de la carte.

- Tag

  - `id` : Identifiant unique du label.
  - `name` : Nom du label.
  - `color` : Couleur du label.
  - `created_at` : Date de création du label.
  - `updated_at` : Date de dernière mise à jour du label.

- Card_has_tag

  - `id` : Identifiant unique de la liaison.
  - `card_id` : Identifiant de la carte.
  - `tag_id` : Identifiant du label.
  - `created_at` : Date de création de la liaison.
  - `updated_at` : Date de dernière mise à jour de la liaison.

## Configuration et Déploiement

Pour déployer l'application, Docker Compose est utilisé pour orchestrer les services nécessaires, notamment PostgreSQL pour la base de données et Node.js pour l'application.

```bash
docker compose up
```
