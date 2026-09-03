---
title: "Fragments"

# seo_titre : facultatif. Remplace title dans la balise <title> uniquement,
# sans effet sur le <h1> ni sur les apercus de partage.
seo_titre: ""

# description : meta description de la page. Une a deux phrases.
description: ""

# layout : obligatoire. C'est lui qui appelle layouts/_default/fragments.html,
# donc la mosaique. Sans lui la page retombe sur le gabarit de page courante
# et le mur n'est pas rendu.
layout: "fragments"

# resources : legendes et textes alternatifs du mur. Meme mecanisme que les
# `alt` de la galerie d'une fiche projet. Cette liste ne decide ni de
# l'affichage ni de l'ordre : les fichiers deposes dans ce dossier sont tous
# affiches, dans l'ordre de leurs noms.
#   src    : nom exact du fichier present dans ce dossier.
#   title  : texte alternatif d'une photo, nom accessible d'une boucle. Un
#            fichier sans entree reste en alt="", donc decoratif.
#   params : projet, client et annee forment la legende, en deux lignes. Le
#            client et l'annee sont separes par un point median, jamais de
#            separateur orphelin si l'un des deux manque, et aucune ligne
#            n'est rendue si les trois manquent.
#
# Nommage des fichiers, detaille dans docs/guide-projet.md :
#   une photo         -> 0102.jpg
#   une boucle video  -> 0104_16x9.mp4, avec son image d'affiche 0104_16x9.jpg
# Numerotation sur quatre chiffres avec un pas de 2, pour inserer sans
# renommer. Le suffixe de ratio est obligatoire sur les MP4 et sur eux seuls :
# Hugo lit les dimensions d'une image, jamais celles d'une video. Formats
# acceptes : 16x9, 9x16, 4x3, 3x4, 3x2, 2x3, 1x1.
# resources:
#   - src: "0104_16x9.mp4"
#     title: "Poncage d'une planche de surf dans un atelier."
#     params:
#       projet: "Tides of Time"
#       client: "Captain Yvon Originals"
#       annee: 2025

draft: true
---

Texte d'introduction du mur, deux a quatre lignes. Il s'affiche sous le
titre, au-dessus de la mosaique.
