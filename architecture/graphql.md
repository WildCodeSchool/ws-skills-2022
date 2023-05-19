# GraphQL

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la différence entre REST et GraphQL ✔️
- les besoins auxquels répond GraphQL ✔️
- la définition d'un schéma
- Query ✔️
- Mutation ✔️
- Subscription ❌

## 💻 J'utilise

### Un exemple personnel commenté ✔️

```graphql

# Schema d'une query pour récupérer un utilisateur à partir d'un id côté client


# On stipule que c'est une (query), on lui donne un nom (ici GetUserById) et on lui donne un paramètre (ici $getUserById) qui est de type (Int) est obligatoire (!)

query GetUserById($getUserById: Int!) {
    # On appelle la fonction getUserById du UserResolver et lui passe le paramètre id avec la valeur de $getUserById.
  getUserById(id: $getUserById) {
    # Ici on demande les champs qu'on veut récupérer
    id
    firstName
    lastName
    email
    password
    role
    subscriptionType
  }
}
# L'utilisation de Codegen facilite la création de tout les type TypeScript pour le schema GraphQL ainsi que les hooks de requêtes et mutations

# Resolver côté server

 # On crée une query pour récupérer un utilisateur à partir d'un id (on précise le type de retour)
  @Query(() => User)
   # On récupère l'id en paramètre de la query et on précise le type de l'id
  async getUserById(@Arg("id", () => Int) id: number): Promise<User> {
    # Ici on utilise le repository de typeorm pour récupérer un utilisateur en bdd avec l'id
    const user = await datasource.getRepository(User).findOne({
      where: { id }, # On précise la condition de recherche
      relations: { friends: true, company: true, createdCompany: true }, # On précise les relations à récupérer
    });

    # Si l'utilisateur n'est pas trouvé on renvoie une erreur
    if (user === null) throw new ApolloError("user not found", "NOT_FOUND");

    return user; # On retourne l'utilisateur trouvé
  }
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
