# TypeScript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'intéret de TypeScript dans l'IDE ✔️
- les types de bases ✔️
- comment et pourquoi étendre une interface ✔️
- les classes et les decorators ❌

## 💻 J'utilise

### Un exemple personnel commenté ✔️

```typescript
export default function ({ groups }: { groups: Group[] }): GroupWithSills[] {
  // déclaration d'un tableau vide qui ne peut contenir que des tableau de GroupWithSills
  const array: GroupWithSills[] = [];

  // première boucle sur groups pour récupérer chaque group
  for (let i = 0; i < groups.length; i++) {
    // et création d'un tableau vide qui contiendra des tableaux de string
    const arr: string[] = [];

    //deuxième boucle pour récupérer chaque student
    for (let j = 0; j < groups[i].students.length; j++) {
      // ajout dans le tableau arr de tout le contenu des skills de chaque student
      arr.push(...groups[i].students[j].skills);
    }
    // ajout au tableau array de l'objet avec une nouvelle clé skills
    // contenant toute les skills des students appartenant au groupe en enlèvent les double et trier par ordre alphabétique
    array.push({
      skills: [...new Set(arr.sort())],
      name: groups[i].name,
      students: groups[i].students,
    });
  }
  return array;
}
```

### Utilisation dans un projet ❌

[lien github](...)

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

### Point de blocage ✔️

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌
- J'ai fait une [présentation](...) ❌
