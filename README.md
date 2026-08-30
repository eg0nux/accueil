# egonux.com

Page d'accueil du domaine : les trois projets, et rien d'autre. Un seul
fichier HTML autonome, sans dépendance de construction.

| Chemin | Ce que c'est |
|---|---|
| `public/index.html` | la page entière — structure, charte et bascule de thème |
| `public/fonts/` | JetBrains Mono 400 et 700, auto-hébergées |

## Publication

- Cloudflare Pages : projet `accueil-egonux`, **envoi direct** (pas
  d'intégration Git côté Cloudflare)
- GitHub Actions publie à chaque poussée sur `main`, via les secrets
  `CLOUDFLARE_API_TOKEN` et `CLOUDFLARE_ACCOUNT_ID`
- À la main, au besoin :

```sh
npx wrangler pages deploy public --project-name=accueil-egonux --branch=main
```

## Charte

Reprise de `fablab.egonux.com` : **JetBrains Mono**, encre `#212121` sur
papier `#fafafa`, rouge `#d32f2f` en accent, crème `#f6ece0` sur `#1c1b19` en
thème sombre. Les trois logotypes sont traités à l'identique — ni cadre, ni
aplat, ni réaction au survol : rien ne doit hiérarchiser trois pans d'une même
maison. Ils s'alignent par la droite, accolades fermantes sur une verticale,
le bloc restant centré dans la page.

Le thème suit le réglage du système ; la bascule sous les logotypes mémorise
un choix contraire dans le stockage local.

## Domaine

`www.egonux.com` redirige en 301 vers l'apex. Attention : une route de Worker
sur `egonux.com/*` prime sur Pages — elle doit être retirée avant que le
domaine personnalisé serve cette page.
