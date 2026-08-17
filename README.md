# liens.atelierduverdier.fr

La page de liens de l'Atelier du Verdier : **une seule page**, écrite à la
main, servie par GitHub Pages sur <https://liens.atelierduverdier.fr>.

Le dépôt *est* le site. `index.html`, les favicons, l'image de partage, le
`CNAME`, la charte posée par le kit — rien d'autre. Pas de générateur, pas de
dépendance, pas d'étape de construction : ce qui est ici est exactement ce qui
est servi.

Sept liens : le site de l'atelier, le journal de la PrintNC, LaserAtelier,
Instagram, YouTube, le dépôt de la config PrintNC, Ko-fi.

## La charte

Les couleurs, la bascule de thème et le chapeau viennent du **kit commun**, dans
le dépôt [`site`](https://github.com/atelierduverdier/site) : `verdier-*.css`,
`verdier.js`, `verdier-chapeau.svg`, `verdier-logo.svg` sont **posés ici** par
son `outils/diffuser_kit.py`, avec un bandeau « engendré, ne pas éditer ici ».

Cette page prend les **jetons seuls** — elle garde sa mise en page, une carte
centrée. Le thème choisi part dans un cookie de domaine, donc il suit le
visiteur sur `atelierduverdier.fr` et `laser.atelierduverdier.fr`.

## Modifier

Éditer `index.html`, vérifier dans un navigateur, pousser.

```bash
xmllint --noout --html index.html
```

**`git push` publie.** Il n'y a pas de préproduction — relire avant.

## Deux choses à ne pas faire

**Ne pas l'outiller.** La tentation sera de la générer, de la templatiser, d'y
mettre un cadriciel. Une page qui change trois fois par an n'en a pas besoin,
et chaque couche ajoutée est une chose de plus à réparer le jour où l'on veut
juste corriger une adresse.

**Ne pas toucher au `CNAME`.** Le supprimer casse le domaine. Il n'a rien à
faire dans un `.gitignore` ni dans un nettoyage de fichiers « inutiles ».

## Compteur

GoatCounter, sans cookie ni tiers publicitaire, sur le compte commun à tout le
domaine. Les chemins sont préfixés par `/liens` : `count.js` envoie le chemin
et **jamais le nom d'hôte**, donc sans préfixe le « / » de cette page et celui
du journal PrintNC tomberaient dans le même seau.
