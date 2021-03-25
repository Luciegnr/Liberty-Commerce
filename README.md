# Liberty Commerce

## Consignes

Vous décidez de monter votre propre entreprise d'e-commerce.

L'objectif de ce projet sera grâce au framework Laravel de monter le site de votre boite.

## Etape 1

### Les pages d'authentification

Vous allez donc commencer par préparer les maquettes de 3 de ces vues :

* login.html : Page de connexion, un formulaire avec email + password.
* register.html : Page d'inscription, un formulaire avec nom + email + password + confirmation password.
* reset.html : Page d'oubli de mot de passe, un formulaire pour rentrer un email uniquement.

### Layout

Vous allez donc préparer le layout que vous utilisez.

* header.html : Votre header va devoir contenir le menu de votre site. Vous le ferez évoluer au fur et à mesure que vous ferez les maquettes de vos pages. Les liens de votre menu ne doivent pas fonctionner il s'agit d'une maquette, mais préparez tout pour la suite du projet.
    * Tout à gauche de votre menu, mettez le nom de votre site.
    * Tout à droite, préparez le fait de noter le nom de l'utilisateur connecté.
* footer.html : Votre footer sera très simple.
    * Faites un bloc uni avec deux icônes (Twitter et Facebook).
    * Les deux icônes doivent être cliquables et enverront vers les hypothétiques réseaux sociaux de votre entreprise.

### Catalogue

Dans cette page, vous préparerez le listage de tout votre catalogue de vente.

* Créez un bloc pour chaque produit, composé d'une photo du produit, d'un titre, d'un bouton lien vers la page produit ainsi qu'un bouton "Achat Direct"
* Pour remplir cette page pour le moment, faites en sorte d'afficher 4 blocs "produit" par ligne sur 3 lignes

### Page Produit

Sur cette page devra obligatoirement apparaitre :

* l'image du produit, mais dans un format plus grand que sur la page catalogue
* le titre du produit
* sa description
* son prix
* la catégorie de produit auquel il appartient

Rajoutez un bouton pour acheter le produit. Il faudra aussi où vous voulez afficher le stock de ce produit encore disponible.

### Panier

Vous réalisez un tableau en HTML, qui contiendra 3 colonnes :

* le titre du produit
* le prix
* le nombre d'unités voulues

### Admin

Vous allez réaliser une page admin.html qui par la suite ne sera accessible qu'à l'administrateur du site.

Cette page servira à ajouter de nouveaux produits dans votre site.

Au vu des demandes pour les maquettes des autres pages, faites le formulaire qui va permettre de rajouter un nouveau produit à votre site.


## Etape 2

### Création des migrations

Générer les migrations de votre base de données.

### Mise en place des models

Maintenant que votre base de données est prête, vous allez mettre en place les models.

Quelques petites règles :

* Créez les models dans app/Model.
* Établissez les relations entre les models.

## Etape 3

### Mise en place des maquettes auth

Vous allez commencer par utiliser les maquettes d'authentification login.html, register.html et reset.html et vous allez ainsi adapter les vues existantes.

Étudiez bien le layout fourni de base, car il contient pas mal d'informations et d'aides qui vous seront utiles. N'oubliez pas d'en profiter pour lier tous vos fichiers CSS, qui devront être placés dans public/css. Vous trouverez dans le layout des exemples pour les lier.

Vous allez devoir ensuite faire en sorte qu'à l'inscription un rôle 'non-admin' soit donné à l'utilisateur. Vous avez plusieurs façons de faire, soit grâce à la structure de votre table user, soit en modifiant la création automatique faite par Laravel.

### Mise en place de votre layout

En repartant de votre maquette, vous allez modifier le layout de base afin d'intégrer le vôtre.

Certaines parties du layout changeront selon l'état d'authentification de l'utilisateur :

* S'il n'est pas connecté, on ne doit voir apparaître dans la partie haute que le nom de votre site ainsi qu'un petit logo
* S'il est connecté, on doit voir le nom et le prénom de l'utilisateur en cours, ainsi qu'un bouton de déconnexion, tout à droite de votre barre de navigation

La partie basse de votre layout devra rester comme sur les maquettes.

### Page Admin

Faites en sorte que sur /admin, on arrive sur le formulaire pour créer un produit.

Vous devez renseigner :

* un titre,
* une description,
* une photo,
* un stock.

À la validation du formulaire, le produit est rajouté à la base de données.

### Page Catalogue

Une fois authentifié, faites en sorte d'être redirigé sur votre catalogue. Comme pour votre maquette il s'agit d'une liste de tous les produits disponibles.

Prévoyez en plus un bouton pour accéder à votre panier. Sur le bouton on doit voir le nombre d'éléments déjà présents dans le panier.

Si on clique sur achat directement, on est redirigé vers le panier qui aura été mis à jour avec le nouveau produit. Si on clique sur description, on arrive sur la page du produit.

### Page Produit

Affichez les infos en base de données du produit sur la page du produit.

Si l'utilisateur connecté est admin, rajouter à côté du stock produit un formulaire pour le mettre à jour. À la validation, on revient sur le produit en question après la mise à jour en base de données.

### Panier 

* Faites en sorte que le panier visible soit celui en cours
* Faites en sorte de pouvoir supprimer les éléments du panier
* Affichez le total de la commande
* Faites un bouton "Payer" qui enregistre la commande en base de données (vous allez devoir donc créer une nouvelle table, un nouveau modèle et une nouvelle migration)

## Etape 4

### Autorisation des cookies

Suite à la mise en place de la RGPD, vous avez dû remarquer que sur les sites internet un pop-up est présente pour valider l'autorisation d'utiliser les cookies.
Il faudra donc que vous mettiez en place un cookie "check_popup". S'il n'est pas renseigné, affichez le pop-up. Et à la validation de le popup mettez à jour le cookie pour qu'il n'apparaisse plus.

![](https://i.imgur.com/aLEWbdd.png)

![](https://i.imgur.com/K9vuKnK.png)

![](https://i.imgur.com/vYs9cT6.png)

![](https://i.imgur.com/37pB6dZ.png)
