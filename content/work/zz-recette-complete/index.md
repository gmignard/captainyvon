---
title: "Recette du template de fiche projet"
date: 2026-08-20
annee: 2026
nature: "personnel"
client: ""
extrait: "Fichier de recette. Ne pas publier. Sert à valider le rendu de la fiche projet."
services: ["Réalisation", "Image", "Montage", "Étalonnage"]
avec: ["Jérémy Janin"]
credit_photo:
  nom: "Prénom Nom"
  url: "https://example.com"
couverture: "01.jpg"
galerie: ["01.jpg", "02.jpg", "03.jpg"]
video:
  plateforme: "youtube"
  id: "lv4eEdBmAx4"
  ratio: "16:9"
distinctions:
  - nom: "Festival A"
    mention: "Sélection officielle"
    annee: 2026
  - nom: "Festival B"
    mention: "Prix du jury"
    annee: 2026
  - nom: "Festival C"
    mention: "Mention spéciale"
    annee: 2025
  - nom: "Festival D"
    mention: "Sélection officielle"
    annee: 2025
  - nom: "Festival E"
    mention: "Compétition internationale"
    annee: 2025
  - nom: "Festival F"
    annee: 2024
  - nom: "Festival G"
    mention: "Hors compétition"
# _build : la fiche est construite et accessible a son adresse, mais n'entre
# dans aucune collection. Elle est donc absente du sitemap, de la liste des
# projets de l'accueil et de tout flux, y compris quand Netlify construit les
# brouillons pour une deploy preview.
_build:
  list: never
  render: always

weight: 999
draft: false
---

Fichier de recette du template de fiche projet. Il n'est jamais construit en
production et sert à vérifier le rendu des champs facultatifs.
