# Tester son application

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les tests unitaires ✔️  Un test unitaire est un test unitaire est un test d'une fonction isolée. Il est rapide à executer et il garantie de fonctionnement de l'unité isolée
- 
- les mocks ✔️ Les mocks sont utilisés lors des tests unitaires. Ils permettent de simuler des données d'entrée, ils sont utilisés pour tester le comportement des composants de manière isolée.
- 
- les tests d'integration ✔️ Les tests d'intégration se trouvent à cheval entre les tests unitaires et les tests de bout en bout. Le but des tests d'intégration est de voir si une fois les unités testées et approuvées séparément fonctionnent toujours lorsqu'on les intègre ensemble.
- 
- les tests de bout en bout (end to end) ✔️ Les tests de bout en bout, ou tests fonctionnels permettent de tester notre application en condition réelle. Ce sont des tests qui sont faits par des personnes qui parcourent les fonctionnalités pour voir qu'elles fonctionnent toutes correctement.
- 
- le TDD ✔️ Le Test Driven Development est une méthode de dévelopment où les tests sont écrits avant les fonctions et méthodes. Lorsque nous écrivons en premier les tests, ceux-ci ne passent pas. Le but étant d'avoir le test qui passe au "vert", il faut donc coder pas à pas jusqu'à ce que le test passe.
- 
- les tests par snapshot ✔️ Les tests par snapshot permettent de s'assurer que UI ne change pas soudainement. Un exemple est qu'il fait un snapshot d'un composant qu'il va rendre puis il le compare de référence stocké à côté du test et les deux doivent être identiques. 

## 💻 J'utilise

### Un exemple personnel commenté ❌✔️
```'javascript'
import { render, screen } from "@testing-library/react"; // 
import Login  from "./Login";
import { MockedProvider } from "@apollo/client/testing";
import { BrowserRouter } from "react-router-dom"

describe('Login', () => {
    it.only('renders a button', () => {
        render(
            <BrowserRouter>
                <MockedProvider mocks={[]} addTypename={false}>
                    <Login />
                </MockedProvider>
            </BrowserRouter>
        );
        expect(screen.getByText(/se connecter/i)).toBeInTheDocument();
    });
});
```

### Utilisation dans un projet ❌ / ✔️

[lien github](...)

Description :

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

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
