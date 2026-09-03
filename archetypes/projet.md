---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"

# seo_titre : facultatif. Remplace title dans la balise <title> uniquement,
# sans effet sur le titre affiche en <h1> ni sur les apercus de partage
# (og:title, twitter:title), qui continuent d'utiliser title. Viser 60
# caracteres au plus : le nom du studio est ajoute ensuite par le gabarit.
seo_titre: ""

# date : date de livraison du projet. Elle donne l'année affichée à côté du
# titre, sur l'accueil comme sur la page projet, et elle donne l'ordre de la
# grille, du plus récent au plus ancien.
# Le marqueur 0001-01-01 vaut « à remplir » : tant qu'il reste en place,
# aucune année ne s'affiche, ni sur l'accueil ni sur la page projet. La
# règle est centralisée dans layouts/partials/annee.html.
date: {{ .Date }}

# annee : année affichée à côté du titre, sur l'accueil comme sur la page
# projet, quand elle ne coïncide pas avec date. Renseignée, elle fait
# autorité sur date pour l'année affichée. Elle sert aux projets dont
# l'année de livraison ne coïncide pas avec la date choisie pour la fiche.
# Elle ne joue aucun rôle dans l'ordre de la grille, qui trie toujours sur
# date.
# annee: 2025

# nature : type de projet. Deux valeurs autorisées, et deux seulement :
#   commande  -> affiche COMMISSIONNÉ à côté de l'année
#   personnel -> affiche PROJET PERSONNEL
# Toute autre valeur, ou un champ vide, n'affiche que l'année.
nature: "commande"

# client : nom du client ou de la structure commanditaire.
client: ""

# extrait : une à trois phrases. Sert de meta description SEO et s'affiche
# en tête de la page projet, dans la colonne de gauche, au-dessus de la note
# d'intention qu'est le corps de ce fichier. N'apparaît pas sur l'accueil.
extrait: ""

# credit_photo : nom du ou de la photographe, affiché juste au-dessus de la
# galerie, sous la forme « Photographies Prénom Nom ». url est facultative :
# renseignée, elle transforme le nom en lien. Sans nom, ou sans galerie,
# aucune ligne n'est affichée.
# credit_photo:
#   nom: "Prénom Nom"
#   url: "https://example.com"

# competences, avec : listes affichées dans le bloc de métadonnées de la page
# projet, chacune sur une ligne, les entrées jointes par une virgule. Une
# liste vide n'affiche aucune ligne.
competences: []
avec: []

# livrables : champ conservé mais NON RENDU. La fiche projet ne l'affiche
# plus depuis août 2026. La donnée reste saisissable pour l'archive et pour
# un usage futur, elle n'apparaît nulle part sur le site.
# livrables: []

# couverture : nom du fichier image de ce dossier. C'est la vignette de
# l'accueil et l'image du lecteur vidéo. Le titre du projet y est incrusté.
couverture: "couverture.jpg"

# galerie : liste explicite des fichiers image de ce dossier à afficher,
# dans l'ordre voulu. Liste vide ou absente : toutes les images du dossier
# sont reprises, couverture exclue, dans l'ordre des noms de fichiers.
# Numéroter ces noms sur deux chiffres, `_01` et non `_1`, sans quoi `_10`
# passe avant `_2`. Voir docs/guide-projet.md.
galerie: []

# resources : texte alternatif des images de la galerie, metadonnees de
# ressource de page au sens de Hugo. Le title d'une ressource devient son
# attribut alt dans la galerie. Une image sans entree ici reste en alt="",
# donc traitee comme decorative, ce qui est le comportement voulu a defaut
# de description. src doit correspondre au nom exact du fichier present
# dans ce dossier. La couverture n'a pas besoin d'entree, elle n'est pas
# affichee dans la galerie.
# resources:
#   - src: "nom-du-fichier.webp"
#     title: "Description de ce que montre l'image."

# video : laisser id vide pour un projet sans vidéo.
video:
  # plateforme : youtube | vimeo
  plateforme: ""
  id: ""
  # ratio : 16:9 par défaut. Ex. 4:3, 2.39:1, 9:16
  ratio: ""
  # masquee : champ absent ou false -> video publiee, comportement actuel.
  # true -> le lecteur ne s'affiche pas, la couverture seule est montree a
  # sa place, mais id reste en place dans l'entete pour la publication a
  # venir.
  # masquee: false

# distinctions : sélections, prix et mentions en festival. Champ facultatif.
# Seul `nom` est requis, `mention` et `annee` sont facultatifs et leur absence
# ne laisse aucune virgule orpheline. Les quatre premières sont affichées,
# les suivantes dans un dépliant.
# distinctions:
#   - nom: "Festival du Film Documentaire de Brest"
#     mention: "Sélection officielle"
#     annee: 2025
#   - nom: "Rencontres de la Photographie"
#     annee: 2024

# accueil : presence du projet dans la grille de l'accueil. Champ absent
# ou true -> le projet est affiche, c'est le comportement par defaut.
# false -> le projet sort de la grille sans etre depublie : sa page reste
# construite, son adresse ne change pas et reste accessible par lien
# direct comme par le sitemap.
# La grille se lit sur deux colonnes : viser un nombre pair de projets
# affiches, sinon la derniere rangee reste a moitie vide.
# accueil: true

draft: true
---

Note d'intention, trois à cinq lignes. Ce texte est l'introduction de la
page projet, en colonne étroite sous le titre.
