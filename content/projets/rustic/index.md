---
title: Rustic
subtitle: "Rewright everything in Rust !"
summary: "Dans le cadre d'un cours sur la continuité de service, nous devions créer une solution de backup avec pour seule consigne : choisissez votre techno. On s'est donc tournés vers le Rust parceque, pourquoi pas ?"
date: 2025-11-10
cardimage: rust-logo.png
featureimage: rust-logo.png
caption: "The Rust Programming Language"
---

## Contexte

Dans le cadre d'un cours sur la continuité de services nous étudions les solutions à la disposition des entreprises. Un projet nous à été donné avec pour consignes de développer une solution de backup en choisissant la techno de notre choix. Les fonctionnalités de la solution développée étaient libres mais cette dernière devait apporter une réelle plus-value à un simple: ` cp -r ` sur un serveur distant.

Ce projet a été réalisé en groupe de 4 pour notre part, certains étaient deux, d'autres cinq. Nous avions environ 5 - 6 séances de 3h pour analyser l'existant, conceptualiser la solution, la développer puis la tester. Cela correspond a une période d'environ 2 mois comme nous sommes en alternance, seulement 2 semaines par mois en cours.

Une présentation orale devant un "client" était attendue en terme de rendu. Cela nous plonge d'avantage dans une situation réaliste ou il faut livrer une solution convaincante et robuste. Nous avons donc dû articuler nos arguments pour rassurer le client et le convaincre que notre solution était la meilleure parmi les solutions des concurrants (camarades de classe) !

## Présentation de la solution

Rustic est donc une application de backup en CLI (Command Line Argument) qui a pour vocation de compresser de la donnée, de la versionner et de la sauvegarder à l'endroit spécifié par l'utilisateur. Plusieurs fonctionnalités s'offrent à nous :

{{< figArray subfolder="images" figCaption="Fonctionnalités de Rustic" >}}

## Méthodes de travail

Ce projet est versionné sur git à l'adresse : [Rustic](https://gitlabinfo.iutmontp.univ-montp2.fr/michielk/rustic/). Nous avons donc suivi un workflow git respectant les standards attendus dans le monde professionnel:\
-> Création d'une issue.\
-> Ouverture d'une merge-request/branche.\
-> développement de la fonctionnalité associée.\
-> review de la merge-request par les collaborateurs du projet.\
-> Merge de la branche créée dans la branche principale (si aucune review négative).

{{< figArray subfolder="images/workflow" figCaption="Gitlab flow" >}}


## Compétences travaillées

Durant ce projet j'ai pu développer mes compétences en **Rust** mais aussi en compréhension du fonctionnement des systèmes de **backup**. L'apprentissage fut rude, loin d'être terminé mais sur une bonne voie.

J'ai notamment dû :
- Apprendre les fondamentaux du Rust
- Travailler en équipe suivant un workflow bien particulier
- conceptualiser des solutions complexes pour répondre à un besoin rééel
