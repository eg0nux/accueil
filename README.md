# egonux.com

Page d'accueil du domaine : les trois projets, et rien d'autre. Un seul
fichier HTML autonome, sans dépendance de construction.

| Chemin | Ce que c'est |
|---|---|
| `public/index.html` | la page entière — structure, charte et bascule de thème |
| `public/fonts/` | JetBrains Mono 400 et 700, auto-hébergées |

## Publication

Un **Worker sans code** qui ne sert que `public/` : `egonux-accueil`, routé sur
`egonux.com/*` (voir `wrangler.jsonc`). Pages aurait fait l'affaire, mais y
brancher un domaine personnalisé passe obligatoirement par le tableau de bord,
alors qu'un Worker déclare sa route dans sa configuration — donc depuis la
ligne de commande.

Publication à la main, quand la page change — ce qui est rare :

```sh
npx wrangler deploy
```

Pas de workflow GitHub Actions ici, délibérément : il aurait fallu y dupliquer
le jeton d'API Cloudflare pour automatiser une page qui bouge deux fois l'an.

## Charte

Reprise de `fablab.egonux.com`, charte Sérigraphie : **JetBrains Mono**,
encre `#1a1613` sur papier crème `#fbf6ec`, safran `#f26b1d` en seconde encre
— toujours en fond, jamais en texte —, crème `#f5eee2` sur `#171311` en thème
sombre. La section de chaque logotype est une étiquette safran pleine, texte
au noir de la page. Les trois logotypes sont traités à l'identique — ni cadre, ni
aplat, ni réaction au survol : rien ne doit hiérarchiser trois pans d'une même
maison. Ils s'alignent par la droite, accolades fermantes sur une verticale,
le bloc restant centré dans la page.

Le thème suit le réglage du système ; la bascule sous les logotypes mémorise
un choix contraire dans le stockage local.

Entre la bascule et le pied de page, un glyphe tiré au sort parmi `{ } / \ # & *`
change toutes les une à deux secondes avec un bref soubresaut — le même
tremblement que le logo de La Traverse au survol, sur fablab.egonux.com. Il est
tramé — un masque en damier de 3 px couvrant 75 % — et épaissi par un contour
plutôt que par une graisse de police supplémentaire, la famille n'étant
auto-hébergée qu'en 400 et 700. Rouge en thème clair, crème en sombre, et
purement décoratif : `aria-hidden`
l'écarte des lecteurs d'écran, et `prefers-reduced-motion` supprime le
tremblement pour qui a demandé moins d'animations.

Le pied de page sépare ses mentions par un croisillon rouge pâli — le motif
des trois autres sites, où il ponctue sans attirer l'oeil.

Le fichier ne porte aucun commentaire, délibérément : la page est publique et
sa source se lit d'un coup d'œil. Les choix sont expliqués ici.

## Domaine

`egonux.com` sert cette page depuis le 2026-08-30 ; `www.egonux.com` y arrive
par une redirection 301 vers l'apex. Un Worker nommé `site`, téléversé le
2026-05-27, servait auparavant une page « Bientôt. » — son rendu est archivé
dans `P:/Egonux/accueil/page-precedente-bientot.html`. Il n'a pas été
supprimé, seulement dépossédé de la route.
