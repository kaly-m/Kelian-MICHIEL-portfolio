---
title: etcd_like
subtitle: "Nodes but not Node.js"
summary: "Dans le cadre d'un cours sur la programmation avancée en système, nous avons dû développer une application client serveur selon une architecture distribuée. Le but étant de reproduire le principe de gitlab avec le protocole RAFT"
date: 2026-01-10
cardimage: etcd-logo.jpg
featureimage: etcd-logo.jpg
caption: "etcd : a distributed key-value store"
---

## Contexte

Dans le cadre d'un cours sur la programmation avancée en système, nous avons dû développer une application client serveur selon une architecture distribuée en C. Le but étant de reproduire le principe de gitlab avec le protocole RAFT.

Ce projet a été réalisé en groupe de 4. Nous avions environ 4 - 5 séances de 3h réaliser ce pojet en mode td. Cela correspond a une période d'environ 2 mois comme nous sommes en alternance, seulement 2 semaines par mois en cours.

## Présentation de la solution

etcd_like est, comme son nom l'indique, comme etcd. Je vous invite donc à aller voir le projet etcd et vous renseigner : [joke](https://etcd.io/). Notre solution est donc une application client-serveur suivant une architecture distribuée. Du côté serveur, chaque noeud agit en réalité en tant que serveur et de client à la fois (entre noeuds). Côté client, ce dernier a la possibilité d'envoyer des requêtes GET(récupérer de la donnée) ou PUT(ajouter de la donnée) au serveur.

{{< figArray subfolder="images/raft-com" figCaption="Connexion d'un client aux noeuds serveur (RAFT)" >}}

Le protocole utilisé côté serveur pour l'architecture distribuée est le protocole RAFT. Lorsque les noeuds du serveur sont lancés, une élection commence pour élire un leader. Ce leader sera le seul à avoir les droits en écriture, il sera en charge de propager la données sur les autres noeuds (action: PUT). Quant aux autres noeuds, ils auront seulement les droits en lecture (action: GET). Si le client demande une action PUT à un noeud qui n'est pas leader, ce dernier le redirigera vers le leader pour qu'il refasse sa demande. Si le leader tombe, une élection est relancée pour élire un nouveau leader.

{{< figArray subfolder="images/raft-elec" figCaption="Protocole d'élection du leader (RAFT)" >}}


## Méthodes de travail

Ce projet est versionné sur git à l'adresse : [etcd_like](https://gitlabinfo.iutmontp.univ-montp2.fr/challiase/etcd_like). Nous avons donc suivi un workflow git respectant les standards attendus dans le monde professionnel:\
-> Création d'une issue.\
-> Ouverture d'une merge-request/branche.\
-> développement de la fonctionnalité associée.\
-> review de la merge-request par les collaborateurs du projet.\
-> Merge de la branche créée dans la branche principale (si aucune review négative).

De plus, ce projet s'est fait en plusieurs étapes. Chaque étape apparait sous forme de dossier sur le gitlab, ces étapes sont bien documentées dans le [README](https://gitlabinfo.iutmontp.univ-montp2.fr/challiase/etcd_like/-/blob/master/README.MD?ref_type=heads). Je vous invite donc à aller y jeter un oeil si cela vous intéresse.

## Compétences travaillées

Durant ce projet j'ai pu développer mes compétences en **systèmes distribués** mais aussi en compréhension du fonctionnement des **structures complexes en C**. En effet, envoyer des trames sur le réseau en C est loin d'être une tache simple, il nous a fallu sérialiser la donnée avec des problématiques d'alignement d'octet.

J'ai notamment dû :
- Comprendre le fonctionnement d'un système distribué.
- Apprendre le fonctionnement du protocole RAFT.
- Appréhender des structures complexes en C (comme des union { struct.. } })
- Sérialiser et Déserialiser des structures pour pouvoir les envoyer sur le réseau.
- Gérer une architecture distribuée suivant un protocole professionnel complexe et établi.
