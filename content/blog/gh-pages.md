---
title: "Déploiement d'un FrontEnd grâce à GitHub Pages"
date: 2020-06-15T09:29:07+02:00
slug: "github-pages-frontend-deployement"
description: "Déploiement d'un FrontEnd grâce à GitHub Pages"
keywords: [github, pages, frontend, deployment]
draft: true
tags: [github, frontend]
stylesheet: "post.css"
---

Lorsque nous travaillons dans une architecture Front/BackEnd, le FrontEnd ne se réduit plus qu'à un simple ensemble de fichiers.

Ces fichiers seront téléchargés par le navigateur et ce sont les instructions de ces fichiers qui feront toute l'intelligence.
Aucun calcul ou traitement n'est alors effectué par l'hébergeur.

**Github** a alors créé un outil à la base utiliser pour héberger les documentations d'application.

**Github Pages** utilise Jekyll et fournit des fichiers statique. Tout simplement.

Finalement, nous pouvons utiliser n'importe quel framework FrontEnd, compiler le site et il nous restera plus qu'à herberger le résultat dans Github Pages

## Déploiement d'une documentation
Comme nous le disions, Github Pages est prévu pour héberger des documentations.

Ce sera notre première étape.

Vous devez sans doute avoir un repository sur Github (privé ou public)

Pour commencer, nous allons créer un dossier _docs_ à la racine puis y mettre un fichier index.html.
On add/commit/push et le dossier est disponible sur notre repo Github.

Nous allons terminer par dire à Github de créer une Pages sur ce dossier là.
Pour cela, rendez-vous dans les _Settings_ de notre repo

On descend un petit peu jusqu'à la section _GitHub Pages_
