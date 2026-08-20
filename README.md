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
| `services` | liste | Affiché dans le bloc de métadonnées, entrées jointes par une virgule. |
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

Les deux portent `draft: true` de façon **permanente** : ils ne sont jamais
construits en production et ne doivent pas être publiés. Ils se vérifient en
local avec :

```
hugo server -D
```

Ne pas les supprimer : ce sont les fiches de recette du gabarit.
