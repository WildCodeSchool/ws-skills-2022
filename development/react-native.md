# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- les différences et points communs entre du code react et du code react native ✔️
- ce que devient et comment est interprêté le code javascript dans une application react native ✔️
- les avantages et inconvénients de react native ✔️
- la différence entre react native et expo ✔️
- les principales briques qui composent react native (core components) ✔️
- comment écrire du style en react native ✔️
- comment est géré le layout en react native ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

```typescript
// Définition des props attendus par le composant
interface Props {
  getFileData: (fileData: ImagePicker.ImagePickerAsset) => void;
}

// Composant ImagePickerElement
export default function ImagePickerElement({ getFileData }: Props) {
  // État local pour stocker l'URI de l'image sélectionnée
  const [image, setImage] = useState<string | null>(null);

  // Fonction pour ouvrir la bibliothèque d'images et permettre à l'utilisateur de choisir une image
  const pickImage = async () => {
    // Pas besoin de demander des permissions pour ouvrir la bibliothèque d'images
    let result = await ImagePicker.launchImageLibraryAsync({
      mediaTypes: ImagePicker.MediaTypeOptions.All,
      allowsEditing: true,
      aspect: [4, 3],
      quality: 1,
    });

    // Si l'utilisateur n'annule pas, on met à jour l'URI de l'image et on envoie les données du fichier
    if (!result.canceled) {
      setImage(result.assets[0].uri);
      getFileData(result.assets[0]);
    }
  };

  // Rendu du composant
  return (
    <View>
      {/* Bouton pour ouvrir la bibliothèque d'images */}
      <TouchableOpacity onPress={pickImage} style={styles.button}>
        <Text style={{ fontWeight: "600", textAlign: "center" }}>{image ? "Changer l'image" : "Ajouter une image"}</Text>
      </TouchableOpacity>
      {/* Affichage de l'image si il y'en a une de sélectionnée */}
      {image && <Image source={{ uri: image }} style={{ width: 200, height: 200, borderRadius: 10 }} />}
    </View>
  );
}

// Styles du composant
const styles = StyleSheet.create({
  button: {
    backgroundColor: "lightgray",
    borderRadius: 5,
    padding: 8,
    borderWidth: 1,
    marginVertical: 15,
  },
});
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
