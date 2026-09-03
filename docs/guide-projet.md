# Guide du projet

Tour de main pour créer un projet, gérer la page studio et déployer le
site. Le schéma des champs d'entête n'est pas repris ici : il vit dans
`archetypes/projet.md`, qui fait référence.

## Créer un projet

```
hugo new content --kind projet work/nom-du-projet/index.md
```

Le drapeau `--kind projet` est nécessaire : sans lui, Hugo retombe sur son
squelette par défaut, sans les champs commentés, faute d'archétype nommé
`work.md` ou `default.md` dans ce dépôt. La commande crée le dossier
`content/work/nom-du-projet/` et le fichier `index.md`, à partir de
`archetypes/projet.md`. Déposer ensuite les images dans le même dossier,
puis passer `draft: false` pour publier.

Les champs de l'entête et leur usage sont documentés dans l'archétype, qui
est le fichier que la commande vient de générer. Il n'y a rien à chercher
ailleurs.

## Retirer un projet de la grille d'accueil

La grille d'accueil est une sélection, pas l'archive complète. Le champ
`accueil` de l'entête décide de la présence d'un projet dans cette grille.

```yaml
accueil: false
```

Sans ce champ, le projet est affiché. C'est le comportement par défaut, et
rien n'est à ajouter dans l'entête d'un projet qui doit rester sur
l'accueil.

Avec `accueil: false`, le projet sort de la grille sans être dépublié. Sa
page reste construite, son adresse ne change pas, elle reste accessible par
lien direct, depuis un partage ou depuis le sitemap. C'est bien un retrait
de la vitrine, pas une suppression. Pour dépublier vraiment un projet, c'est
`draft: true` qu'il faut poser, ce qui est une autre décision.

La grille se lit sur deux colonnes. Viser un nombre pair de projets
affichés, sinon la dernière rangée reste à moitié vide. Retirer un projet en
appelle donc un second, ou un retour à seize.

L'ordre de la grille ne change pas : il reste le tri par `date`, du plus
récent au plus ancien. `accueil` ne fait que retirer, il ne remonte ni ne
descend rien.

Le champ est décrit dans `archetypes/projet.md`, comme tous les autres.

## Conventions de fichiers

Les images d'un projet, dans `content/work/<projet>/`, sont numérotées sur
deux chiffres, `<slug>_01.jpeg` à `<slug>_15.jpeg`, et non `_1` à `_15`.

Hugo trie les page resources en ordre lexicographique, pas en ordre
naturel. Avec une numérotation à un chiffre, `_10` passe avant `_2` et la
galerie s'affiche dans le désordre. Le zéro de tête rétablit l'ordre voulu
sans qu'aucun tri ne soit écrit dans un gabarit.

Le nom `couverture.<ext>` est réservé : c'est lui qui fait reconnaître
l'image comme couverture du projet, et qui l'exclut de la galerie.

Les couvertures sont pré-recadrées en 16:9 depuis les masters, avant
d'être déposées dans le bundle. Toutes les images d'un projet, couverture
comprise, sont issues des masters. Jamais un JPEG recompressé depuis une
exportation déjà compressée.

## Page studio

La page studio est le bundle `content/studio/`.

La clé `fiche` de l'entête de `content/studio/index.md` porte les lignes
affichées dans la colonne de contact, chacune avec un `libelle` et une
`valeur`. Le champ `url` est facultatif : renseigné, il transforme la
valeur en lien.

Les deux réalisateurs viennent de `data/equipe.yaml`. Le fichier ne porte
que les adresses : le texte affiché d'un site est déduit de son adresse,
protocole retiré, et le compte Instagram est saisi sans arobase, le
gabarit posant l'arobase et l'adresse du profil.

Orthographe volontaire : Jeremy Janin sans accent, Grégory Mignard avec.
Les deux graphies sont volontaires, ne pas les uniformiser.

### Le mur de photos de tournage

La clé `galerie` de l'entête de `content/studio/index.md` pilote seule
l'affichage et l'ordre du mur. Rien n'est ramassé automatiquement dans le
dossier.

Chaque entrée porte son texte alternatif :

```yaml
galerie:
  - image: bts-cys_1.webp
    alt: "Ce que montre la photo, en une phrase."
```

Un `alt` absent donne une image décorative, `alt=""`. Une entrée dont le
fichier n'existe pas dans le bundle est ignorée, sans casser la mise en
page. Retirer la clé `galerie`, ou la vider, fait disparaître la section
entière.

## Ajouter une photo de tournage

Deux gestes.

1. Déposer le fichier dans `content/studio/`.
2. Ajouter son entrée à la clé `galerie` de `content/studio/index.md`.

C'est cette liste, et elle seule, qui décide de ce qui s'affiche et dans
quel ordre.

Le dossier mélange aujourd'hui deux conventions de nommage, `bts-cys_N` et
`bts_meneham_N`, numérotées sur un chiffre, et deux gabarits de fichiers.
Le lot `bts-cys_*` est calé à 900 px de large au plus, pour un poids qui
va de 116 à 352 Ko. Le lot `bts_meneham_*` va jusqu'à 1920 px de large,
pour un poids qui va de 527 à 1432 Ko.

Pour tout ajout à venir, tenir la règle du lot `bts-cys_*` : 900 px de
large au plus et 300 Ko par fichier au plus.

Le lot `bts_meneham_*` sort de cette règle et reste à retraiter. Ce n'est
pas fait ici.

## Déployer

Une branche par chantier, une pull request, une validation visuelle sur la
deploy preview Netlify, puis la fusion.

Netlify construit `main` en production avec la commande de `[build]` dans
`netlify.toml`, sans `--buildDrafts`.
