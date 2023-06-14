+++
title = "Git - Trois espaces, trois temps"
date = "2023-06-14T14:42:50+02:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = []
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
summary = "Git, le Doctor Who du code"
+++

Quand on travaille avec un projet suivi par Git, on joue entre trois espaces,
qui servent à trois temps différents.

## La copie de travail

La première chose dont on a besoin pour un projet Git, c'est le projet,
c'est-à-dire l'ensemble des fichiers et répertoires nécessaires pour votre
application.

Il s'agit de l'ensemble des fichiers et répertoires placés dans le répertoire
qui contient le dépôt (répertoire .git). C'est cela qu'on appelle copie de
travail.

Ces fichiers peuvent être versionnés ou suivis par Git ou non. Si un fichier est
suivi, cela signifie que dans l'historique du dépôt au moins une version
antérieure existe. 

Cette copie de travail sert comme zone où vous allez effectuer vos
modifications, vos créations et suppressions de fichier. Il sert donc à l'étape
de développement.

## Le dépôt (Repository)

C'est le répertoire .git à l'intérieur de votre projet, il contient
l'intégralité de l'historique de votre projet soit l'ensemble des évolutions,
les différentes branches, etc.

Cette espace sert à voyager dans l'historique du projet, il sert comme mémoire
du projet. Il permet d'extraire une copie de travail depuis n'importe quelle
évolution stockée dans l'historique.

## La zone de rassemblement (Staging)

La zone de rassemblement une particularité de Git, c'est une zone qui sert à
mettre en forme ses évolutions avant de les concrétiser dans le dépôt.

Dans les bonnes pratiques Git, on souhaite que nos évolutions enregistrées
soient les plus petits possibles. Cela va faciliter la revue de code,
l'intégration dans les dépôts externes, etc. 

Le staging sert à regrouper les modifications dans des sous-ensembles
cohérentes, il sert comme étape de transition entre les modifications effectuées
dans la copie de travail (fluides) et le dépôt (fixe). C'est grâce à lui que
l'on peut mettre en oeuvre les bonnes pratiques.