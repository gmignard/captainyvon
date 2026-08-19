# Captain Yvon Studio

Site du studio, construit avec Hugo. Thème maison, aucune dépendance : pas de
thème tiers, pas de module Hugo, pas de build JavaScript, aucune police distante.

**Prérequis :** Hugo **extended** 0.148.2 (la version est épinglée dans
`netlify.toml`, garder les deux alignées).

```bash
hugo server        # aperçu local sur http://localhost:1313
hugo --gc --minify # build de production dans public/
```

---

## 1. Ajouter un projet

```bash
hugo new content --kind projet work/nom-du-projet/index.md
```

Cela crée `content/work/nom-du-projet/index.md` à partir de
`archetypes/projet.md`. Le dossier `nom-du-projet` devient l'URL
`/work/nom-du-projet/`. Il faut ensuite passer `draft: true` à `draft: false`
pour que le projet soit publié.

### Champs de l'entête

| Champ | Rôle |
|---|---|
| `title` | Titre affiché. Si absent, le nom du dossier est utilisé. |
| `nature` | `film`, `photo` ou `mixte`. Voir ci-dessous. |
| `client` | Bloc accordéon **Client**. |
| `annee` | Année, affichée en petit sous le titre. |
| `extrait` | 1 à 3 phrases. Sert de description sur l'accueil, de texte italique sous le titre, et de meta description SEO. |
| `services` | Liste, bloc accordéon **Services**. |
| `livrables` | Liste, bloc accordéon **Livrables**. |
| `avec` | Liste de collaborateurs, bloc accordéon **Avec**. |
| `couverture` | Nom du fichier image servant de vignette et d'affiche vidéo. |
| `video` | `plateforme` (`youtube` ou `vimeo`), `id`, `ratio` (`16:9` par défaut). |
| `mise_en_avant` | `true` remonte le projet en tête de la grille d'accueil. |
| `weight` | Entier. Ordre croissant sur l'accueil et pour Précédent / Suivant. |
| `draft` | `true` = non publié. |

**Tout champ laissé vide disparaît simplement du rendu.** Aucun libellé
orphelin, aucune liste vide, aucun accordéon sans contenu. Un projet dont
l'entête ne contient que `title` s'affiche correctement.

### Valeurs de `nature`

| Valeur | Rendu |
|---|---|
| `film` | Bloc vidéo en tête, galerie en bas. |
| `photo` | Aucun bloc vidéo, la galerie est le corps principal. |
| `mixte` | Bloc vidéo en tête et galerie en bas. |

Si `nature` est absent, il est déduit : une vidéo renseignée donne `film`,
sinon `photo`. La nature s'affiche en libellé discret sur la vignette d'accueil.

### Images et nommage

Déposer les images **dans le dossier du projet**, à côté de `index.md`.

- Le fichier désigné par `couverture` sert de vignette sur l'accueil et
  d'affiche pour la vidéo. Il est **exclu de la galerie**.
- **Tous les autres fichiers image du dossier composent la galerie**,
  automatiquement, triés par nom de fichier. Il n'y a pas de champ `galerie`
  dans l'entête : ajouter une image au dossier suffit, sans toucher au YAML.
- Préfixer les fichiers `01_`, `02_`, `03_`… pour maîtriser l'ordre.
  Le préfixe numérique est retiré du texte alternatif.
- Le texte alternatif est déduit du nom de fichier sans extension.
  Nommer les fichiers de façon descriptive : `03_atelier-du-forgeron.jpg`
  donne `alt="Atelier du forgeron"`.
- Format d'entrée : JPEG ou PNG, au moins 1600 px de large. Hugo génère
  automatiquement les versions WebP 800 et 1600 px. Portrait et paysage se
  côtoient sans recadrage.

Les images sont ré-encodées au build : les données EXIF, dont les coordonnées
GPS, ne se retrouvent pas dans les fichiers publiés.

---

## 2. Ajouter une entrée de menu

Tout se passe dans `hugo.toml`, section `[[menus.main]]`. **Aucun template
n'est à modifier.**

```toml
[[menus.main]]
  name = "Archives"
  url = "/archives/"
  weight = 40
```

`weight` définit l'ordre d'affichage, croissant de gauche à droite.

### Soulignement de l'entrée active

Une entrée est soulignée (et porte `aria-current="page"`) si :

- son `url` correspond à la page affichée, **ou**
- son paramètre `accueil` vaut `true` et la page affichée est l'accueil, **ou**
- l'adresse de la page commence par l'un de ses `prefixes`.

C'est ce dernier point qui fait que **Work** reste souligné sur
`/work/immersion/` :

```toml
[[menus.main]]
  name = "Work"
  url = "/"
  weight = 10
  [menus.main.params]
    accueil = true
    prefixes = ["/work/"]
```

### Test effectué

Une quatrième entrée factice « Archives » a été ajoutée à `hugo.toml`, puis le
site reconstruit. L'entrée est apparue dans la navigation **sans qu'aucun
fichier de `layouts/` soit touché** (empreinte SHA-256 de l'arborescence
`layouts/` identique avant et après). L'entrée a ensuite été retirée.
Reproduire ce test après toute modification de `nav.html` :

```bash
find layouts -type f | sort | xargs sha256sum | sha256sum   # avant
# ajouter l'entrée dans hugo.toml, puis :
hugo --gc --minify
find layouts -type f | sort | xargs sha256sum | sha256sum   # doit être identique
```

---

## 3. Déployer

Hébergement Netlify. La configuration vit dans `netlify.toml` : commande de
build, dossier publié (`public`) et version de Hugo épinglée.

1. Travailler sur une branche : `git checkout -b ma-modification`
2. Pousser la branche : `git push -u origin ma-modification`
3. Ouvrir une pull request. Netlify construit automatiquement un **deploy
   preview** sur une URL temporaire, avec sa propre `baseURL` pour que les
   liens canoniques ne pointent pas vers la production.
4. Vérifier l'aperçu, puis **merger sur `main`**. Le merge déclenche le
   déploiement en production.

Les redirections héritées de l'ancien site sont dans `static/_redirects`.
Les adresses `/work/<slug>`, `/studio` et `/contact` sont identiques à
l'ancien site : aucune redirection n'est nécessaire pour elles.

---

## 4. À remplacer avant mise en ligne

Ces fichiers sont des **placeholders** générés pendant la construction du site.
Ils sont valides et le site fonctionne avec, mais ils ne sont pas les
véritables éléments graphiques du studio.

### Logo

`assets/img/logo-captainyvon-noir.svg` — cadre noir contenant le texte
« CAPTAIN YVON ». Remplacer par le logo définitif, puis ajuster dans
`hugo.toml` :

```toml
[params]
  logo = "img/logo-captainyvon-noir.svg"
  logoLargeur = 220   # largeur intrinsèque du fichier, en pixels
  logoHauteur  = 36   # hauteur intrinsèque du fichier, en pixels
```

Ces deux dimensions évitent tout décalage de mise en page au chargement.
Le logo est un fichier image : si la palette est inversée (voir plus bas),
il faut fournir une version claire et changer la ligne `logo`.

### Icônes sociales

`assets/icones/instagram.svg`, `youtube.svg`, `linkedin.svg`.

Les icônes définitives vont dans `assets/icones/`, **en SVG**, et doivent
respecter trois règles :

- **pas d'attribut `width`**
- **pas d'attribut `height`**
- **pas de `fill` codé en dur** — utiliser `fill="currentColor"`

Uniquement un `viewBox` et `fill="currentColor"`. La taille est fixée par
`.icone svg` dans la feuille de style, et la couleur est héritée du texte
parent : l'inversion de palette est alors gratuite, sans toucher aux fichiers.

Le nom du fichier (sans `.svg`) est la valeur du champ `icone` dans
`hugo.toml` :

```toml
[[params.social]]
  nom = "Instagram"
  url = "https://www.instagram.com/captainyvon/"
  icone = "instagram"      # -> assets/icones/instagram.svg
```

### Images des projets de démonstration

Toutes les images de `content/work/*/` sont des **aplats gris** générés aux
bonnes dimensions, mélangeant portrait et paysage, pour valider la galerie.
Les remplacer par les vraies photographies, en gardant la convention de
nommage décrite en section 1.

L'image Open Graph de repli `assets/img/og-defaut.jpg` (1200 × 630) est elle
aussi un aplat gris. Elle s'affiche lors du partage des pages qui n'ont pas
de couverture (Studio, Contact, 404).

### Textes Studio et Contact

`content/studio.md` et `content/contact.md` contiennent un texte minimal, écrit
à partir des seules informations disponibles, marqué par un commentaire
`TEXTE À VALIDER`. Le relire et le compléter.

### Champs `annee` des projets

Les trois projets de démonstration ont un champ `annee` volontairement vide
(commenté « à renseigner »). Le renseigner projet par projet.

---

## Inverser la palette

Le site est noir sur fond blanc, en clair, assumé : `prefers-color-scheme`
n'est **pas** implémenté. Toutes les couleurs passent par quatre variables
déclarées une seule fois en haut de `assets/css/main.css` :

```css
:root {
  --fond: #ffffff;
  --texte: #111111;
  --texte-doux: #5a5a5a;
  --trait: #d9d9d9;
}
```

Modifier ces quatre lignes suffit à inverser tout le site, icônes sociales
comprises. Seul le logo, qui est un fichier image, demande un fichier clair
et une ligne changée dans `hugo.toml`.
