---
title: Burger Time
publishDate: 2019-12-01 00:00:00
img: /assets/stock-2.jpg
img_alt:  le jeu de burgeur tim
description: |
  Le jeu à été développer en java via un Ide (netbeans).
  
tags:
  - Dev
  - Branding
  - Backend
---

Le jeu de BurgeurTime est un jeu des plateformes composée de plusieur échelles et piéges sur la quelle se déplace un cuisinier . Au lancements du jeu un interface  s'ouvre et l'utilisateur à le choix de cliquer le bouton joueur pour lancer une partie ou sur quitter pour fermer le jeu.
Une fois que l'utilisateur à choisir de joueur , il peut deplacer le cuistot en utilsant les flêches du clavier dans un environement constituer des échelles et un plateau. Il peut se deplacer soit horizantalement sur le plateau ou verticalement pour monter les échelles . Durant son parcours le cuistot est poursuivuit par plusieurs énnemmies qui sont des saucisses , salades, steacks et œuf . le cuistot peut soit attaquer les ennemies en cliqueant sur le boutton espace du clavier et gagner 100 points ou soit les éviter . Si les ennemies parviennent à toucher le cuistot il perd une vie , s'il perd tout ces vies(3) la partie est terminée.
Pour réaliser le jeu nous avons créer 8 packages qui sont : console, controle, environnement joueur, media outils, et burgeurTime.
le package console contient deux classe : la classe cage.java et console.java , ensuite le package controle qui contient une classe commandeListener qui fait tout les évenement lier au clavier. le package Environnement  contient 10 classes qui répresente l'environnement du jeu parmis les quelles certaines gére le position du joueur est du burgeur, un classe cuisinier qui contient le nomre de vie du joueur et de son score au départ et qui vérifie aussi si le joueur est vivant ou pas.
