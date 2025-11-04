# tdapi

TD API – Gestion des utilisateurs

Une petite API REST développée en Node.js + Express + TypeScript, permettant d’ajouter et de récupérer des utilisateurs.
Le stockage est pour l’instant en mémoire (les données disparaissent quand le serveur redémarre).

🚀 Installation
1️⃣ Cloner le projet
git clone https://github.com/baptistebrill/tdapi.git
cd tdapi

2️⃣ Installer les dépendances
npm install

🧱 Structure du projet
tdapi/
├── src/
│   ├── controllers/
│   │   └── user.controller.ts      # Logique pour ajouter et récupérer les utilisateurs
│   ├── routes/
│   │   └── user.routes.ts          # Routes Express pour /users
│   ├── server.ts                   # Point d’entrée du serveur
│   └── ...
├── package.json
├── tsconfig.json
└── README.md

▶️ Lancer le serveur
En mode développement (avec ts-node)
npm run dev

Ou compiler + exécuter
npm run build
npm start


Le serveur démarre sur :

http://127.0.0.1:4000

📡 Routes disponibles
➕ Ajouter un utilisateur

POST /users

Exemple avec curl :

curl -X POST http://127.0.0.1:4000/users \
     -H "Content-Type: application/json" \
     -d "{\"name\": \"Alice\", \"email\": \"alice@example.com\"}"


Réponse :

{
  "message": "Utilisateur Alice ajouté avec succès !",
  "email": "alice@example.com"
}

📋 Récupérer la liste des utilisateurs

GET /users

Exemple avec curl :

curl -X GET http://127.0.0.1:4000/users


Réponse :

{
  "users": [
    { "name": "Alice", "email": "alice@example.com" }
  ]
}

🧠 Notes

Les utilisateurs sont stockés en mémoire → la liste se vide quand le serveur redémarre.

Tu peux facilement modifier user.controller.ts pour sauvegarder les données dans un fichier JSON ou une base de données.

🛠 Technologies utilisées

Node.js

Express

TypeScript

🧑‍💻 Auteur

Projet réalisé par Baptiste Brill dans le cadre du TD de développement web.
