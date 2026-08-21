---
title: "Studio"
description: "Captain Yvon Studio, duo de réalisateurs et photographes entre Brest et Lille."

# layout : gabarit dedie, layouts/_default/studio.html. Il scinde ce texte et
# la colonne de contact, puis rend le mur de photos de tournage.
layout: "studio"

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

# Les coordonnees ne sont plus dans ce fichier : la colonne de droite du
# gabarit les rend depuis [params] de hugo.toml et data/pied.yaml.
---

Fondé en 2016 par Grégory Mignard et Jeremy Janin, Captain Yvon est un studio de création visuelle dédié à la vie en plein air et à l'aventure. Depuis près de 10 ans, nous racontons les histoires de ceux qui vivent, travaillent et s'épanouissent dans la nature.

Nous collaborons avec des agences, des destinations touristiques et des marques engagées, en mettant l'accent sur les projets qui célèbrent l'humain et son territoire. Notre expérience dans le documentaire et le tourisme d'attractivité nous permet de capturer l'âme d'un lieu et de révéler ce qui le rend unique. Notre travail a été reconnu à plusieurs reprises dans des festivals et dans les milieux de la communication et du tourisme.

Notre force réside dans notre polyvalence et notre authenticité. Nous sommes à l'aise dans tous les environnements (terre, eau, air) et nous adaptons à toutes les conditions. Que la météo tourne, que la marée change ou que le plan prenne un autre virage, nous composons avec ce que la nature offre. Notre background en documentaire outdoor nous a appris à être patients, à traquer la lumière naturelle et à capturer les moments honnêtes plutôt que les poses forcées. Nous ne sommes pas juste des techniciens : nous vivons ce que nous filmons. Cette immersion nous permet de créer des images qui résonnent, des histoires qui marquent, et des contenus qui traversent le temps. Nous travaillons également avec un réseau de précieux collaborateurs, des gens qui, comme nous, s'épanouissent quand les éléments se déchaînent et que tout ne se passe pas comme prévu. De la conception à la livraison, nous collaborons étroitement avec nos clients pour créer des projets qui leur ressemblent vraiment.
