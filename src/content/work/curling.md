---
title: jeu de curling
publishDate: 2020-03-02 00:00:00
img: /assets/curling.jpg
img_alt: Iridescent ripples of a bright blue and pink liquid
description: |
  Ce jeu a été developper dans le cadre d'un projet de Licence.
tags:
  - Design
  - Dev
  - User Testing
---

## Presentation du jeu

Le projet consiste à réaliser le jeu de curling , il est constitué des manches appelés « ends ».
Lors de chaque manche , chaque joueur a droit à cinq pierre . le joueur de chaque équipe joue alternativement .
Lors du jet de la pierre, celle-ci doit être relâchée au milieu de la piste avant que la ligne du jeu soit atteinte.
A chaque tir , deux joueurs de chaque balais la piste a l’avancée de la pierre pour modifier sa trajectoire ou augmenter la distance.
  

## Modélisation

#### Piste
La piste est constituée d’un plateau et deux maisons .
Pour modéliser le plateau nous avons utilisé l’objet géométrique PlaneGeometry.
Pour les maisons nous avons créé trois anneaux de même centre dont l’objet géométrique est RingGeometry, et regroupé dans un groupe appelé GroupRing . Pour afficher les deux maisons sur le plateau on a créer une fonction du nom anneaux qui retourne le GroupRing. Pour le positionnement des maisons sur le plateau on a effectué une translation de X en 8 et -8.

#### Balaie

Pour modéliser le balaie on choisit 3 objets géométrique : un parallélépipède pour le rectangle, un
cylindre pour le manche et des cônes des révolutions pour les poils.
Pour le parallélépipède on a utilisé l’objet géométrique BoxGeometry qui a comme paramètre la largeur, la hauteur et la profondeur . Le rectangle a pour coordonné 2 pour la largeur et 0.3 pour la hauteur.
Le cylindre est modélisée en utilisant CylinderGeometry et comme coordonnées 0.1 pour le rayon d’en haut, 0.1 pour le rayon d’en bas et 3 pour la hauteur. Pour maintenir droit le cylindre nous avons fait une rotation de 90° (PI/2) par rapport à X.
Pour les poils nous avons eu besoin 16 cônes du type ConeGemetry qui sont tous de même hauteur, largeur et taille et sont placés tout au long du rectangle.
Pour faciliter le maniement de notre balaie ,les objets géométriques sont mis dans un groupe du nom balaie .
Aenean pretium purus augue, ut bibendum erat convallis quis. Cras condimentum quis velit ac mollis. Suspendisse non purus fringilla, venenatis nisl porta, finibus odio. Curabitur aliquet metus faucibus libero interdum euismod. Morbi sed magna nisl. Morbi odio nibh, facilisis vel sapien eu, tempus tincidunt erat. Nullam erat velit, sagittis at purus quis, tristique scelerisque tortor. Pellentesque lacinia tortor id est aliquam viverra. Vestibulum et diam ac ipsum mollis fringilla.

#### Pierre
Pour modéliser la pierre nous avons utilisées deux lathe, un cylindre et un tore.
Pour la conception des lathes on a utilisés deux courbes de Bézier de dégrée 3.

Pour le cylindre on a utilisé l’objet géométrique CylinderGeometry , la modélisation du tore est faite pour relier le cylindre au lathe.
Le tore à pour centre un point qui prend en coordonnée l’abscisse du point qui débute la cylindre et pour ordonnée l’ordonnée du dernier point de contrôle du lathe intermédiaire. le rayon du tore est la distance entre le centre du tore et le dernier point de contrôle .

#### Animation
Pour mettre en marche le jeu , il faut d’abord sélectionner la trajectoire désirée. Après le choix du trajectoire, si le choix est une courbe on peut modifier la trajectoire dans le menu avec l’option courbure ou point d’arrivé . si le choix est porté sur la trajectoire rectiligne, on procède au déplacement du point. Le lancement de la pierre s’effectue seulement à l’appui de l’option « lancer » dans le menu. Quand le joueur sélectionne un trajectoire courbe il à la possibilité de modifier sa trajectoire durant le déplacement de la pierre. Durant un déplacement en courbe le balaie apparait .


