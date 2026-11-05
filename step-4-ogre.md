# Step 4 — Ajouter l'ogre

Ajoutez un ogre dans la forêt.

À chaque tour :

1. tous les enfants tentent de se déplacer
2. les conséquences de leurs déplacements sont traitées
3. l'ogre observe son environnement et choisit son déplacement
4. l'ogre se déplace et les conséquences de son déplacement sont traitées

L'ogre possède volontairement un comportement simple :

- il regarde vers le nord, l'est, le sud et l'ouest
- il ne voit pas à travers les arbres
- il repère les enfants visibles dans ces quatre directions
- il se dirige vers l'enfant visible le plus proche
- si plusieurs enfants visibles sont à la même distance minimale, l'ogre ne bouge pas
- s'il ne voit aucun enfant, l'ogre ne bouge pas

Lorsqu'il rejoint la case d'un enfant, celui-ci est immédiatement boulotté. Une tombe apparaît sur cette case.

Les tombes ont une durée de vie limitée. Après un nombre paramétrable de tours, elles disparaissent de la forêt. L'ogre peut les traverser, mais elles bloquent les enfants.

L'affichage doit permettre de suivre l'ogre de la même manière qu'un enfant.

---

[Retour au sujet principal](README.md)
