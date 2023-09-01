# Docker

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la création d'une image docker ✔️
- l'éxécution d'un container ✔️
- l'orchestration de containers avec docker-compose ✔️


## 💻 J'utilise

### Un exemple personnel commenté ✔️

Voici l'exemple d'un docker file d'une IHM codée en Javascript avec la bibliothèque Reactjs.

```'javascript'
FROM node:lts
// spécifie l'image de base à utiliser, ici c'est une image Node.js

RUN mkdir app
// creation d'un répertoire se nommant app
RUN npm install -g npm
// Installation de npm 
WORKDIR /app
// établissement de app comme notre répertoire de travail

COPY public public
COPY package.json ./
COPY tsconfig.json ./
COPY ./.env ./.env
// les lignes COPY permettent de copier nos fichiers (public, package.json, tsconfig.json, .env) de la machine hôte vers le répertoire app vers l'image docker.

RUN npm config set legacy-peer-deps true
// cette commande passe le paramètre legacy-peer-deps à true ce qui fait qu'npm va utiliser des dépendances plus anciennes et plus adaptatives.
RUN npm install 
// celle-ci installe toutes les dépendances se trouvant dans le package.json


COPY src src /app/
// ici on copie le dossier src de notre machine hôte dans notre dossier app de notre image docker

CMD npm start
// et enfin on on spécifie quelle commande à effectuer afin de démarrer notre application nodejs à l'intérieur de notre container Docker
```



### Utilisation dans un projet ✔️

[lien github](https://github.com/WildCodeSchool/2022-11-turing-FindSpots)

Description : Dans ce projet il se trouvent un frontend et un backend, chacun possède leur DockerFile, voir ci-dessus les explications du dockerfile du client. 

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Titre

- https://dockerlabs.collabnix.com/docker/cheatsheet/
- Cheatsheet contenant les commandes les plus utiles de docker

- https://docs.docker.com/
- Documentation officielle de docker.

- https://hub.docker.com/
- Docker hub contenant les images docker officielles. 

## 🚧 Je franchis les obstacles

### Point de blocage ❌ / ✔️

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌ / ✔️
- J'ai fait une [présentation](...) ❌ / ✔️
