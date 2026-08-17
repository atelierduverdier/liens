# CLAUDE.md

Ce qui doit être vrai à chaque session sur ce dépôt. Il est minuscule ; ce
fichier l'est aussi.

## Ce que c'est

**Une seule page**, `index.html`, écrite à la main : la page de liens de
l'Atelier du Verdier, servie par GitHub Pages sur **`liens.atelierduverdier.fr`**
(voir `CNAME`). Sept liens, les favicons, l'image de partage.

Pas de générateur, pas de dépendance, pas d'étape de construction. Ce qui est
dans le dépôt est exactement ce qui est servi.

Le dépôt vit dans `~/Projets/site/Site_Liens` — il était rangé sous
`Site_PrintNC/liens-site`, ce qui n'avait plus de sens depuis que le journal
PrintNC n'est plus qu'un des sites de l'atelier.

## Non négociable

### 1. C'est une page PUBLIQUE, et pousser la publie

Il n'y a pas de préproduction : `git push` met en ligne. Toute modification est
donc **tournée vers l'extérieur** — relire avant de pousser, et vérifier le
rendu dans un navigateur, pas seulement le HTML.

### 2. Ne pas y ajouter d'outillage

La tentation sera de la générer, de la templatiser, d'y mettre un framework.
Une page de liens qui change trois fois par an n'en a pas besoin, et chaque
couche ajoutée est une chose de plus à réparer le jour où l'on veut juste
corriger une adresse.

### 3. Les fichiers `verdier-*` viennent du kit, on ne les édite PAS ici

`verdier-jetons.css`, `verdier.js`, `verdier-chapeau.svg`, `verdier-logo.svg` et
`.kit-empreintes.json` sont **posés** par `outils/diffuser_kit.py` du dépôt
`atelierduverdier/site` — la charte commune. Chacun porte un bandeau qui le dit.
Une retouche faite ici sera écrasée au prochain envoi ; le script s'arrête même
en la voyant. Corriger `kit/` là-bas, puis rediffuser.

La page prend les **jetons seuls** (les couleurs), pas `verdier.css` en entier :
elle a sa propre mise en page, une carte centrée, et la charte complète lui
imposerait la sienne.

### 4. Le `CNAME` fait vivre le domaine

Le supprimer ou le modifier casse `liens.atelierduverdier.fr`. Il n'a rien à
faire dans un `.gitignore` ni dans un nettoyage de fichiers « inutiles ».

## Vérifier

```bash
xmllint --noout --html index.html      # la page est-elle bien formée
```

Et ouvrir le fichier dans un navigateur : les favicons et l'`og-image` ne se
voient pas autrement.
