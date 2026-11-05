# Step 5 — Décorer les enfants

Les événements vécus dans la forêt modifient progressivement le comportement des enfants.

Utilisez le pattern **Decorator** pour ajouter dynamiquement de nouveaux comportements à un enfant sans modifier sa classe initiale.

Un même enfant peut cumuler plusieurs décorations. En revanche, il ne doit recevoir qu'une seule fois chaque type de décoration.

La détection des événements appartient au moteur du jeu. Les décorateurs représentent uniquement leurs conséquences sur l'enfant.

## `FrightenedChild`

### Déclenchement

Un enfant devient `FrightenedChild` lorsqu'il passe à trois cases ou moins de l'ogre.

Cette détection doit respecter les règles de perception définies pour l'événement. La distance utilisée doit être paramétrable.

### Comportement

L'enfant paniqué continue toujours dans la même direction jusqu'à rencontrer un obstacle.

- tant que le déplacement reste possible, il conserve sa direction précédente
- lorsqu'il rencontre un obstacle, il choisit aléatoirement une autre direction possible
- s'il ne peut partir dans aucune direction, il reste immobile

## `TraumatizedChild`

### Déclenchement

Un enfant devient `TraumatizedChild` lorsqu'il tente de se déplacer sur une tombe.

Voir une tombe ne suffit pas. L'enfant doit réellement buter dessus. Son déplacement est alors bloqué et la décoration lui est appliquée.

### Comportement

L'enfant traumatisé est régulièrement tétanisé.

- il reste immobile un tour sur deux
- lorsqu'il peut se déplacer, il conserve le comportement fourni par l'enfant qu'il décore

## `TerrifiedChild`

### Déclenchement

Un enfant devient `TerrifiedChild` lorsqu'il voit un autre enfant se faire boulotter par l'ogre.

Les arbres bloquent la vision. La distance maximale à laquelle l'événement peut être observé doit être paramétrable.

### Comportement

L'enfant terrifié cherche à s'éloigner des autres enfants.

- il observe uniquement les enfants qu'il peut voir
- il choisit une direction augmentant sa distance avec l'enfant visible le plus proche
- s'il ne voit aucun autre enfant, il conserve le comportement fourni par l'enfant qu'il décore
- en cas d'égalité, il conserve également la direction proposée par l'enfant décoré

## `SurvivorChild`

### Déclenchement

Lorsque le nombre d'enfants encore vivants devient inférieur ou égal à un seuil paramétrable, tous les enfants restants deviennent des `SurvivorChild`.

Un survivant peut ensuite recevoir d'autres décorations, comme `TerrifiedChild`, `TraumatizedChild` ou `FrightenedChild`.

### Comportement

Le survivant a appris à fuir l'ogre, mais il ne connaît pas automatiquement sa position.

- il ne réagit que s'il voit réellement l'ogre
- son champ de vision est limité à une distance paramétrable
- les arbres bloquent sa vision
- s'il voit l'ogre, il choisit une direction augmentant la distance qui les sépare
- s'il ne voit pas l'ogre, il conserve le comportement fourni par l'enfant qu'il décore

## Empilement des décorateurs

Les décorateurs doivent pouvoir être empilés autour d'un même enfant. Par exemple :

```text
TerrifiedChild
└── SurvivorChild
    └── FrightenedChild
        └── Child
```

Chaque décorateur peut récupérer la direction proposée par l'élément qu'il décore, puis la conserver, la modifier ou décider d'immobiliser l'enfant.

L'ordre d'empilement a donc une importance. Le décorateur extérieur produit la décision finale. Lorsqu'une nouvelle décoration est appliquée, elle devient le décorateur extérieur.

## Points d'attention

- Les décorateurs ne doivent pas déplacer directement l'enfant
- Ils produisent une décision de déplacement, par exemple au travers d'une méthode `getDirection(...)`
- Le moteur du jeu valide ensuite le déplacement au regard de l'état réel de la forêt
- Un décorateur ne doit pas rechercher lui-même les événements qui provoquent son application
- Un enfant ne doit jamais recevoir deux fois le même type de décoration
- Les décorations déjà obtenues ne disparaissent pas lorsqu'une nouvelle décoration est ajoutée

---

[Retour au sujet principal](README.md)
