# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- Comment développer en utilisant un système de _livereloading_ (`nodemon` par exemple) ✔️
- La connexion de mon application à une base de données avec et sans ORM/ODM (avec `mongodb` puis `mongoose` par exemple) ❌
- Le développement d'une API REST et GraphQL (avec les packages `express` et `graphql` par exemple) ✔️
- _Bonus : la manipulation des fichiers système avec `fs` et l'utilisation des streams en NodeJS_ ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

```javascript
// this function takes a path to a .md file of the host system and write the HTML version of this file
// the .html file is given back
import fs from "fs";
import marked from "marked";

const convertMDFileToHTML = (pathToMDFile) => {
  // Lire le contenu du fichier Markdown
  const mdContent = fs.readFileSync(pathToMDFile, "utf8");

  // Convertir le contenu Markdown en HTML
  const htmlContent = marked(mdContent);

  // Définir le chemin du fichier HTML
  const pathToHTMLFile = pathToMDFile.replace(/\.md$/, ".html");

  // Écrire le contenu HTML dans un nouveau fichier .html
  fs.writeFileSync(pathToHTMLFile, htmlContent);

  // Retourner le chemin du fichier HTML
  return pathToHTMLFile;
};

// Exemple d'utilisation
const pathToHTMLFile = convertMDFileToHTML("example.md");
console.log(pathToHTMLFile); // Output: 'example.html'
```

### Utilisation dans un projet ✔️

[lien github](https://github.com/WildCodeSchool/2211-wns-neumann-green-gesture)

Description :

### Utilisation en production si applicable❌

[lien du projet](...)

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
