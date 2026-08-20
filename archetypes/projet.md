---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"

# date : obligatoire. Elle donne l'année affichée sur l'accueil et sur la
# page projet, et elle donne l'ordre de la grille, du plus récent au plus
# ancien. Il n'y a pas de champ `annee` ni de champ `weight` : un seul
# mécanisme, donc aucun risque de désaccord entre deux sources.
date: {{ .Date }}

# type : nature du projet, affichée telle quelle à droite du titre sur la
# page projet, en bas de casse. Ex. film documentaire, photographie,
# film de marque. Laisser vide si sans objet.
type: ""

# Nom du client ou de la structure commanditaire.
client: ""

# Lieu et durée, affichés dans le bloc de métadonnées.
lieu: ""
duree: ""

# roles : ce que le studio a fait sur le projet. Affiché en une ligne,
# les entrées jointes par une virgule. Liste vide = pas de ligne.
roles: []

# avec : collaborateurs, structures partenaires. Même rendu que roles.
avec: []

# extrait : une à trois phrases. Sert de meta description SEO.
# N'apparaît ni sur l'accueil ni dans le corps de la page projet, dont
# l'introduction est le corps de ce fichier.
extrait: ""

# couverture : nom du fichier image de ce dossier. C'est la vignette de
# l'accueil et l'image de la façade vidéo. Le titre du projet y est incrusté.
couverture: "couverture.jpg"

# galerie : liste explicite des fichiers image de ce dossier à afficher,
# dans l'ordre voulu. Liste vide ou absente = aucune galerie. Le contenu du
# dossier ne pilote pas l'affichage, seule cette liste le fait.
galerie: []

# video : laisser id vide pour un projet sans vidéo.
video:
  # plateforme : youtube | vimeo
  plateforme: ""
  id: ""
  # ratio : 16:9 par défaut. Ex. 4:3, 2.39:1, 9:16
  ratio: ""

# tags : mots-clés libres. Non affichés pour l'instant.
tags: []

# mise_en_avant : réservé, non utilisé pour l'instant.
mise_en_avant: false

draft: true
---

Note d'intention, trois à cinq lignes. Ce texte est l'introduction de la
page projet, en colonne étroite sous le titre.
