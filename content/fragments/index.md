---
# Ce dossier n'est plus une page : build.render = never empeche toute
# construction de /fragments/. Il reste lu par layouts/index.html, qui y
# puise les medias du mur affiche sur l'accueil. Deposer un fichier ici le
# publie donc sur la page d'accueil, pas a une adresse /fragments/.
build:
  render: never
  list: never
  publishResources: true

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
#
# Échafaudage : une entrée par fichier du dossier, dans l'ordre, champs
# vides. Un champ laissé vide se comporte exactement comme un champ absent,
# la page est donc juste en l'état. Remplir au fur et à mesure.
resources:
  - src: "0102_16x9.mp4"
    title: ""
    params:
      projet: "Portrait de Léa Brassy"
      client: "Attitude Manche"
      annee: "2019"

  - src: "0104_16x9.mp4"
    title: ""
    params:
      projet: "Reportage Mytiliculture"
      client: "Mytilimer"
      annee: "2024"

  - src: "0106_9x16.mp4"
    title: ""
    params:
      projet: "Immersion"
      client: "Attitude Manche"
      annee: "2020"

  - src: "0108.jpg"
    title: ""
    params:
      projet: "Reportage - Récolte d'algues"
      client: "Bord à Bord"
      annee: "2023"

  - src: "0110_9x16.mp4"
    title: ""
    params:
      projet: "Ahoy"
      client: "Eric Bellion"
      annee: "2025"

  - src: "0112_16x9.mp4"
    title: ""
    params:
      projet: ""
      client: ""
      annee: ""

  - src: "0114_16x9.mp4"
    title: ""
    params:
      projet: ""
      client: ""
      annee: ""

  - src: "0116_16x9.mp4"
    title: ""
    params:
      projet: ""
      client: ""
      annee: ""

  - src: "0118_16x9.mp4"
    title: ""
    params:
      projet: ""
      client: ""
      annee: ""

  - src: "0115.jpg"
    title: ""
    params:
      projet: "Campagne d'affichage"
      client: "Bretagne Tourisme"
      annee: ""
  - src: "0120_9x16.mp4"
    title: ""
    params:
      projet: ""
      client: ""
      annee: ""

  - src: "0122_16x9.mp4"
    title: ""
    params:
      projet: ""
      client: ""
      annee: ""

  - src: "0124_16x9.mp4"
    title: ""
    params:
      projet: ""
      client: ""
      annee: ""

  - src: "0126_16x9.mp4"
    title: ""
    params:
      projet: ""
      client: ""
      annee: ""

  - src: "0128_9x16.mp4"
    title: ""
    params:
      projet: ""
      client: ""
      annee: ""

draft: false
---
