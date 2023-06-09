+++
title = "Vscodium - Navigation dans l'éditeur"
date = "2023-06-07T09:45:03+02:00"
author = "James"
authorTwitter = "" #do not include @
cover = ""
tags = []
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
summary = "ctrl + p -> pleine puissance pour la programmation de vos projets"
+++

## CTRL + P

Si on retient une chose de ce tutoriel, c'est le raccourci clavier `ctrl+p`. Ce
raccourci ouvre une boîte de dialogue où l'on peut saisir un nom de fichier. On
n'a pas besoin de connaître le chemin, on a pas besoin de saisir le nom en
entier, VSCodium trouvera la plupart du temps le fichier que l'on cherche même
avec quelques caractères.

Si plusieurs fichiers répondent à la saisie on peut naviguer dans la liste (`↑`
/ `↓`) ou (`ctrl+n` / `ctrl+p`).

On peut même aller sur une ligne précise d'un fichier directement si on la
connaît d'avance en tapant `:` ou bien naviguer entre les symboles avec `@`.

## Les onglets

Une fois qu'on commence à avoir plusieurs fichiers ouverts dans les onglets, on
aimerait bien pouvoir naviguer entre ces derniers au clavier. Pour ce faire, on
peut faire `ctrl+tab` pour aller sur l'onglet suivant et `ctrl+shift+tab` pour
naviguer à l'onglet précédent.

## Splits

Parfois on peut vouloir consulter deux fichiers en même temps, par exemple un
fichier d'interface et son implémentation ou encore voir un même fichier à deux
endroits en même temps.

Pour scinder pouvoir afficher deux pages en même temps, il suffit de faire
`ctrl+\`.

On a plusieurs possibilités pour naviguer entre les groupes d'édition :

On peut directement aller sur le groupe qui nous intéresse en faisant `ctrl + 1`
pour aller sur le premier en partant de la gauche, `ctrl + 2` le deuxième en
partant de la gauche, etc.

On peut aussi naviguer vers le groupe immédiatement à gauche (`ctrl + k` puis
`ctrl + ←`) ou immédiatement à droite (`ctrl + k` puis `ctrl + →`).

## Edition

On retrouve les opérations habituelles de copier, couper et coller mais VSCodium
propose beaucoup plus de fonctionnalités.

On se déplacer dans le document avec les flèches du clavier ou encore `ctrl + g`
pour sauter à une ligne en particulier. 

Une fois qu'on est sur la ligne qui nous intéresse on peut se déplacer de mot en
mot avec `ctrl + ←` pour un mot sur la gauche et `ctrl + →` pour aller à un mot
sur la droite. 

Maintenir `shift` permet de sélectionner du texte, ce que l'on
peut combiner avec le déplacement mot par mot ou simplement les flèches.

Pour sélectionner une ligne commplète on peut faire `ctrl + l`, chaque nouvelle
saisie sélectionne la ligne en-dessous.

Un outil très pratique est le mécanisme des curseurs multiples, avec le HTML ou
le XML on se retrouve souvent avec deux balises une ouvrante et une fermante. On
peut modifier l'un puis l'autre mais ça va prendre du temps. Pour aller plus
vite on positionne le curseur sur le premier élément, par exemple le `p` dans une balise
paragraphe et fait `ctrl + d`. VSCodium sélectionne alors le premier `p`, si on
refait maintenant `ctrl + d` il sélectionne le `p` de la balise fermante. Il
suffit alors de saisir la balise de remplacement. On peut faire autant de 
`ctrl + d` que nécessaire. Une fois qu'on a fini sa saisie on fait `échappe`
pour retrouver un curseur unique.

Pour supprimer une ligne en entier, il suffit de positionner le curseur sur la
ligne et de faire `ctrl + x`. On peut ensuite coller la ligne si nécessaire ou
procéder à d'autres modifications.

Si c'est juste pour déplacer une ligne, il suffit de faire `alt + ↑` pour la
monter dans le fichier source ou `alt + ↓` pour la descendre.

De la même façon pour dupliquer une ligne, vers le haut c'est  `alt + shift + ↑`
et `alt + shift + ↓`.

Enfin pour commenter son code, on peut faire `ctrl + /` pour faire un
commentaire de ligne et `shift + alt + a` pour faire un commentaire de bloc, si
votre langage fait bien la distinction entre les deux.

## Conclusion

On a déroulé les raccourcis les plus utiles mais chacun travaille différemment,
c'est pourquoi il faut toujours demander quelles sont les manipulations que l'on
fait en boucle et est-ce qu'on aurait pas moyen d'utiliser des raccourcis pour
le faire plus vite.

VSCodium intègre un lien vers une synthèse des raccourcis clavier, on le trouve
dans la barre de menu sous `Help` / `Keyboard Shortcuts Reference`