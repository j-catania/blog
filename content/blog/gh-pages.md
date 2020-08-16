---
title: "Initiation au Github Pages"
date: 2020-08-16T18:58:47+02:00
slug: "github-pages-frontend-deployement"
description: "Initiation au Github Pages"
keywords: [github, pages, deployment]
draft: true
tags: [github, pages, actions]
stylesheet: "post.css"
---

Lorsque nous travaillons dans une architecture Front/BackEnd, le FrontEnd ne se réduit plus qu'à un simple ensemble de fichiers.

Ces fichiers seront téléchargés par le navigateur et ce sont les instructions de ces fichiers qui feront toute l'intelligence.
Aucun calcul ou traitement n'est alors effectué par l'hébergeur.

[**Github**](https://github.com/) a alors créé un outil à la base utiliser pour héberger les documentations d'application.

[**Github Pages**](https://pages.github.com/) utilise Jekyll et fournit des fichiers statique. Tout simplement.

Finalement, nous pouvons utiliser n'importe quel framework FrontEnd, compiler le site et il nous restera plus qu'à herberger le résultat dans Github Pages

## Déploiement d'une documentation
Comme nous le disions, Github Pages est prévu pour héberger des documentations.

Ce sera notre première étape.

Vous devez sans doute avoir un repository sur Github (privé ou public)

Pour commencer, nous allons créer un dossier _docs_ à la racine puis y mettre un fichier index.html.
On add/commit/push et le dossier est disponible sur notre repo Github.

Nous allons terminer par dire à Github de créer une _Page_ sur ce dossier-là.
Pour cela, rendez-vous dans les _Settings_ de notre repo.

On descend un petit peu jusqu'à la section _GitHub Pages_.
Dans la partie _Source_ nous y trouverons une liste. C'est ici que se fera toute la magie.

![Affichage des différentes options](/static/blog/gh-pages/first-step.png)

Nous avons 3 choix possibles :

1. _master branch_ : Ceci va héberger vos fichiers disponibles à la racine de la banche master (s'il n'existe pas d'index.html, la première page sera le readme)
2. _master branch /docs folder_ : Celui-ci va prendre votre branche master mais ne déployer que les fichiers présents dans le dossier _docs_
3. _None_ : Désactivation de GitHub Pages

Lorsque nous choisissons une des deux premières options, Github va immédiatement prendre en compte le choix.

Il va également en profiter pour vous donner le lien qui vous permettra d'acéder aux fichiers hébergés. 
Attention, le temps de déploiement peut prendre quelques minutes et n'oubliez pas de vider vos caches :smile: 

![Affichage des différentes options](/static/blog/gh-pages/show-url.png)

Maintenant que nous avons commencé à utiliser la puissance de GitHub Pages, on se dit que nous pouvons aller beaucoup plus loin !

La suite dans un autre post :star: 


