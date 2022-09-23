# Langage Javascript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les `structures` de base du langage ✔️

JavaScript est un langage dont le typage est faible et dynamique: il n'est pas nécessaire de déclarer le type d'une variable avant de l'utiliser. Le type de la variable sera automatiquement déterminé lorsque le programme sera exécuté. De plus la même variable pourra avoir différents types au cours de son existence.

- les normes `ecmascript` ✔️

Ensemble de normes javascript ajoutant des fonctionnalités au langage sans pour autant négliger la compatibilité avec les précédentes versions.
Exemple : initialement seul le mot clé "var" permettait d'initier une variable, mais depuis ES6, des mots différents ont été implémentés pour initier des variables ou des constantes (respectivement "let" et "const")

- l'utilisation de l'`asynchrone` ✔️

Permet d'ajouter la notion de temps à l'execution des fonctions pour palier aux biais de l'exécution synchrone par défaut de javascript.
Par exemple attendre la fin de l'exécution d'un fonction longue pour utiliser son résultat grâce aux mots clés "async" et "await".

- les spécifités du mot-clef `this`  ✔️
"this" est un mot clé faisant référence à l'instance de l'objet utilisé. Notamment utilisé en Programmation Orientée Objet et dans les constructeurs des class component 

## 💻 Je code en Javascript

### Un exemple de code commenté  ✔️

```javascript
// fonction destinée à récupérer un wilder en BDD via typeORM
  readOneById: async (req, res) => {
    try {
        // récupération de la donnée
      const wilder = await datasource.getRepository(Wilder).findOne({
        where: { id: parseInt(req.params.id, 10) },
        relations: { grades: { skill: true } },
      });
      // conditionnement des données
      if (wilder !== null)
        res.send({
          ...wilder,
          grades: undefined,
          skills: wilder?.grades.map((g) => ({
            id: g.skill.id,
            name: g.skill.name,
            vote: g.votes,
          })),
        });
        // traitement de la donnée non trouvée
      else res.status(404).send("Wilder not found");
    } catch (err) {
        // traitement de l'erreur
      console.error(err);
      res.send("error while reading wilder");
    }
  },
```

### Utilisation dans un projet ✔️

[lien github](https://github.com/AxelCabanat/wildbook)

Description : Projet réalisé sur les 2 premières semaines de la formation Développeur Web Avancée

### J'ai utilisé ce langage en production ❌ / ✔️

[lien du projet](...)

Description :

### J'ai utilisé ce langage en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Titre

- lien
- description

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

