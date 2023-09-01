# Tester son application

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les tests unitaires ✔️  Un test unitaire est un test unitaire est un test d'une fonction isolée. Il est rapide à executer et il garantie de fonctionnement de l'unité isolée
- 
- les mocks ✔️ Les mocks sont utilisés lors des tests unitaires. Ils permettent de simuler des données d'entrée, ils sont utilisés pour tester le comportement des composants de manière isolée.
- 
- les tests d'integration ✔️ Les tests d'intégration se trouvent à cheval entre les tests unitaires et les tests de bout en bout. Le but des tests d'intégration est de voir si une fois les unités testées et approuvées séparément fonctionnent toujours lorsqu'on les intègre ensemble. C'est un ensemble de tests unitaires.
- 
- les tests de bout en bout (end to end) ✔️ Les tests de bout en bout, ou tests fonctionnels permettent de tester notre application en condition réelle. Ce sont des tests qui sont faits par des personnes qui parcourent les fonctionnalités pour voir qu'elles fonctionnent toutes correctement.
- 
- le TDD ✔️ Le Test Driven Development est une méthode de dévelopment où les tests sont écrits avant les fonctions et méthodes. Lorsque nous écrivons en premier les tests, ceux-ci ne passent pas. Le but étant d'avoir le test qui passe au "vert", il faut donc coder pas à pas jusqu'à ce que le test passe.
- 
- les tests par snapshot ✔️ Les tests par snapshot permettent de s'assurer que UI ne change pas soudainement. Un exemple est qu'il fait un snapshot d'un composant qu'il va rendre puis il le compare de référence stocké à côté du test et les deux doivent être identiques. 

## 💻 J'utilise

### Un exemple personnel commenté ✔️
Ici nous souhaitons tester si notre composant React nous rend bien un élément contenant "se connecter".

Dans le fichier test Login.test.tsx de notre composant :
```'javascript'
import { render, screen } from "@testing-library/react"; // 
import Login  from "./Login";
import { MockedProvider } from "@apollo/client/testing";
import { BrowserRouter } from "react-router-dom"

describe('Login', () => {
    it('renders a button', () => {
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
render permet de déclarer le composant que nous allons tester
screen nous permet de faire des requêtes dans le rendu
getByText nous permet de faire une requête pour voir quel élément contient le text dans la regexp entre parenthèses
toBeIntheDocument est là pour annoncer qu'on souhaite que le text soit dans ce composant

Dans le fichier Login.tsx de notre composant :

```'javascript'
import { useState } from "react";
import { Link, useNavigate } from "react-router-dom";
import { useLazyQuery } from "@apollo/client";
import { LOGIN } from "../services/auth.query";
// import { format } from "path";

function Login() {
    const [form, setForm] = useState({
        email: "",
        password: "",
    });
    const navigate = useNavigate();
    const [error, setError] = useState('')
    const [login, { loading }] = useLazyQuery(LOGIN, {
    onCompleted(data: any) {
        localStorage.setItem("token", data.login.token);
            if (!data.login.success) {
            return setError(data.login.message)
        }
        navigate("/home");
    },
    onError(error: any) {
     setError(error.message);
    },
    });

    const handleSubmit = (e: any) => {
        e.preventDefault();
        login({
            variables: {
                loginInput: {
                    email: form.email,
                    password: form.password,
                },
            },
        });
    };
    const handleChange = (e: any) => {
        console.log(e);
        setForm((form) => ({ ...form, [e.target.name]: e.target.value }));
    };

    return (
    <div>
        <h1>Login</h1>
        <form onSubmit={handleSubmit}>
            <input
                placeholder="email"
                value={form.email}
                name={"email"}
                onChange={handleChange}
            />
            <input
                placeholder="password"
                value={form.password}
                name={"password"}
                onChange={handleChange}
            />
            <button disabled={loading}>Se connecter</button>
            {error && <p>{error}</p>}
        </form>

        <Link to={"/auth/register"}>Pas encore inscrit?</Link>
    </div>
    );
}
```
Dans le composant nous pouvons voir notre bouton avec le texte "Se connecter"

### Utilisation dans un projet ✔️

[lien github](https://github.com/WildCodeSchool/2022-11-turing-FindSpots)

Description :

### Utilisation en production si applicable ✔️

[[lien du projet](...)](https://github.com/WildCodeSchool/2022-11-turing-FindSpots)

Description : Findspot est un cityguide qui permet à l'utilisateur de visiter des villes et leurs points d'intérêts. En tant qu'utilisateur et selon ses droits on peut ajouter des points d'interêts. 

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Titre

- https://jestjs.io/fr/
- Documentation jestjs

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
