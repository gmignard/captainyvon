---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"

# nature : film | photo | mixte
#   film   -> bloc vidéo en tête, galerie en bas
#   photo  -> aucun bloc vidéo, la galerie est le corps principal
#   mixte  -> bloc vidéo en tête et galerie en bas
# Si le champ est absent, il est déduit : vidéo renseignée => film, sinon photo.
nature: "film"

# Nom du client ou de la structure commanditaire.
client: ""

# Année de réalisation, ex. 2024.
# Affichée sur l'accueil, entre parenthèses après le titre du projet.
# Laisser vide si inconnue : la légende n'affiche alors que le titre,
# sans parenthèses vides.
annee:

date: {{ .Date }}

# extrait : une à trois phrases. Sert de texte d'introduction sur la page
# projet et de meta description SEO. N'apparaît pas sur l'accueil, dont les
# vignettes ne portent que le titre et l'année.
extrait: ""

# Listes affichées en accordéon. Une liste vide n'affiche aucun bloc.
services: []
livrables: []

# avec : collaborateurs, structures partenaires. Liste vide = pas de bloc.
avec: []

# couverture : nom du fichier image de ce dossier. Il est exclu de la galerie.
# Tous les autres fichiers image du dossier composent la galerie,
# triés par nom de fichier. Préfixer 01_, 02_... pour maîtriser l'ordre.
couverture: "couverture.jpg"

# video : laisser id vide pour un projet sans vidéo.
video:
  # plateforme : youtube | vimeo
  plateforme: ""
  id: ""
  # ratio : 16:9 par défaut. Ex. 4:3, 2.39:1, 9:16
  ratio: ""

# mise_en_avant : remonte le projet en tête de la grille d'accueil.
mise_en_avant: false

# weight : ordre croissant sur l'accueil et pour la navigation Précédent / Suivant.
weight: 10

draft: true
---
