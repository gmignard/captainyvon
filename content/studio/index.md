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
  - image: bts-cys_1.webp
    alt: "Deux femmes assises à une table de pique-nique en montagne, thermos et caméra posés devant elles, la vallée en contrebas."
  - image: bts-cys_2.webp
    alt: "Deux mains engagent un film argentique dans un dos moyen format, posé sur une valise de transport marquée Captain Yvon."
  - image: bts-cys_5.webp
    alt: "Un opérateur filme un cycliste qui se change au bord d'un muret de pierre, face à l'océan au crépuscule."
  - image: bts-cys_12.webp
    alt: "Une silhouette seule debout sur un plateau rocheux au bord de la mer, dans la lumière rasante du soir."
  - image: bts-cys_4.webp
    alt: "Un surfeur en combinaison remonte une plage recouverte de neige, le village et la falaise derrière lui."
  - image: bts-cys_3.webp
    alt: "Un opérateur accroupi filme un troupeau de moutons dans les herbus, le Mont-Saint-Michel à l'horizon."
  - image: bts-cys_9.webp
    alt: "Deux pieds nus en combinaison sur le sable mouillé, à côté de palmes jaunes et d'un caisson étanche."
  - image: bts-cys_6.webp
    alt: "Un opérateur cadre au moniteur déporté, micro monté sur la caméra, dans la lumière rose de fin de journée."
  - image: bts-cys_10.webp
    alt: "Deux surfeurs en combinaison remontent la cale, l'un portant une planche blanche, l'autre un caisson photo."
  - image: bts-cys_7.webp
    alt: "Un homme filme debout sur une pointe rocheuse balayée par la neige, la mer blanche derrière lui."
  - image: bts-cys_14.webp
    alt: "Une main tend un enregistreur et ses micros au-dessus d'un ruisseau bordé de pierres rouges."
  - image: bts-cys_8.webp
    alt: "Un photographe assis sur un rocher, son appareil et sa casquette posés dans la végétation rase."
  - image: bts-cys_13.webp
    alt: "Un photographe progresse entre des sapins chargés de neige, appareil autour du cou."
  - image: bts-cys_18.webp
    alt: "Un appareil photo couvert de neige, suspendu à sa sangle sur une veste kaki."
  - image: bts-cys_15.webp
    alt: "Un preneur de son tient une barrette stéréo à deux micros, casque aux oreilles, devant un dériveur à la tombée du jour."
  - image: bts-cys_11.webp
    alt: "Deux hommes adossés à un vieux panneau de bois dans les dunes, sous un ciel gris."
  - image: bts-cys_19.webp
    alt: "Un opérateur cadre sous la pluie, gouttes d'eau sur l'écran du moniteur déporté."
  - image: bts-cys_16.webp
    alt: "Un preneur de son accroupi oriente ses micros vers le port, les lumières des quais dans le fond."

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
