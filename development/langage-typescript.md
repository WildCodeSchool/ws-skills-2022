# TypeScript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'intéret de TypeScript dans l'IDE  ✔️
Outre le fait de rajouter une couche de robustesse au code avec son typage statique, l'IntelliSense de VSCode se voit garni de nombreuses détections et explications d'erreurs avec parfois des suggestions de modifications des lignes concernées.

- les types de bases  ✔️
Si des types élaborés existent pour décrie différents évènements, les types de bases couverts par TypeScript sont les suivants:
- Boolean: true or false
- String: chaîne de caractères
- Number: nombre (entier ou décimal)
- Any: n'importe quel type
- Void: ne retourne reading
- Enum: valeurs listées exclusivement
- Array: tableau de valeurs (exemple : tableau de nombre =>    let array: number[] = [0, 1, 2])

- comment et pourquoi étendre une interface ✔️
Dans TypeScript, une interface est une construction qui déclare des normes. Les classes dérivées d'une interface doivent être conformes aux normes imposées par l'interface. Ainsi, une interface étendu pourra rajouter des spécificité à une classe à portée plus large.

- les classes et les decorators ❌ / ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️
```javascript
// Par soucis de lisibilité, les imports ont été négligés
// Interface déterminant les données transmises par la parent
interface WilderProps {
  wilder: IWilder
  loadWildersIntoState: () => void
}

const Wilder = ({ wilder: { id, name, skills = [] }, loadWildersIntoState} : WilderProps) => {
// Mise en place de l'état "en exécution" de type booléen 
  const [processing, setProcessing] = useState<bolean>(false);

// Fonction exécutée au click du bouton "SUPPRIMER"
  const handleClick = async (e:MouseEvent) => {
    
    setProcessing(true)
    try {
      await deleteWilder(id);
      loadWildersIntoState();
    } catch (err) {
      console.log(err)
    } finally {
      setProcessing(false)
    }
    
  }
  // Affichage 
  return (
    <article className={styles.card}>
      <img src={blank_profile} alt='Profile' />
      <Link to={`/wilders/${id}`}><h3>{name[0].toUpperCase() + name.split('').splice(1).join('')}</h3></Link>
      <button onClick={(e) => handleClick(e)} disabled={processing}>SUPPRIMER</button>
      <h4>Wild Skills</h4>
      <ul className={styles.skills}>
        {skills.map((skill, index) => (
          <Skill key={index} name={skill.name} vote={skill.vote} />
        ))}
      </ul>
    </article>
  );
};

export default Wilder;

```
### Utilisation dans un projet ✔️

[lien github](https://github.com/AxelCabanat/wildbook)

Description : Projet réalisé sur les 2 premières semaines de la formation Développeur Web Avancée

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
