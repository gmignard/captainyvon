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

Sous la dernière rangée de la grille, une phrase et un bouton renvoient
vers les fragments. Ils viennent du bloc `suite` de l'entête de
`content/_index.md`. Retirer ce bloc retire la phrase et le bouton, sans
toucher à aucun gabarit.

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

## La page Fragments

La page `/fragments/` est le bundle `content/fragments/`. C'est un mur de
visuels prélevés dans nos travaux, photos et boucles vidéo muettes mêlées.
Rien n'y est cliquable et rien ne renvoie vers une fiche projet.

Déposer les fichiers à la racine de `content/fragments/`. Il n'y a aucune
liste à tenir dans l'entête pour l'affichage. Déposer un fichier suffit à le
publier, et l'ordre du mur est celui des noms de fichiers.

Le squelette de l'entête vit dans `archetypes/fragments.md`, comme celui
d'un projet vit dans `archetypes/projet.md`. La page existe déjà, il n'y a
donc rien à générer, mais c'est là que le détail des champs est décrit.

### La numérotation

Quatre chiffres, avec un pas de 2.

```
0102.jpg
0104_16x9.mp4
0106.jpg
```

Le pas de 2 laisse une place libre entre deux visuels. Insérer une image
entre `0104` et `0106` se fait en la nommant `0105`, sans renommer tout le
dossier derrière elle.

### Une photo

Un fichier image seul, `0102.jpg`. Rien d'autre à faire. Hugo lit ses
dimensions et en déduit sa place dans la grille.

### Une boucle vidéo

Deux fichiers obligatoires, et ils vont toujours par paire.

```
0104_16x9.mp4     la boucle
0104_16x9.jpg     son image d'affiche
```

Le suffixe de ratio est obligatoire sur le MP4, et sur lui seul. Hugo sait
lire les dimensions d'une image, jamais celles d'une vidéo. Sans ce suffixe
la tuile n'aurait pas de hauteur avant l'arrivée du fichier, et la page se
décalerait au chargement. Sept valeurs sont acceptées.

`16x9`, `9x16`, `4x3`, `3x4`, `3x2`, `2x3`, `1x1`

L'image d'affiche porte exactement le même nom que le MP4, extension mise à
part. Elle est ce que voient les visiteurs avant que la boucle démarre, et
elle est le rendu complet de la tuile quand le JavaScript est désactivé.

Une boucle sans image d'affiche s'affiche quand même, à sa bonne dimension,
et le build le signale par un avertissement nommant le fichier. Mais sa
tuile reste un aplat vide pour les visiteurs qui ont demandé la réduction
des animations dans leur système : chez eux aucune boucle n'est jamais
chargée, et l'image d'affiche est le seul contenu qu'ils verraient. C'est
pour cette raison que la commande ci-dessous n'est pas facultative.

Un MP4 sans suffixe de ratio exploitable est le seul cas qui reste écarté du
rendu. Sans ratio la tuile n'a pas de hauteur, et l'afficher casserait la
rangée entière.

### Mettre les boucles en conformité

Le flux réel est celui-ci. Le studio dépose ses exports bruts dans
`content/fragments/`, sans se soucier du poids ni de l'image d'affiche. Une
passe Claude Code les met en conformité. Le studio ne renseigne ensuite que
les légendes.

La commande de mise en conformité traite tout le dossier en une passe, elle
fait l'encodage et l'extraction de l'image d'affiche pour chaque boucle.

```bash
cd content/fragments
for f in *.mp4; do
  ffmpeg -y -i "$f" -an \
    -vf "scale=w=1280:h=1280:force_original_aspect_ratio=decrease:force_divisible_by=2" \
    -c:v libx264 -profile:v high -pix_fmt yuv420p \
    -crf 28 -preset slow -movflags +faststart -map_metadata -1 \
    "tmp_$f" && mv "tmp_$f" "$f"
  ffmpeg -y -i "$f" -frames:v 1 -q:v 3 "${f%.mp4}.jpg"
done
```

Le plafond de 1280 porte sur le plus grand côté et non sur la largeur, pour
qu'une boucle verticale ne finisse pas démesurément haute.

`-an` supprime la piste audio. Les boucles sont muettes, le son ne serait
jamais joué et pèserait pour rien.

`-movflags +faststart` place les métadonnées en tête du fichier. Sans lui, la
lecture progressive attend le téléchargement complet du MP4 avant de
démarrer.

`-map_metadata -1` retire les métadonnées de caméra et de montage.

La seconde commande extrait la première image du MP4 encodé, et pas une
image du milieu. C'est celle que le spectateur voit juste avant le démarrage
de la boucle, elle doit raccorder. La prendre dans le fichier final, et non
dans le master, garantit qu'elle a exactement les dimensions et le cadrage
de la boucle.

Viser 300 à 700 Ko par boucle. Au-delà de 1 Mo, c'est la durée qu'il faut
regarder avant la qualité : une boucle de vingt secondes pèsera toujours
plus qu'une boucle de quatre.

### Les légendes

Elles sont saisies dans l'entête de `content/fragments/index.md`, sous la
clé `resources`. C'est le même mécanisme que les textes alternatifs de la
galerie d'une fiche projet.

```yaml
resources:
  - src: "0104_16x9.mp4"
    title: "Ponçage d'une planche de surf dans un atelier."
    params:
      projet: "Tides of Time"
      client: "Captain Yvon Originals"
      annee: 2025
```

`title` est le texte alternatif d'une photo, ou le nom accessible d'une
boucle. `projet`, `client` et `annee` forment la légende affichée au survol,
en deux lignes. Un champ absent ne laisse ni virgule ni point médian
orphelin, et une entrée sans aucun des trois ne produit aucune légende.

Un fichier sans entrée reste affiché. Il est simplement traité comme
décoratif, sans texte alternatif et sans légende.

Sur un écran tactile, où le survol n'existe pas, un lien en tête de mur
affiche toutes les légendes d'un coup.

### La densité du mur

Le mur est une grille justifiée. Le gabarit accumule les proportions des
visuels et ferme une rangée quand leur somme approche un seuil, réglé par
`params.fragments.densite` dans `hugo.toml`, à 4.5 par défaut. Devant chaque
visuel il compare deux possibilités, fermer avant lui ou le faire entrer, et
retient celle qui tombe le plus près du seuil.

Monter la valeur met plus de visuels par rangée, donc des rangées plus
basses. La descendre fait l'inverse. Rien d'autre n'est à toucher, aucune
hauteur n'est écrite nulle part.

Ce réglage gouverne les grands écrans, au-delà de 1300 pixels de large. En
dessous, une rangée de quatre visuels deviendrait trop basse pour se lire,
et le mur se recompose alors tout seul, ligne par ligne, en mettant sur
chaque ligne ce qui y tient à une hauteur correcte. Il n'y a rien à régler
pour ça. Sous 700 pixels, un visuel par ligne, pleine largeur.

Une remarque de mise en page. La dernière rangée est presque toujours
incomplète, c'est normal et prévu. Elle se cale à gauche plutôt que de
s'étirer sur toute la largeur.

Dans tous les cas, un visuel garde sa proportion d'origine. Rien n'est
jamais recadré, ni étiré.

## Déployer

Une branche par chantier, une pull request, une validation visuelle sur la
deploy preview Netlify, puis la fusion.

Netlify construit `main` en production avec la commande de `[build]` dans
`netlify.toml`, sans `--buildDrafts`.
