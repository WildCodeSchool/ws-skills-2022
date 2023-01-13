# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'état (_state_) pour contrôler l'affichage d'un composant ✔️
- les composants enfants et les _props_ qu'on leur passe ✔️
- le déclenchement d'instructions en fonction des actions de l'utilisateur ✔️
- le déclenchement d'instructions en fonction de l'étape du cycle de vie du composant ou du changement de valeur de ses props ✔️
- l'usage d'un reducer (_useReducer_) pour gérer un état composé dans un composant ❌
- l'état stocké dans un composant avec un _context provider_ et accessible dans ses descendants via `useContext` ❌

## 💻 J'utilise

### Un exemple personnel commenté ✔️

```javascript
// création du composant AddWilder et récupère une fonction dans son props
const AddWilder = ({ onWilderCreated }: IWilderForm) => {
  // le state name gère l'état de l'input
  const [name, setName] = useState < IWilderInput["name"] > "";
  // la state processing gère l'état du bouton en mode disabled
  const [processing, setProcessing] = useState < Boolean > false;

  // la fonction handleSubmit est appelée à la soumission du formulaire en mode asynchrone
  // et prend en paramètre l'event
  const handleSubmit = async (e: FormEvent) => {
    // try va exécuter le code et s'il échoue l'erreur est récupérer dans le catch
    try {
      // empêche le rechargement de la page
      e.preventDefault();
      // passe le bouton en disabled=true
      setProcessing(true);
      // utilisation de la fonction récupérée dans le props et exécution de la requête pour créer un wilder
      // le mot-clé await indique d'attendre le retour de la requête pour continuer le code
      onWilderCreated(await creatWilder({ name }));
      //réinitialisation de la valeur initiale de l'input
      setName("");
      // capture des éventuelle erreur
    } catch (err) {
      console.error(err);
      // quoi qu'il arrive finally exécutera le setProcessing qui repasse le disabled du bouton à false
    } finally {
      setProcessing(false);
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Name:
        <input
          type="text"
          name="name"
          value={name}
          // modification de la valeur de name à chaque changement de la valeur de l'input
          onChange={(e) => setName(e.target.value)}
          required
          // modification de l'input en fonction de la valeur de processing
          disabled={processing ? true : false}
        />
      </label>
      // modification du bouton en fonction de la valeur de processing
      <button type="submit" disabled={processing ? true : false}>
        Submit
      </button>
    </form>
  );
};

export default AddWilder;
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

### Point de blocage ❌

Description: Je n'ai pas encore bien compris le fonctionnement du useEffect

Plan d'action : (à valider par le formateur)

- action 1 : revoir les quêtes de la Wilde et pratiquer ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌
- J'ai fait une [présentation](...) ❌
