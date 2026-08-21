# Captain Yvon Studio

Site du studio, construit avec Hugo. Thème maison

## Créer un projet

```
hugo new content work/nom-du-projet/index.md
```

La commande crée le dossier et le fichier `index.md` à partir de
`archetypes/projet.md`, qui contient déjà tous les champs commentés. Déposer
ensuite les images dans le même dossier, puis passer `draft: false` pour
publier.

## Champs d'entête d'un projet

### Obligatoires

| Champ | Type | Rôle |
|---|---|---|
| `title` | texte | Titre du projet. Affiché sur la vignette d'accueil et en haut de la fiche. |
| `date` | date | Date de livraison. Donne l'année affichée et l'ordre de la grille, du plus récent au plus ancien. Le marqueur `0001-01-01` signifie « à remplir » : aucune année ne s'affiche tant qu'il est là. |
| `couverture` | nom de fichier | Image du dossier qui sert de vignette sur l'accueil et de couverture au lecteur vidéo. Un projet sans couverture n'apparaît pas dans la grille. |

### Facultatifs

| Champ | Type | Rôle |
|---|---|---|
| `nature` | `commande` ou `personnel` | Type de projet, affiché à côté de l'année. Voir ci-dessous. |
| `annee` | nombre | Année d'affichage, quand elle ne coïncide pas avec `date`. Fait autorité sur `date`. |
| `client` | texte | Nom du client. Vide ou absent, la ligne Client n'apparaît pas. |
| `extrait` | texte | Une à trois phrases. Sert de meta description SEO et s'affiche en tête de la fiche. N'apparaît pas sur l'accueil. |
| `competences` | liste | Affiché dans le bloc de métadonnées, entrées jointes par une virgule. |
| `avec` | liste | Idem, pour les collaborateurs. |
| `credit_photo` | structure | Crédit photographique, affiché au-dessus de la galerie. Voir ci-dessous. |
| `galerie` | liste de noms de fichiers | Sélection et ordre explicites des images. Absente, toutes les images du dossier sont reprises, couverture exclue, dans l'ordre des noms de fichiers. |
| `video` | structure | Lecteur vidéo. `plateforme` vaut `youtube` ou `vimeo`, `id` est l'identifiant de la vidéo, `ratio` vaut `16:9` par défaut. Laisser `id` vide pour un projet sans vidéo. |
| `distinctions` | liste de structures | Sélections, prix et mentions. Voir ci-dessous. |
| `livrables` | liste | **Conservé mais plus affiché.** La donnée reste saisissable pour l'archive, elle n'apparaît nulle part sur le site. |
| `mise_en_avant` | booléen | Réservé, sans effet sur l'ordre de la grille. |
| `draft` | booléen | `true` empêche la construction en production. |
| `weight` | nombre | Poids Hugo. Non utilisé pour l'ordre de la grille, qui trie par date. |

### `nature`

Deux valeurs autorisées, et deux seulement :

| Valeur | Affichage à côté de l'année |
|---|---|
| `commande` | COMMISSIONNÉ |
| `personnel` | PROJET PERSONNEL |

Toute autre valeur, un champ vide ou un champ absent n'affiche que l'année,
sans séparateur orphelin. Les capitales viennent de la feuille de style : le
fichier, lui, s'écrit en bas de casse.

### `credit_photo`

Affiché juste au-dessus de la galerie, sous la forme « Photographies Prénom
Nom ». `url` est facultative : renseignée, elle transforme le nom en lien.

```yaml
credit_photo:
  nom: "Prénom Nom"
  url: "https://example.com"
```

Sans nom, ou sur un projet sans galerie, aucune ligne n'est affichée et aucune
place n'est réservée.

L'ancienne écriture reste lue, pour ne pas avoir à réécrire les entêtes en
place, mais ne pas l'employer pour un nouveau projet :

```yaml
credit_photo: "Prénom Nom"
credit_photo_url: "https://example.com"
```

### `distinctions`

Sélections, prix et mentions en festival, affichés en bas de fiche, après la
galerie.

```yaml
distinctions:
  - nom: "Festival du Film Documentaire de Brest"
    mention: "Sélection officielle"
    annee: 2025
  - nom: "Rencontres de la Photographie"
    annee: 2024
```

Seul `nom` est requis. `mention` et `annee` sont facultatifs et leur absence ne
laisse aucune virgule orpheline. Une entrée sans nom est ignorée.

Les quatre premières distinctions sont affichées. Au-delà, les suivantes sont
repliées dans un dépliant qui annonce leur nombre. Champ absent : ni section,
ni titre.

## Page studio

La page studio est un page bundle, `content/studio/`. Elle se lit de haut en
bas dans cet ordre : le titre seul sur sa ligne, le filet, deux colonnes, puis
le mur de photos de tournage.

Le filet sous le titre est **celui des pages projet**, le même élément et la
même règle. Il n'est décrit qu'une fois dans la feuille de style, sous le nom
`.projet-filet` : les deux entêtes du site ne peuvent donc pas diverger.

### La fiche contact

Colonne de droite du haut de page. Format fiche : un intitulé en Courier
Prime, petite taille et casse haute, posé au-dessus de sa valeur. C'est la
grammaire des métadonnées d'une page projet, avec l'intitulé au-dessus plutôt
qu'à gauche, la colonne étant trop étroite pour deux pistes.

Deux blocs séparés par un filet léger, plus discret que celui du titre.

**Le bloc studio** : le bouton d'écriture et l'adresse viennent de
`params.email` dans `hugo.toml`. Les lignes suivantes viennent de la clé
`fiche` de l'entête de `content/studio/index.md` :

```yaml
fiche:
  - libelle: "Basés à"
    valeur: "Brest et Lille"
  - libelle: "Représentés par"
    valeur: "Le collectif AUNORD"
    url: "https://aunord.fr"
```

`url` est facultatif : sans lui la valeur reste du texte, avec lui elle devient
un lien qui s'ouvre dans un nouvel onglet. Une entrée sans libellé ou sans
valeur est ignorée. Retirer une entrée, ou la clé entière, ne demande aucune
retouche du gabarit.

**Le bloc personnes** vient de `data/equipe.yaml`. Le nom fait l'intitulé, le
site et le compte Instagram forment la ligne de valeur, séparés par un point
médian. Le nom n'est jamais un lien.

Le fichier ne porte que les adresses : le texte affiché d'un site est déduit de
son adresse, protocole retiré, et le compte Instagram y est saisi sans arobase,
le gabarit posant l'arobase et l'adresse du profil. Rien n'est écrit deux fois.

Vider `site` ou `instagram` retire l'entrée et le point médian avec elle, sans
laisser de ponctuation orpheline. Une personne sans aucun des deux n'apparaît
pas dans la fiche. Les champs `portrait` et `bio` sont là pour un futur bloc
équipe et restent vides aujourd'hui, sans rien produire.

Orthographe : **Jeremy Janin sans accent, Grégory Mignard avec**. Les deux
graphies sont volontaires, ne pas les uniformiser.

### Le mur de photos de tournage

Le mur est un bloc **pleine largeur sur fond sombre**, en rupture avec le fond
ivoire du site. Ses deux couleurs sont celles du pied de page, reprises de la
palette : rien n'est saisi en dur. Les photos y sont posées librement, sur un
motif de dix emplacements que le gabarit boucle — colonne de départ, largeur
en colonnes et décalage vertical sont décrits une fois pour toutes dans
`assets/css/main.css`.

Le mur **rejoint le pied de page sans couture** : les deux fonds sont le même
noir, ils se lisent comme une seule bande sombre qui ferme la page. C'est le
seul endroit du site où la respiration que `main` pose sous le contenu est
annulée, par une marge négative qui vaut exactement `--contenu-espace-bas`.
Les autres pages gardent la leur.

### Ajouter une photo de tournage

Deux gestes, pas un seul :

1. déposer le fichier dans `content/studio/`, nommé `bts-NN.<ext>` ;
2. ajouter son entrée à la clé `galerie` de `content/studio/index.md`.

C'est cette liste, et elle seule, qui décide de ce qui s'affiche et dans quel
ordre : rien n'est ramassé automatiquement, rien n'est trié, rien n'est tiré
au sort. Deux constructions successives donnent donc exactement le même HTML.
Une photo déposée mais absente de la liste n'apparaît pas ; une entrée dont le
fichier n'existe pas est ignorée sans casser la mise en page.

Chaque entrée porte son texte alternatif :

```yaml
galerie:
  - image: bts-16.jpg
    alt: "Ce que montre la photo, en une phrase."
```

`alt` absent donne `alt=""` : la photo est alors traitée comme décorative.
Une entrée peut aussi se réduire au seul nom de fichier, avec le même effet.

Le nombre de photos est libre — de 6 à 20 sans y penser. Le motif boucle sur
dix emplacements : la onzième photo retombe sur le premier, en retirer trois
ne dérange rien. L'ordre de la liste alterne volontairement paysages et
portraits, et place les portraits sur les emplacements les plus étroits :
c'est ce qui évite qu'une image verticale prenne six colonnes.

Retirer la clé `galerie`, ou la vider, fait disparaître la section entière,
titre et fond sombre compris.

Format et poids des fichiers déposés : du JPEG, **1000 px de large au plus**
et **300 Ko par fichier au plus**. Hugo produit ensuite les WebP servis au
visiteur, calés sur la largeur réelle de l'emplacement, mais il n'agrandit
jamais une source ni ne compense un fichier trop lourd au dépôt. Cette limite
tient le poids de la page sous 1,5 Mo — mesuré à 718 Ko avec quinze photos,
fontes comprises.

## Nommage des images d'un page bundle

Les images de galerie d'un projet sont numérotées sur **deux chiffres**,
`<slug>_01.jpeg` à `<slug>_15.jpeg`, et non `_1` à `_15`.

Hugo trie les page resources en ordre lexicographique, pas en ordre naturel :
avec une numérotation à un chiffre, `_10` passe avant `_2` et la galerie
s'affiche dans le désordre. Le zéro de tête rétablit l'ordre voulu sans
qu'aucun tri ne soit écrit dans le gabarit.

La couverture, elle, garde le nom `couverture.<ext>` : c'est ce nom qui la
fait reconnaître comme couverture et exclure de la galerie.

## Maintenance

### Fiches de recette

Deux projets de test vivent dans `content/work/` et servent à vérifier le
gabarit de fiche projet après chaque évolution :

- `zz-recette-complete` : tous les champs facultatifs renseignés, plus de
  quatre distinctions donc un dépliant, une distinction sans mention, une
  autre sans année, un `client` présent mais vide ;
- `zz-recette-minimale` : ni image, ni galerie, ni vidéo, ni crédit, ni
  distinction.

Les images `bts-*.jpg` de `content/studio/` sont **provisoires** : elles sont
copiées d'un bundle de projet en attendant la sélection définitive des photos
de tournage. Les remplacer par les vraies avant la mise en ligne.

Les deux portent `draft: true` de façon **permanente** : ils ne sont jamais
construits en production et ne doivent pas être publiés. Ils se vérifient en
local avec :

```
hugo server -D
```

Ne pas les supprimer : ce sont les fiches de recette du gabarit.

Les deploy previews de Netlify construisent les brouillons, ces deux fiches y
sont donc consultables à leur adresse pendant une relecture, alors que la
production ne les construit jamais. Leur entête déclare `_build.list: never` :
même en preview, elles n'apparaissent ni dans le sitemap, ni dans un flux, ni
dans la liste des projets de l'accueil.
