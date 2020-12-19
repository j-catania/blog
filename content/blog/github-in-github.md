---
title: "Comment GitHub utilise... GitHub ?"
date: 2020-12-15T22:26:36+01:00
draft: true
description: "Découvrons ensemble comment GitHub est utilisé dans le cycle de vie d'un ajout de fonctionnalité"
keywords: [github, pages, deployment]
tags: [github, pages, actions]
---

La vidéo d'opening de la GitHub Universe 2020 est très intéressante.

Je vous laisse la découvrir par vous-même :
<div style="text-align: center">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/2m9nUP-e8Co" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

Nous allons ensemble décortiquer cette vidéo étape par étape.

1. Tout commence par la rédaction d'une idée dans le fil _Discussions_.

Si l'idée convainc alors ils transforment directement la discussion en _Issue_:
![Transformation discussion en issue](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/discussion-to-issue.png)

2. Un fois l'_Issue_ créée, le débat technique est lancé : comment réaliser cette évolution ?

L'_Issue_ est complétée avec toutes les informations requises:
![Renseignement des informations de l'Issue](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/issue-details.png)

3. Un développeur analyse la demande directement depuis le GitHub CLI:
![Visualisation des informations de l'Issue depuis le GH CLI](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/github-cli-view-issue.png)

4. Elle continue en créant une Branche, installe la dépendance NPM et termine par commiter tout ça:
![Création de la branche Git en local](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/branch-creation.png)

5. Grâce au _GitHub CLI_ elle crée directement la PR sur le projet:
![Création de la PR depuis GH CLI](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/pull-request-creation.png)

6. C'est parti pour la réalisation directement dans la PR :
![Ça bosse dur 01](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/working-hard-01.png)
![Ça bosse dur, encore](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/working-hard-02.png)

7. Une fois terminé, une vérification des vulnérabilités dans les dépendances NPM est réalisée directement depuis la PR:
![Vérification des dépendances](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/dependencies-verification-before-merging-request.png)

8. Cette évolution utilise énormément la dépendance NPM P5.js. L'équipe de développement voulant que le code soit maintenu, ils décident alors de financer celle-ci:
![Sponsoring P5.JS](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/sponsoring-p5js.png)

9. Maintenant que le développement est terminé, ils peuvent passer la PR en 'Ready for Review' :
![Passage en Ready for Review de la PR](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/ready-for-review.png)

10. La CI vérifie que tout soit OK :
![Checks ok](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/checks-ok.png)

11. La PR peut maintenant être intégrée à la branche principale.

12. Ryan valide l'intégration dans la branche principale
    * Mais il y a un soucis, la lettre 'h' de GitHub est en minuscule. Il décide de corriger lui-même depuis sont iPad avec Codespaces :
![Correction depuis Codespaces](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/codespaces.png)
    
    * La Pull Request peut être validée :
![Pull Request validée](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/pull-request-approved.png)
    
13. Une release peut être créée :
![Création d'une release](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/release-creation.png)

14. C'est maintenant que GitHub Actions entre en scène :
    * Voici le workflow utilisé :
![Workflow GitHub Actions](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/continiuous-deployment.png)
    1. Construction de l'application et de la documentation
    2. Déploiement en environnement de test (staging)
    3. Déploiement en environnement de production
    * L'environnement de staging est prêt :
![Environnement Staging prêt](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/staging-deployed.png)
    * L'environnement de production quant à lui a une 'Protection rule' :
![Protection Rules environnement de production](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/production-environement-rules.png)
_Ici, seul les utilisateurs de la team *octocademy/dev* pourrons valider le déploiement de cet environnement_
    * Une fois la version validée en environnement de staging, les utilisateurs valident le déploiement en production :
![Validation du déploiement en production](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/production-deployment-validation.png)
    * L'environnement de production est déployé en 15 secondes :
![Production déployée](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/production-deployed.png)
    * L'Issue peut maintenant être fermée :
![Fermeture de l'Issue](http://kim.jcatania.io/blog-staging/static/blog/github-in-github/closing-issue.png)

L'analyse de la vidéo est maintenant terminée.

J'espère avoir répondu à certaines de vos interrogations sur les process utilisés par GitHub :smile: 

Peace,

Juu' :heart: 
    
    
