# Task Manager API

API REST de gestion de tâches et d'utilisateurs, avec Node.js, Express et MongoDB.

## Fonctionnalités

- CRUD complet des tâches
- Statut d'une tâche : `en cours` ou `termine`
- Filtres par statut et par date de création
- CRUD des utilisateurs
- Liste des tâches d'un utilisateur
- Réponses JSON et codes HTTP adaptés (201, 400, 404, 500)

## Technologies

- Node.js et Express 4
- MongoDB et Mongoose 8
- body-parser

## Routes

**Tâches**

| Méthode | Route | Rôle |
|---|---|---|
| GET | `/taches` | lister les tâches |
| POST | `/taches` | créer une tâche |
| GET | `/taches/:id` | lire une tâche (avec son utilisateur) |
| PUT | `/taches/:id` | modifier une tâche |
| DELETE | `/taches/:id` | supprimer une tâche |
| GET | `/taches/statut/:statut` | filtrer par statut |
| GET | `/taches/date/:date` | tâches créées à partir d'une date |

**Utilisateurs**

| Méthode | Route | Rôle |
|---|---|---|
| GET | `/utilisateurs` | lister les utilisateurs |
| POST | `/utilisateurs` | créer un utilisateur |
| GET | `/utilisateurs/:id` | lire un utilisateur |
| PUT | `/utilisateurs/:id` | modifier un utilisateur |
| DELETE | `/utilisateurs/:id` | supprimer un utilisateur |
| GET | `/utilisateurs/:id/taches` | tâches d'un utilisateur |

## Modèles

```
Tache        titre (obligatoire), description, statut, dateCreation, utilisateurId
Utilisateur  nom (obligatoire)
```

## Lancer le projet

Prérequis : Node.js 18 ou plus récent et MongoDB en local.

```bash
git clone https://github.com/imene-be/task-manager-api.git
cd task-manager-api
npm install
node server.js
```

Le serveur se connecte à `mongodb://localhost:27017/gestion-de-taches` et écoute sur le port `3000`.

## Exemple

```bash
curl -X POST http://localhost:3000/taches \
  -H "Content-Type: application/json" \
  -d '{"titre": "Écrire le README", "description": "Un bon README"}'
```

---

Réalisé par [Imène Bentifraouine](https://imenebe.fr).
