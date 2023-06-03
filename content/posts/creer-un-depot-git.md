+++
title = "Git - Créer un dépôt"
date = "2023-05-31T14:27:42+02:00"
author = "James"
authorTwitter = "" #do not include @
cover = ""
tags = []
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "red" #color from the theme settings
summary = "La vie commence avec git init."
+++

## Créer un dépôt Git en partant de rien

La première étape de toute manipulation sous Git, c'est de créer un dépôt.

Un dépôt est un simple répertoire qui contiendra toutes les informations
nécessaires au fonctionnement de Git. 

Pour créer le dépôt on lance la commande `git init` à la racine de notre projet.

Une fois la commande lancée on voir apparaître dans notre répertoire un
répertoire cachée (`ls -la` pour le voir) un répertoire .git.

## Créer un dépôt Git à partir d'un dépôt existant

La plupart du temps on va pas créer son propre dépôt mais on va reprendre une copie
d'un dépôt existant.

Pour ce faire, on peut utiliser la commande `git clone
https://url-de-mon-depot.fr/mon-depot.git`. Le ".git" à la fin de l'URL est une
convention qu'on retrouve souvent mais en aucun cas une obligation. Un dépôt
n'est toujours qu'un répertoire même quand c'est distant.
