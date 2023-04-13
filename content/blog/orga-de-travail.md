---
title: "Organisation de travail"
date: 2023-04-13T11:22:31+02:00
slug: ""
description: ""
keywords: ["git", "github", "workflow", "release"]
draft: true
tags: ["github", "workflow"]
math: false
toc: true
stylesheet: "post.css"
mermaid: true
---

## Introduction
Nous codons tous les jours, mais si nous n'avons pas une organisation de travail où tous les cas sont prévus,
il est vite possible de se sentir bloqué.

C'est pourquoi je vais vous décrire dans cet article ma manière de travailler au quotidien.

Tout va y passer :
* [Création d'une feature](#création-dune-feature) : on ajoute une fonctionnalité
* [Correction d'un incident urgent](#correction-dun-incident-urgent) : on corrige un bug
* [Création d'une release](#création-dune-release) : on fige la version
* [Livraison](#livraison) : on livre une release

## Globalement
{{< mermaid >}}
flowchart LR
subgraph localhost
lA[commit fa:fa-hashtag 1] --> lB[commit fa:fa-hashtag 2]
lB --> lC[commit fa:fa-hashtag 3]
end
lC --> |fa:fa-bolt PUSH| GHAA
subgraph GHA[Github Actions]
GHAA[Intégration\ndu code]
GHAA --> BHAB[Déploiement \nen staging]

    GHAC[Demande \nd'une release] --> GHAD[Validation du code]
    GHAD --> GHAE[Release]
    GHAE --> GHAF[Création du PA]
    GHAF --> GHAG[Dépôt du PA \ndans le registre]
end
subgraph DEP[GHA/AWX/A4C/Helm/Rancher]
DEPA[Demande \nd'une livraison] --> DEPB[Renseignement\nEnv ?\nVersion ?]
DEPB --> DEPC[Récupération du PA\nen VERSION x.y.z\ndepuis le registre]
DEPC --> DEPD[Livré]
end
GHAG <--> DEPC

style GHA fill:#2088FF
style GHA color:white
style DEP fill:#EE0000
style DEP color:white
{{< /mermaid >}}

## Création d'une feature

{{< mermaid >}}
flowchart LR
A[Création d'une branche\nnom : feature/FEAT_NAME\ndepuis : main] --> B[Création d'une PR]
B --> C(Commits locaux ...)
C --> |fa:fa-bolt PUSH| D{CI}
D --> E[head]
D --> F[merge]
E --> |fa:fa-circle-xmark| FAIL[Terminé ERR]
E --> |fa:fa-circle-check| CIOK[Terminé OK]
FAIL --> |corrections|C
F --> |fa:fa-circle-xmark| FAIL
F --> |fa:fa-circle-check| CIOK
CIOK --> |fa:fa-bolt SQUASH PR| DONE(Déclanchement \nCI Main)
CIOK --> |complément| C
{{< /mermaid >}}
## Correction d'un incident urgent

{{< mermaid >}}
flowchart LR
A[Création d'une branche\nnom : hotfix/FIX_NAME\ndepuis : TAG] --> B[Création d'une PR \nsur main]
B --> C(Commits locaux ...)
C --> |fa:fa-bolt PUSH| D{CI}
D --> E[head]
D --> F[merge]
E --> |fa:fa-circle-xmark| FAIL[Terminé ERR]
E --> |fa:fa-circle-check| CIOK[Terminé OK]
FAIL --> |corrections|C
F --> |fa:fa-circle-xmark| FAIL
F --> |fa:fa-circle-check| CIOK
CIOK --> |Validé| RLS(RELEASE)
RLS --> |fa:fa-bolt SQUASH PR| DONE(Terminé)
CIOK --> |complément| C
{{< /mermaid >}}
## Création d'une release
{{< mermaid >}}
flowchart LR
A[Demande d'une\nrelease] --> E[Renseignement\nVersion ?]
E --> B{CI main}
B --> |fa:fa-circle-xmark| FAIL(Terminé ERR)
B --> |fa:fa-circle-check| C[Génération\ndu PA]
C --> |fa:fa-circle-check| D[Dépot du PA\n dans le registre]
D --> |fa:fa-circle-check| DONE(Terminé OK)

{{< /mermaid >}}
## Livraison
{{< mermaid >}}
flowchart LR
A[Demande de\nlivraison] --> B[Renseignement\nEnv ?\nVersion ?]
B --> C[Récupération\ndu PA dans la bonne version]
C --> D[Installation]
D --> DONE(Terminé OK)

{{< /mermaid >}}
