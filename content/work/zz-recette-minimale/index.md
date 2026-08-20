---
title: "Recette minimale"
date: 2026-08-20
annee: 2026
nature: "commande"
client: "Client de recette"
extrait: "Fichier de recette. Ne pas publier. Fiche dépourvue de tout champ facultatif."
competences: ["Réalisation"]
# _build : la fiche est construite et accessible a son adresse, mais n'entre
# dans aucune collection. Elle est donc absente du sitemap, de la liste des
# projets de l'accueil et de tout flux, y compris quand Netlify construit les
# brouillons pour une deploy preview.
_build:
  list: never
  render: always

weight: 999
draft: true
---

Fichier de recette du cas minimal. Aucun champ facultatif renseigné.
