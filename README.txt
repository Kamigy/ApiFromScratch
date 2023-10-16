Création d'un site web et de son API Rest avec authentification dans le cadre d'un projet de cours.
Utilisation de MongoDB pour la BDD & JS pour le code.

Ressources :

Jeux:

id (identifiant unique)
titre
description
prix
genre (ex: action, aventure, RPG, etc.)
plateforme (ex: PC, PS5, Xbox, etc.)
image/couverture
stock (quantité disponible)


Utilisateurs:

id (identifiant unique)
nom
prénom
email
mot de passe (hashé pour des raisons de sécurité)
rôle (ex: utilisateur, administrateur)
historique d'achats


Commandes:

id (identifiant unique)
idUtilisateur (lien vers l'utilisateur qui a passé la commande)
date
total
statut (ex: en attente, expédiée, livrée, etc.)
jeux commandés (potentiellement une table de liaison pour gérer les relations "plusieurs à plusieurs" entre les jeux et les commandes)


Avis:

id (identifiant unique)
idUtilisateur (lien vers l'utilisateur qui a laissé l'avis)
idJeu (lien vers le jeu concerné)
note (ex: sur 5 ou 10)
commentaire


Panier (optionnel, si vous souhaitez avoir une fonctionnalité de panier) :

id (identifiant unique)
idUtilisateur
jeux dans le panier

CONTROLEURS : 

a. Contrôleur pour les Jeux:

Create: Ajoute un nouveau jeu à la base de données.
Read:
Récupère un jeu spécifique par ID.
Récupère tous les jeux ou selon certains critères (par genre, plateforme, etc.).
Update: Modifie un jeu spécifique (titre, description, prix, etc.).
Delete: Supprime un jeu par ID.


b. Contrôleur pour les Utilisateurs:

Create: Inscription d'un nouvel utilisateur.
Read:
Récupère un utilisateur par ID.
Récupère tous les utilisateurs (peut être utile pour l'administration).
Update: Modifie les informations d'un utilisateur (nom, email, mot de passe, etc.).
Delete: Supprime un utilisateur par ID.


c. Contrôleur pour les Commandes:

Create: Crée une nouvelle commande.
Read:
Récupère une commande par ID.
Récupère toutes les commandes d'un utilisateur spécifique ou toutes les commandes.
Update: Modifie le statut d'une commande ou d'autres détails.
Delete: Supprime une commande par ID.


d. Contrôleur pour les Avis:

Create: Ajoute un nouvel avis pour un jeu.
Read:
Récupère tous les avis pour un jeu spécifique.
Récupère un avis par ID.
Update: Modifie un avis (note, commentaire).
Delete: Supprime un avis par ID.


e. Contrôleur pour le Panier :

Create: Ajoute un jeu au panier.
Read: Récupère les jeux dans le panier d'un utilisateur.
Update: Modifie la quantité d'un jeu dans le panier ou ajoute/supprime un jeu.
Delete: Supprime un jeu du panier ou vide le panier.