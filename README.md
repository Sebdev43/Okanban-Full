# Okanban

## Description du projet

Okanban est une application inspirée de Trello, conçue pour offrir une gestion de projets visuelle et intuitive via des tableaux de type Kanban. L'application permet aux utilisateurs de créer des cartes et de les organiser dans des listes, offrant ainsi une flexibilité maximale pour la gestion des tâches et des projets.

## Fonctionnalités principales

- Gestion des utilisateurs : Enregistrement, connexion et gestion des utilisateurs.
- Gestion des cartes : Création, modification, suppression et réorganisation des cartes dans les listes.
- Gestion des tags : Création, modification et suppression des tags, ainsi que l'association des tags aux cartes.
- Drag and Drop : Déplacement des cartes et des listes via une interface glisser-déposer intuitive.
- Authentification et Sécurité : Utilisation de tokens CSRF pour sécuriser les requêtes, gestion des sessions avec Sequelize.

## Technologies utilisées

### Frontend

![HTML5](https://img.shields.io/badge/-HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/-CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Bulma](https://img.shields.io/badge/-Bulma-00D1B2?style=flat&logo=bulma&logoColor=white)
![FontAwesome](https://img.shields.io/badge/-Font%20Awesome-339AF0?style=flat&logo=font-awesome&logoColor=white)

### Backend

![Node.js](https://img.shields.io/badge/-Node.js-339933?style=flat&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/-Express-000000?style=flat&logo=express&logoColor=white)
![Sequelize](https://img.shields.io/badge/-Sequelize-52B0E7?style=flat&logo=sequelize&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![CSRF Token](https://img.shields.io/badge/-CSRF_Token-000000?style=flat&logo=json-web-tokens&logoColor=white)
![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat&logo=docker&logoColor=white)

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

Pour déployer l'application, Docker Compose est utilisé pour orchestrer les services nécessaires, notamment PostgreSQL pour la base de données et Node.js pour l'application Back.

### Prérequis

- Docker
- Docker Compose

### Configuration

1. Clonez le dépôt :

```bash
git clone https://github.com/Sebdev43/Okanban-Full.git
cd Okanban-Full
```

2. Configuration du backend :

```bash
cd okanban-back
mv .env.example .env
```

3. Lancez Docker Compose pour démarrer les services :

```bash
docker-compose up -d
```

4. Configuration du frontend :

Ouvrez un nouveau terminal, puis exécutez :

```bash
cd okanban-front
npm install
npm start
```

5. L'API sera disponible à l'adresse suivante :

```bash
http://localhost:5000
```

6. Le frontend sera disponible à l'adresse suivante :

```bash
http://localhost:5173
```

7. Arrêt des services

Pour arrêter les services Docker, exécutez :

```bash
docker-compose down
```
