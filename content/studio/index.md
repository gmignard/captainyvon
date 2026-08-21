---
title: "Studio"
description: "Captain Yvon Studio, duo de réalisateurs et photographes entre Brest et Lille."

# layout : gabarit dedie, layouts/_default/studio.html. Il scinde ce texte et
# la colonne de contact, puis rend le mur de photos de tournage.
layout: "studio"

# fiche : les lignes de la fiche contact, colonne de droite du haut de page.
# Elles sont saisies ici et non dans le gabarit : leur ordre est celui de la
# liste, et en retirer une ne demande aucune retouche de code.
# Chaque entree porte un libelle et une valeur. `url` est facultatif : sans
# lui la valeur reste du texte, avec lui elle devient un lien externe.
# Une entree sans valeur est ignoree, sans laisser de libelle orphelin.
fiche:
  - libelle: "Basés à"
    valeur: "Brest et Lille"
  - libelle: "Représentés par"
    valeur: "Le collectif AUNORD"
    url: "https://aunord.fr"
  - libelle: "Podcast"
    valeur: "Slow is Beautiful"
    url: "https://slowisbeautiful.substack.com"

# galerie : ordre et textes alternatifs du mur de photos de tournage.
# C'est cette liste, et elle seule, qui pilote l'affichage : le mur ne ramasse
# plus les fichiers du dossier tout seul. Deux consequences voulues.
#   1. L'ordre est explicite, donc stable : deux constructions successives
#      produisent le meme HTML, sans tri automatique ni tirage aleatoire.
#   2. Chaque photo porte son texte alternatif, ce qu'un nom de fichier ne
#      saura jamais donner.
# Une entree se reduit a `image` seul : `alt` manquant devient alt="", la
# photo est alors traitee comme decorative. Une entree dont le fichier
# n'existe pas dans le bundle est ignoree, sans casser la mise en page.
#
# Le nombre d'entrees est libre, de 6 a 20 : le motif de placement du mur
# boucle sur dix emplacements, en ajouter ou en retirer ne derange rien.
# L'ordre ci-dessous alterne volontairement paysages et portraits, et place
# les portraits sur les emplacements les plus etroits du motif : c'est ce qui
# evite qu'une image verticale prenne six colonnes et ecrase le reste.
galerie:
  - image: bts-01.jpg
    alt: "Un opérateur filme au trépied une personne assise à une table, seule au milieu d'un champ noyé de brume."
  - image: bts-05.jpg
    alt: "Un réalisateur en chemise à carreaux, caméra en main et retour au casque, indique une direction dans un champ de lin."
  - image: bts-02.jpg
    alt: "Champ de lin en fleurs photographié au ras des tiges, fleurs bleues piquées dans le vert."
  - image: bts-03.jpg
    alt: "Un cycliste pousse un vélo jaune sur un chemin de terre, en lisière de champ, dans la brume du matin."
  - image: bts-06.jpg
    alt: "Détail d'une sacoche de cadre en toile de lin brute, son étiquette cousue et ses sangles noires."
  - image: bts-09.jpg
    alt: "Allée centrale d'un atelier de tissage, deux rangées de métiers à tisser sous les néons."
  - image: bts-04.jpg
    alt: "Un homme présente à bout de bras une sacoche de cadre en lin, debout dans un champ de lin en fleurs."
  - image: bts-12.jpg
    alt: "Un ouvrier en blouse claire surveille une ligne de bobines de fil dans une filature."
  - image: bts-07.jpg
    alt: "Une couturière assemble une pièce de toile de lin à la machine, dans un atelier de confection."
  - image: bts-08.jpg
    alt: "Vue d'ensemble d'un atelier de confection, plusieurs postes de couture alignés sous les néons."
  - image: bts-10.jpg
    alt: "Une sacoche de cadre en toile suspendue dans l'allée d'un atelier de tissage, machines floues à l'arrière-plan."
  - image: bts-11.jpg
    alt: "Un groupe de cyclistes de dos sur une piste cyclable couverte de feuilles mortes, sous une allée de platanes."
  - image: bts-14.jpg
    alt: "Bottes de lin fraîchement arrachées, tiges et capsules étalées au sol."
  - image: bts-15.jpg
    alt: "Un cycliste casqué progresse derrière un champ de blé, sous un ciel couvert."
  - image: bts-13.jpg
    alt: "Gros plan sur des bobines de fil de lin écru, marquées d'un repère orange."

# Ne sont pas dans ce fichier, et n'ont pas a y etre saisies : l'adresse
# e-mail, qui vient de [params] de hugo.toml, et les deux realisateurs, qui
# viennent de data/equipe.yaml.
---

Fondé en 2016 par Grégory Mignard et Jeremy Janin, Captain Yvon est un studio de création visuelle dédié à la vie en plein air et à l'aventure. Nous racontons les histoires de ceux qui vivent, travaillent et s'épanouissent dans la nature. Nous travaillons entre Brest et Lille, et partout où le sujet nous emmène.

Nous collaborons avec des agences, des destinations touristiques et des marques engagées, sur des projets qui célèbrent l'humain et son territoire. Notre travail a été distingué à plusieurs reprises en festival et dans les milieux de la communication et du tourisme.

Nous ne mettons pas en scène. Nous prenons le temps, nous écoutons, nous attendons la lumière. Notre expérience du documentaire nous a appris à capter les moments honnêtes plutôt que les poses forcées, et à composer avec ce que la nature offre quand la météo tourne ou que la marée change. Nous sommes à l'aise à terre, sur l'eau et en l'air, et nous nous adaptons aux conditions plutôt que de les combattre.

Nous ne cherchons pas la perfection technique mais la vérité d'un instant. Une lumière qui baisse trop vite, un visage à contre-jour, un mouvement qu'on n'avait pas prévu. Nous ne corrigeons pas ces accidents, nous les accueillons. C'est souvent dans ce léger écart avec l'image idéale que quelque chose de vrai se glisse. Le son suit la même logique : nous l'enregistrons avec le même soin que l'image, parce qu'un film sans matière sonore n'est qu'une belle image muette.

Pas d'agence, pas d'interlocuteurs multiples. Vous travaillez avec ceux qui font les images, de la conception à la livraison. Tout notre matériel tient dans un sac à dos. Cette légèreté nous rend discrets : on entre dans un atelier, sur un bateau, dans une cuisine, sans transformer l'endroit en plateau. Elle nous laisse aussi une liberté totale, celle de rester quand la scène se prolonge et de partir quand elle est finie.

Le résultat, c'est une image qu'on pourrait regarder dans dix ans sans rougir. Pas parce qu'elle suit une mode, mais parce qu'elle cherchait quelque chose de juste.
