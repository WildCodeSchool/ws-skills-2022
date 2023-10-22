# Docker

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la création d'une image docker ✔️
- l'éxécution d'un container ✔️
- l'orchestration de containers avec docker-compose ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

```dockerfile
# création de l'image du client à partir de l'image node:lts-alpine récupérer sur le DockerHub
FROM node:lts-alpine

# création de l'éspace de travail
RUN mkdir /app
WORKDIR /app

# copy des différents fichiers successible de ne pas changer pour optimiser le système de cache de Docker
COPY codegen.yml .
COPY tsconfig.json .
COPY package*.json .
RUN npm i

# copy des dossiers successible de changer
COPY ./src ./src
COPY ./public ./public

# La commande à exécuter au lancement du container
CMD npm start
```

```dockerfile
# création de l'image du server
FROM node:lts-alpine

RUN mkdir /app
WORKDIR /app

COPY .eslintrc.js .
COPY tsconfig.json .
COPY package*.json .
RUN npm i

COPY ./src ./src

CMD npm start
```

```yml
# Les services sont les différents containers à créer.
services:
  # Le container db
  db:
    # à partir d'une image sur le DockerHub
    image: postgres:15-alpine
    # en cas de crash on lui demande de se relancer tout le temps
    restart: always
    # Les variables d'environnement nécessaire à connexion
    environment:
      POSTGRES_PASSWORD: postgres
      PGUSER: postgres
      # Le port sur lequel il sera exposé le premier celui de l'hôte, le second celui du container
    ports:
      - 5432:5432
      # indique au server si la db est bien lancer pour éviter tout problème
    healthcheck:
      test: ["CMD-SHELL", "pg_isready"]
      interval: 10s
      timeout: 5s
      retries: 5

  # Le server
  server:
    # dépend de la db
    depends_on:
      db:
        # attend le retour de la db avant de se lancer
        condition: service_healthy
    # Le container sera créer à partir d'un fichier Dockerfile dans le dossier ./server
    build: ./server
    ports:
      - 5000:5000
      - 4000:4000
    # Le volume permet de synchroniser les changements entre le projet externe et le projet à l'intérieur du container
    volumes:
      - ./server/src:/app/src

  client:
    build: ./client
    ports:
      - 3000:3000
    volumes:
      - ./client/src:/app/src
```

### Utilisation dans un projet ✔️

[lien github](https://github.com/WildCodeSchool/2211-wns-neumann-green-gesture)

Description :

### Utilisation en production si applicable ✔️

[lien du projet](https://neumann2.wns.wilders.dev/)

Description :

### Utilisation en environement professionnel ❌

Description :

## 🌐 J'utilise des ressources

### Titre

- lien
- description

## 🚧 Je franchis les obstacles

### Point de blocage ❌

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌
- J'ai fait une [présentation](...) ❌
