# homotope-media

Vidéos publiques du site [homotope.app](https://homotope.app), hors du dépôt applicatif (T104).

- **Chemins** : `tutos/<tuto>.<langue>.<webm|mp4>` (tutos de la page « Prise en main »),
  `presentation/…` (vidéo de présentation, à venir). Un fichier ici = une entrée `media` du
  manifeste du dépôt applicatif (`public/<dossier>/manifest.json` : taille, SHA-256, révision de
  ce dépôt). Le manifeste est la vérité.
- **Écriture** : par `npm run media:push` du dépôt applicatif seulement (session de rendu), jamais à
  la main. Le site lit ces fichiers à la révision épinglée par le manifeste, via le workflow
  `media-sync` qui les recopie dans le bucket ; aucun code de ce dépôt n'est exécuté.
- **Historique sans valeur** : il peut être remis à zéro (branche orpheline) quand il pèse ; il
  suffit ensuite de relancer `media:push` et `media-sync`.
- **Jamais ici** : un secret, une clé, un master YouTube (`out/tutos-master/`, hors dépôt), un
  fichier de plus de 100 Mo.
