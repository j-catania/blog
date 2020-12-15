---
title: "Comment GitHub utilise... GitHub ?"
date: 2020-12-15T22:26:36+01:00
draft: true
---

La vidéo d'opening de la GitHub Universe 2020 est très intéressante.

Je vous laisse la découvrir par vous même:
<div style="text-align: center">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/2m9nUP-e8Co" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

Nous allons ensemble décortiquer cette vidéo étape par étape.
1. Une bonne idée dans GitHub Discussions
    1. Création d'une issue
2. Affichage info de l'issue depuis GH CLI
3. Création d'une branche
    1. Ajout de la dépendance 'p5'
4. Création d'une PR en draft depuis GH CLI
    1. ça bosse dur dans la PR avec échange tout au long du dev
    2. Vérification des vulnérabilités dans les dépendances NPM directement depuis GH
5. Fincancement de la dépendance P5 par GH
6. Passage de la PR en ready for review
7. Auto merge de la PR dans main
8. Review de la PR
    1. Correction du h en H depuis codespaces
    2. PR validée
9. création d'une release
10. GH Actions démarre le workflow
    1. Génération du code et build du code
    2. Déploiement dans l'env de test et validation
    3. Déploiement en production
