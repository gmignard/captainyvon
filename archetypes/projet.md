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
# en tête de la page projet, dans la colonne de gauche, au-dessus du crédit
# photo et de la note d'intention qu'est le corps de ce fichier.
# N'apparaît pas sur l'accueil.
extrait: ""

# credit_photo : nom du ou de la photographe, affiché sous l'extrait.
# credit_photo_url : adresse du site, facultative. Renseignée, elle transforme
# le nom en lien. Laisser les deux vides n'affiche aucune ligne de crédit.
credit_photo: ""
credit_photo_url: ""

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

# mise_en_avant : réservé, sans effet sur l'ordre de la grille.
mise_en_avant: false

draft: true
---

Note d'intention, trois à cinq lignes. Ce texte est l'introduction de la
page projet, en colonne étroite sous le titre.
