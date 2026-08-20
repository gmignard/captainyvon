---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"

# date : date de livraison du projet. Elle donne l'année affichée à côté du
# titre, sur l'accueil comme sur la page projet, et elle donne l'ordre de la
# grille, du plus récent au plus ancien.
date: {{ .Date }}

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

# services, avec : listes affichées dans le bloc de métadonnées de la page
# projet, chacune sur une ligne, les entrées jointes par une virgule. Une
# liste vide n'affiche aucune ligne.
services: []
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
# passe avant `_2`. Voir le README.
galerie: []

# video : laisser id vide pour un projet sans vidéo.
video:
  # plateforme : youtube | vimeo
  plateforme: ""
  id: ""
  # ratio : 16:9 par défaut. Ex. 4:3, 2.39:1, 9:16
  ratio: ""

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

# mise_en_avant : réservé, sans effet sur l'ordre de la grille.
mise_en_avant: false

draft: true
---

Note d'intention, trois à cinq lignes. Ce texte est l'introduction de la
page projet, en colonne étroite sous le titre.
