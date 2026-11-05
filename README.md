# Ogre Boulotteur

## Présentation

L'objectif de ce TP est de réaliser en **Java** un programme dans lequel un ogre chasse des enfants au sein d'une forêt.

Le projet sera développé progressivement. Chaque étape introduit de nouveaux besoins et doit conduire à faire évoluer l'architecture sans remettre en cause tout le travail précédent.

Le programme doit respecter le modèle **MVC** et utiliser **Maven**. L'affichage sera réalisé avec la bibliothèque `com.jad.textwindow`.

## Organisation du TP

Le sujet est découpé en cinq étapes :

1. [Step 1 — Générer la forêt](step-1-generation-foret.md)
2. [Step 2 — Afficher la forêt avec des sprites](step-2-affichage-sprites.md)
3. [Step 3 — Ajouter les enfants](step-3-enfants.md)
4. [Step 4 — Ajouter l'ogre](step-4-ogre.md)
5. [Step 5 — Décorer les enfants](step-5-decorator.md)

## Règles générales

- La forêt est constituée de cases pouvant contenir du décor, notamment des arbres
- Les arbres sont infranchissables
- Les enfants et l'ogre se déplacent uniquement vers le nord, l'est, le sud ou l'ouest
- Deux enfants ne peuvent pas occuper la même case
- Lorsqu'un ogre rejoint la case d'un enfant, celui-ci est boulotté
- Une tombe apparaît alors sur la case où l'enfant a été boulotté
- L'ogre peut traverser les tombes
- Les enfants ne peuvent pas traverser les tombes
- Une tombe disparaît automatiquement après un nombre paramétrable de tours
- À chaque tour, tous les enfants jouent d'abord, puis l'ogre joue

Les paramètres du programme ne doivent pas être dispersés dans le code. La taille de la forêt, le nombre d'enfants, la durée de présence des tombes, les distances de perception et les autres valeurs similaires doivent pouvoir être configurés facilement.

## Contraintes techniques

- Le projet doit être développé en **Java**
- Le projet doit utiliser **Maven**
- Le modèle **MVC** doit être respecté
- Les responsabilités du modèle, de la vue et du contrôleur doivent être clairement séparées
- La génération des éléments de la forêt doit utiliser une **Factory**
- Les algorithmes initiaux de déplacement doivent utiliser le pattern **Strategy**
- Les transformations successives du comportement des enfants doivent utiliser le pattern **Decorator**
- L'affichage doit utiliser la bibliothèque `com.jad.textwindow`
- Les valeurs configurables ne doivent pas être dispersées sous forme de constantes magiques dans le code
- Le code doit être versionné avec Git et publié dans le dépôt prévu pour le TP
