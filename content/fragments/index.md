---
title: "Fragments"
seo_titre: "Fragments, images et boucles prélevées dans nos travaux"
description: "Un mur d'images fixes et de boucles muettes prélevées dans les films et les reportages de Captain Yvon Studio."
layout: "fragments"

# ATTENTION, JEU D'ESSAI
# Les fichiers numérotés 0102 à 0126 présents dans ce dossier sont des mires
# de recette, générées pour vérifier la grille sur la deploy preview. Elles
# ne sont pas des images du studio. Les remplacer par les vrais fichiers
# avant la mise en production, et mettre à jour les entrées `resources`
# ci-dessous en conséquence.
#
# resources : légendes et textes alternatifs du mur. Le mécanisme est celui
# des `alt` de la galerie d'une fiche projet.
#   src    : le nom exact du fichier présent dans ce dossier.
#   title  : texte alternatif d'une photo, nom accessible d'une boucle. Un
#            fichier sans entrée reste en alt="", donc décoratif.
#   params : projet, client et annee forment la légende, en deux lignes.
#            Le client et l'année sont séparés par un point médian, jamais
#            de séparateur orphelin si l'un des deux manque. Aucune légende
#            n'est rendue si les trois manquent.
#
# Les fichiers sont affichés dans l'ordre de leurs noms, cette liste ne
# décide de rien d'autre que des textes.
resources:
  - src: "0102.jpg"
    title: "Mire de recette au format 3:2."
    params:
      projet: "Hiver à contre-courant"
      client: "Brest Métropole"
      annee: 2023

  - src: "0104_16x9.mp4"
    params:
      projet: "Portrait de Léa Brassy"
      client: "Attitude Manche"
      annee: 2019

  - src: "0106.jpg"
    title: "Mire de recette au format 2:3."
    params:
      projet: "Meneham"
      client: "Captain Yvon Originals"
      annee: 2024

  - src: "0108_9x16.mp4"
    title: "Immersion"
    params:
      projet: "Immersion"
      client: "Attitude Manche"
      annee: 2020

  - src: "0110.jpg"
    params:
      projet: "Récolte d'algues dans les Abers"
      client: "Bord à Bord"
      annee: 2023

  - src: "0112_4x3.mp4"
    title: "Mire de recette animée au format 4:3."
    params:
      projet: "Immersion"
      client: "Decathlon"

  - src: "0114.jpg"
    title: "Mire de recette au format carré."
    params:
      projet: "Togitaku"
      client: "Togitaku"
      annee: 2023

  - src: "0116_16x9.mp4"
    title: "Mire de recette animée au format 16:9."
    params:
      projet: "She's Out There"
      client: "Captain Yvon Originals"
      annee: 2021

  # 0118.jpg n'a volontairement aucune entrée : la tuile reste décorative,
  # sans texte alternatif et sans légende. C'est le comportement attendu
  # d'un fichier déposé sans métadonnées.

  - src: "0120_3x4.mp4"
    title: "Mire de recette animée au format 3:4."
    params:
      projet: "Le Capitaine"
      client: "Le Capitaine"
      annee: 2022

  # 0122.jpg porte un texte alternatif mais aucune métadonnée de contexte :
  # l'image est décrite, aucune ligne de légende n'est rendue.
  - src: "0122.jpg"
    title: "Mire de recette au format 2:3."

  - src: "0124_16x9.mp4"
    title: "Mire de recette animée au format 16:9."
    params:
      projet: "Vendée Globe"
      client: "Éric Bellion"
      annee: 2024

  - src: "0126_1x1.mp4"
    title: "Mire de recette animée au format carré."
    params:
      projet: "Une adresse, la Manche"
      client: "Département de la Manche"
      annee: 2023

draft: false
---

Des images et des boucles prélevées dans nos films et nos reportages. Des
cadres retenus en repérage, des gestes vus de près ou des plans qui n'ont
pas trouvé leur place au montage. Rien ici ne renvoie vers une fiche
projet : ce sont des fragments, on les regarde pour eux-mêmes.
