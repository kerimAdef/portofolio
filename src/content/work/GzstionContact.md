---
title: Gestions des contacts
publishDate: 2019-10-02 00:00:00
img: /assets/stock-4.jpg
img_alt: Soft pink and baby blue water ripples together in a subtle texture.
description: |
  Cete application permet de gerer les contacts en interagissant avec une base des données
tags:
  - Design
  - Branding
---
### Presentation
Cet application a été conçu en c++ via qtcreator ,son but est de permettre à un utilisateur des gerer des contacts.Il peut ajouter , supprimer ,modifer ou rechercher un contact.
##### Construction de l'interface IHM et fonctionnnement de l'application

Dans notre Application nous avons utilisé 5 interfaces dont les rôles sont les suivantes. Une interface principale qui est le mainwindow construit comme un formulaire qui contient un bouton affiche qui nous permet d’afficher tous nos contacts contenu dans la base des données. L’action de ce bouton déclenche un slot clicked.
Une table view qui sert comme table pour afficher les contacts une fois le bouton affiche cliqué.
Pour que les contacts contenus dans la base soit afficher dans la table nous avons fait appel à notre base de données en créant une variable nommée condb de type bdd(classe de la base des données) . Après on la connecte à la base grâce à connectBD(fonction qui permet de se connecter à la base) et ensuite on crée une requête query qui va selectionner tout ce qui est dans la table contact de notre base .
Un bouton recherche avec une ligne de texte qui permet de rechercher un contact dans la base. Pour effectuer cette recherche l’utilisateur doit saisir soit le nom, prénom ou l’entreprise d’un contact puis cliquer sur le bouton recherche . Une fois le bouton cliqué ,elle  déclenche une action qui contient une requête pour sectionner dans la base l’information saisi par l’utilisateur puis l’afficher dans la table view. Pour récupérer les données saisies par l’utilisateur nous avons initialisé une variable rech de type QString sur laquelle on récupère comme un texte les données saisies par l’utilisateur .En plus on a 4 menus qui sont des slots et qui ont comme action triggerd(action de déclenché) qui seras connecter avec nos 4 interfaces restantes qui sont des QDialog.
Une deuxième interface nommée dialolog_ajout qui est un QDialog.
Dans cette interface on a un formulaire dans la quelle il contient 6 lignes de texte (nom,prenom,mail,entreprise,telephone,et photo) qui permettent à l’utilisateur de saisir les données nécessaires pour créer un contact. Un bouton ajout qui est un slot et a comme action clicked. Une fois les informations saisies et le bouton cliqué la requête qui permet d’insérer ses informations dans la base est exécuter. Pour récupérer les informations saisis nous allons instancier deux pointeur, un nommé con de type contact et un deuxième lc de type listContact. Le premier il récupère grâce au setter du classe contact les infos saisis dans le formulaire et le deuxième l’ajoute au liste des contact grâce à la méthode ajoutContact() .
Par la suite on a un autre interface nommé dialog_ajout_modif de type QDialog qui a pour rôle de modifier ou de supprimer un contact. Dans cette interface on a les mêmes lignes de texte que la précédente a l’exception d’une nouvelle nommée id qui permet à l’utilisateur de saisir l’identifiant du contact à supprimer ou à modifier, en plus on deux a bouton nommer modifie et supprimer.
Pour pouvoir supprimer on doit saisir d’abord l’identifiant du contact à supprimer puis en suite cliquer sur le bouton supprimer , une fois ce bouton cliquer il déclenche un slot qui contient une requête SQL permettant de supprimer un contact si l’identifiant saisis par l’utilisateur correspond à celui de la base. Tandis que pour pouvoir modifié l’utilisateur doit saisir l’identifiant du contact et les infos à modifier puis par la suite cliquer le bouton modifier qui déclenche le slot qui contient la requête update qui permet de modifier un contact si les infos saisis correspondent à celle contenu dans la base.
Ensuite on a une interface dialog_interaction qui permet à l’utilisateur d’ajouter une interaction a un contact . Celle-ci contient 3 lignes de texte permettant à l’utilisateur de saisir l’identifiant du contact, le contenu et la date d’interaction.
Une fois les infos saisis l’utilisateur doit cliquer sur le bouton ajout qui déclenche un slot contenant une requête permettant à l’utilisateur d’insérer une interaction. En plus l’utilisateur peut chercher une interaction par son date ou l’identifiant de son contact. 
En fin un interface dialogtodo qui permet d’ajouter des tags à une interaction.
##### Base des données

Dans cette partie nous avons implémenté une base de données nous permettant d’ajouter des contacts des interactions ou des tags.
Dans notre base nous avons créé 3 tables, une table nommée contact composée de 6 colonnes. Ses colonnes contiennent respectivement : un identifiant id de type entier qui est une clé primaire auto-incrémentant, une deuxième nommée nom qui est une chaîne de caractères non nul. Et pour le reste respectivement nommé prénom,entreprise,mail,téléphone et photo qui sont également des chaînes de caractères. Une deuxième table interaction qui a un identifiant id clé primaire qui s’auto-incrémente, un deuxième identifiants idcontacts qui est une clé étrangère au table contact.
En plus de sa on a deux colonne respectivement contenu et date interaction qui sont des chaînes des caractères. Une dernière table todo qui a aussi un identifiant id clé primaire auto-incrément et un deuxième identifiants idinteraction qui est une clé étrangère à la table interaction, en plus de cela on a deux variables de type text qui permettent de stocker le tag et la date d’une interaction


