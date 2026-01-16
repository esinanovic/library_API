# Library REST API – **Node.js, TypeScript, Prisma**


API REST pour la gestion d’une bibliothèque (livres, auteurs, tags), développée en Node.js, TypeScript et Prisma.
Projet backend conçu pour démontrer une **architecture propre et maintenable.**


## Objectif du projet

- Concevoir une API REST claire et cohérente
- Mettre en place une architecture backend scalable
- Gérer des relations complexes avec Prisma ORM
- Appliquer de bonnes pratiques (handlers, PATCH, séparation des responsabilités)

## Fonctionnalités
- Gestion des livres
- Gestion des auteurs
- Gestion des tags


Base de données gérée via Prisma ORM

## STACK TECHNIQUE : 

- Node.js
- TypeScript
- Prisma
- API REST
- npm

## Arborescence du projet
.
├── prisma/                # Schéma Prisma et migrations
├── requestHandlers/       # Handlers des routes API
│   ├── author.ts          # Endpoints liés aux auteurs
│   ├── book.ts            # Endpoints liés aux livres
│   └── tag.ts             # Endpoints liés aux tags
├── src/                   # Code source principal
├── package.json
├── package-lock.json
├── tsconfig.json
└── .gitignore



## API Endpoints

Auteurs
| Méthode | Endpoint              | Description                |
| ------- | --------------------- | -------------------------- |
| GET     | `/authors`            | Récupérer tous les auteurs |
| GET     | `/authors/:author_id` | Récupérer un auteur par ID |
| POST    | `/authors`            | Créer un nouvel auteur     |
| PATCH   | `/authors/:author_id` | Mettre à jour un auteur    |
| DELETE  | `/authors/:author_id` | Supprimer un auteur        |


Books
| Méthode | Endpoint                    | Description                           |
| ------- | --------------------------- | ------------------------------------- |
| GET     | `/books`                    | Récupérer tous les livres             |
| GET     | `/books/:book_id`           | Récupérer un livre par ID             |
| GET     | `/authors/:author_id/books` | Récupérer tous les livres d’un auteur |
| POST    | `/authors/:author_id/books` | Créer un livre pour un auteur         |
| PATCH   | `/books/:book_id`           | Mettre à jour un livre                |
| DELETE  | `/books/:book_id`           | Supprimer un livre                    |


Tags
| Méthode | Endpoint                       | Description                         |
| ------- | ------------------------------ | ----------------------------------- |
| GET     | `/tags`                        | Récupérer tous les tags             |
| GET     | `/tags/:tag_id`                | Récupérer un tag par ID             |
| GET     | `/books/:book_id/tags`         | Récupérer les tags d’un livre       |
| POST    | `/tags`                        | Créer un nouveau tag                |
| POST    | `/books/:book_id/tags/:tag_id` | Associer un tag à un livre          |
| PATCH   | `/tags/:tag_id`                | Mettre à jour un tag                |
| DELETE  | `/tags/:tag_id`                | Supprimer un tag                    |
| DELETE  | `/books/:book_id/tags/:tag_id` | Supprimer l’association tag ↔ livre |


## Points techniques clés : 

Relations One-to-Many (Author → Books)
Relations Many-to-Many (Books ↔ Tags)
Handlers séparés par domaine métier
Utilisation de PATCH pour les mises à jour partielles


## À propos de l’auteur
Emir Sinanovic
Développeur Fullstack

LinkedIn : www.linkedin.com/in/emirsinanovic/
