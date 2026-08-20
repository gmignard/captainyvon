---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"

# date : date de livraison du projet. Elle donne l'année affichée à côté du
# titre, sur l'accueil comme sur la page projet, et elle donne l'ordre de la
# grille, du plus récent au plus ancien.
date: {{ .Date }}

# client : nom du client ou de la structure commanditaire.
client: ""

# extrait : une à trois phrases. Sert de meta description SEO.
# N'apparaît ni sur l'accueil ni dans le corps de la page projet, dont
# l'introduction est le corps de ce fichier.
extrait: ""

# services, livrables, avec : listes affichées dans le bloc de métadonnées
# de la page projet, chacune sur une ligne, les entrées jointes par une
# virgule. Une liste vide n'affiche aucune ligne.
services: []
livrables: []
avec: []

# couverture : nom du fichier image de ce dossier. C'est la vignette de
# l'accueil et l'image du lecteur vidéo. Le titre du projet y est incrusté.
couverture: "couverture.jpg"

# galerie : liste explicite des fichiers image de ce dossier à afficher,
# dans l'ordre voulu. Indispensable aux projets photographiques, qui n'ont
# pas de vidéo. Liste vide ou absente = aucune galerie.
galerie: []

# video : laisser id vide pour un projet sans vidéo.
video:
  # plateforme : youtube | vimeo
  plateforme: ""
  id: ""
  # ratio : 16:9 par défaut. Ex. 4:3, 2.39:1, 9:16
  ratio: ""

# mise_en_avant : réservé, sans effet sur l'ordre de la grille.
mise_en_avant: false

draft: true
---

Note d'intention, trois à cinq lignes. Ce texte est l'introduction de la
page projet, en colonne étroite sous le titre.
