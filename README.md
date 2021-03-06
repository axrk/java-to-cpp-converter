# ♨ TP5 Java - Convertisseur Java vers C++
Programme exécutable via la ligne de commande permettant de convertir une classe Java en une classe C++ (sans implémentation de méthodes).

## ✨ Installation
Télécharger le projet ou cloner le dépôt en local.
Il suffit ensuite de l'importer dans IntelliJ ou d'ouvrir un terminal pour l'utiliser.

## 🚀 Utilisation
### Lancement du programme
Un Makefile préconfiguré pour une classe exemple est présent dans le projet, ce qui permet de compiler le code Java, de l'éxécuter et de compiler le fichier .hpp créé ainsi en une seule commande (à lancer depuis l'intérieur du projet Java).
```
make
```

La version manuelle est : 
```
javac fichier1.java [fichier2.java ...]
java -classpath out/production/TP5 main.Main nom_classe_java [nom_classe_C++] [--stdout]
g++ nom_classe_C++.hpp
```

Pour convertir une autre classe que la classe proposée en exemple, il faut : 
- Copier la classe Java dans le projet Java
- Modifier le Makefile pour qu'il prenne en compte la nouvelle classe

Le nom donné à la classe de sortie C++ peut aussi être changée dans le Makefile.

### Options
La seule option disponible est `--stdout` qui permet d'afficher le contenu du fichier C++ créé sur la sortie standard.

## 📝 Détails sur le programme
### Utilité des classes
**Main.java** : analyse les arguments passés en ligne de commande et lance la conversion.<br/>
**Example.java** : classe d'exemple servant à tester la conversion pour divers cas.<br/>
**Fetcher.java** : récupère les informations des attributs, constructeurs et méthodes de la classe Java à convertir (accès, type, type de retour, nom, arguments). Elle effectue également une conversion de types et elle liste les dépendances nécéssaires à ajouter en C++.<br/>
**Writer.java** : écrit le fichier C++ final à partir des informations récupérées par Fetcher.java.<br/>
