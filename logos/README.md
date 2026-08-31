# Logotype `egonux`

Un chevron suivi de trois barres : le prompt d'un terminal, et le `E` du nom.
Symbole seul, ou posé dans un disque ou un carré.

| Fichier | Usage |
|---|---|
| `egonux-symbole-noir.svg` | le symbole seul, sur fond clair |
| `egonux-symbole-blanc.svg` | le symbole seul, sur fond sombre |
| `egonux-carre-noir.svg` | pastille carrée : favicon, icône d'application, tampon gravé |
| `egonux-carre-blanc.svg` | idem, sur fond sombre |
| `egonux-cercle-noir.svg` | pastille ronde : avatar sur les plateformes qui recadrent en cercle |
| `egonux-cercle-blanc.svg` | idem, sur fond sombre |
| `planche-variantes.png` | la planche d'origine, dont ces fichiers sont vectorisés |

## Le symbole est évidé, pas peint en blanc

Dans les versions carrée et ronde, un seul tracé porte à la fois la pastille
et le symbole, avec `fill-rule="evenodd"` : les barres et le chevron y creusent
des trous. Le symbole prend donc la couleur de ce qu'il y a derrière — une
page rouge, une photo, un thème sombre. Un symbole peint en blanc, lui,
imposerait un fond blanc partout où on le poserait.

Conséquence à connaître avant de graver : sur un fichier de découpe, ce sont
bien deux contours imbriqués, pas une forme et un aplat.

## Couleurs

Noir `#000000` et blanc `#ffffff` purs, pour l'impression et la gravure, où
les gris de la charte se dégraderaient mal. Pour un usage à l'écran, remplacer
le `fill` par `currentColor` : le logo suit alors la couleur du texte
environnant, donc le thème clair ou sombre, sans second fichier.

L'encre `#212121` et le papier `#fafafa` de la charte des sites conviennent
aussi — c'est une seule valeur à changer dans chaque fichier.

## Géométrie

Relevée au pixel sur la planche, dans un repère de 116 x 99 :

- barres du haut et du bas : `x 16`, largeur `100`, hauteur `14`
- barre du milieu : `x 55`, largeur `61`, hauteur `15`
- chevron : bord extérieur par `(0,21) (43,49.5) (0,78)`, bord intérieur par
  `(0,37.5) (20,49.5) (0,61.5)`

Le symbole occupe 66 % de la largeur du carré et 63 % du diamètre du cercle.
