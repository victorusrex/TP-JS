
# TP n° 2 & 3  - Pokedex

Ces travaux pratiques ont été réalisés dans le cadre de le module R3-01 – Vue JS encadré par Monsieur Antoine OFFROY.




# Sujet
Nous avions comme consigne de réaliser en vue.js un pokedex rassemblant l'ensemble des Pokemons liés à l'API "__Pokebuild__" de manière dynamique. 


# Réalisations

Avant de parler de ma façon de procéder, je veux juste indiquer que j'ai réalisé le TP3 jusque la __question 4__.

Tout d'abord, nous avons dû créer les composants suivants afin de réaliser ce pokédex :

- __App.vue__  qui permet l'affichage des autres composants.

- __Pokedex.vue__ qui nous permet d'afficher l'ensemble des pokémons avec leurs noms, leurs types et une couleur de fond de la carte qui correspond au type primaire.

En plus de cela, pour répondre à la deuxième question du TP n°3 j'ai rajouté avant le pokédex un champ de type input qui va permettre à l'utilisateur de choisir le nombre de pokémons qu'il souhaite voir sur la page. Une valeur de __20__ a été déclarée par défaut et un minimum d'__un__ pokémon a été marqué pour le champ de saisie.

- __Pokemon.vue__ qui est utile afin de définir le type et la couleur respective du pokémon.

- __ListesTypesPokemon.vue__ qui permet l'affichage des différents types des pokémons présents retournés ainsi que leur nombre d’occurrence.

- __DetailsPokemons.vue__ qui détaille les informations d’un pokémon sélectionné sur une nouvelle page (route) ce qui entraîne la création du fichier __route.js__ et __main.js__ qui sont tous deux là pour configurer les routes pour la navigation à l'intérieur de l'application.

- __Footer.vue__ qui est la réponse à la question 1 du TP n°3 qui indique mon nom, ma promotion afin d'identifier plus facilement l'auteur du TP.

Ensuite, il fallait simplement améliorer le style global de la page en terme d'esthétique. Pour cela, nous avons agrémenté mon code avec du CSS pour le style.

## Auteur

FOURNIER Victor

BUT 2 - TD 1 / TP A 

Rendu le 28 janvier 2024
