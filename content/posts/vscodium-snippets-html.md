+++
title = "Vscodium: Snippets et emmet pour du HTML"
date = "2023-06-02T09:43:53+02:00"
author = "James"
authorTwitter = "" #do not include @
cover = ""
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = true
hideComments = false
color = "" #color from the theme settings
summary = "Découvrez le monde merveilleux du code qui s'écrit tout seul !"
+++

## Snippets VSCodium

Imaginez que vous écrivez souvent des pages HTML, vous allez saisir souvent quelque chose 
qui ressemble à ça pour commencer à chaque fois:

```html
<!DOCTYPE html>
<html lang="fr">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Ma page HTML</title>
    </head>

    <body>

    </body>
</html>
```

Si on doit retaper tout ça à la main ça va prendre un bon moment, multiplié par 
le nombre de fichiers HTML à créer, sans parler du risque d'une faute de frappe...

Pour pallier ce problème VSCodium propose les snippets, des gabarits (templates)
de code pré-écrit. Pour obtenir quelque chose qui ressemble à l'extrait de code
ci-dessus, il suffit d'écrire `html:5` dans VSCodium et d'appuyer sur entrée.
VSCodium alimente alors notre fichier.

Cela va encore plus loin qu'une sorte de copié collé, l'auteur d'un
snippet peut indiquer les emplacements où l'on va faire les modifications les
plus fréquentes afin qu'on puisse y naviguer rapidement.

Si on reprend le code généré plus haut, après avoir écrit `html:5` puis entrée, 
on peut faire `tab` pour naviguer successivement sur les points numérotés entre
paranthèses.

```html
<!DOCTYPE html>
<html lang="fr">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width (1), initial-scale=1.0 (2)">
        <title>Ma page HTML (3)</title>
    </head>

    <body>
        (4)
    </body>
</html>
```

Il existe de nombreux snippets intégrés dans VSCodium pour de nombreux langages.
Il suffit de commencer à écrire son code pour les voir apparaître dans le popup
de suggestion.

Quelques exemples:

|Caractère saisi   | Code généré avec position générée  |
|---|---|
| p  | `<p>(1)</p>`  |
| h1  | `<h1>(1)</h1>`  |
| img:s  | `<img src="(1)" alt="(2)" srcset="(3)">`  |

## Emmet

Pour ce qui concerne le HTML spécifiquement, VSCodium permet d'aller plus loin.
Pour ce faire, il s'appuie sur un outil qui s'appelle emmet, qui permet de générer
des snippets à la volée. Tout comme les snippets on saisit directement le "code"
emmet et on fait entrée pour provoquer la génération.

Voici un exemple, si on saisit `ul>li*3.toto#titi$`, VSCodium va nous générer

```html
<ul>
    <li class="toto" id="titi1"></li>
    <li class="toto" id="titi2"></li>
    <li class="toto" id="titi3"></li>
</ul>
```

On voit que très vite on peut écrire des quantités énormes de HTML en très peu
de caractères. C'est assez incompréhensible au début mais nous verrons qu'une
fois qu'on connaît les quelques caractères opérateurs, cela va très vite.

Il faut faire attention toutefois, emmet ne fait aucune contrôle
sur les balises contrairement aux snippets. Il est donc tout à fait possible de saisir des balises
inexistantes avec une faute de frappe.

**NB:** Quand on copie-colle des exemples de code emmet, on n'a pas forcément le popup
de suggestion qui apparaît pour le déclencher on fait `ctrl+espace`.

Voyons maintenant les différents raccourcis proposés par emmet.

### Imbrication

Il est très fréquent en HTML de vouloir imbriquer des éléments, pour faire ça
avec emmet on utilise le caractère `>`. On peut imbriquer autant de niveaux que
l'on souhaite.

Voici quelques exemples:

`p>strong`
```html
<p>
    <strong>(1)</strong>
</p>
```

`ul>li`
```html
<ul>
    <li>(1)</li>
</ul>
```

`ul>li>p`
```html
<ul>
    <li>
        <p>(1)</p>
    </li>
</ul>
```

### Des éléments de même niveau

Même si un document HTML est un ensemble d'éléments imbriqués, on peut aussi
avoir plusieurs éléments de même niveau. Pour représenter ça avec emmet on
utilise le caractère `+`.

Voici quelques exemples: 

`h2+img+p`
```html
<h2>(1)</h2>
<img src="(2)" alt="(3)">
<p>(4)</p>
```

`p+code`
```html
<p>(1)</p>
<code>(2)</code>
```

### Remonter d'un niveau

Il peut être intéressant de combiner les deux précédents opérateurs (`>` et `+`)
mais on va se retrouver coincé si on veut des éléments de même niveau après une
imbrication. Pour sortir d'une imbrication on peut utiliser le caractère `^`.

Par exemple:

`h2+p+ul>li^p`
```html
<h2>(1)</h2>
<p>(2)</p>
<ul>
    <li>(3)</li>
</ul>
<p>(4)</p>
```
On voit bien ici que le dernier `p` n'est pas imbriqué dans le `li` mais remonte
d'un niveau.

On peut remonter de plusieurs niveaux d'un coup :

`h2+p+ul>li>p^^h2`
```html
<h2>(1)</h2>
<p>(2)</p>
<ul>
    <li>
        <p>(3)</p>
    </li>
</ul>
<h2>(4)</h2>
```
Ici `h2` est remonté au niveau de `ul`.

### La multiplication

On peut vouloir aussi avoir plusieurs éléments identiques les uns à la suite des
autre, on pense par exemple à 
```html
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
<ul>
```
Avec ce que nous avons vu, on pourrait être tentés d'écrire `ul>li+li+li+li+li`
mais ça devient très vite long et source d'erreur. C'est pourquoi emmet nous propose
l'opérateur `*`.

On peut alors générer le code ci-dessus avec l'expression `ul>li*4`, où quatre
est le nombre d'éléments que l'on souhaite générer.

Un autre exemple plus complet:

`section>article*4>h2+p*3`
```html
<section>
    <article>
        <h2>(1)</h2>
        <p>(2)</p>
        <p>(3)</p>
        <p>(4)</p>
    </article>
    <article>
        <h2>(...)</h2>
        <p></p>
        <p></p>
        <p></p>
    </article>
    <article>
        <h2></h2>
        <p></p>
        <p></p>
        <p></p>
    </article>
    <article>
        <h2></h2>
        <p></p>
        <p></p>
        <p></p>
    </article>
</section>
```

### Les sélecteurs CSS

Pour générer des éléments avec des "class" et "id" pré-reseignés il suffit
d'utiliser les sélecteurs CSS habituels, à savoir `.` et `#` respectivement.

Par exemple:

`p.toto`
```html
<p class="toto"></p>
```

`p#titi`
```html
<p id="titi"></p>
```

On peut les combiner à souhait :

`p.toto.tutu.ma-classe#idParagraphe`
```html
<p class="toto tutu ma-classe" id="idParagraphe"></p>
```

### La numérotation

On peut vouloir de temps en temps numéroter des éléments, comme le cas des id de
l'exemple en début de section. Pour ce faire avec emmet on utilise l'opérateur
`$`.

En pratique ça donne:

`p*3#mon-id-$`
```html
<p id="mon-id-1"></p>
<p id="mon-id-2"></p>
<p id="mon-id-3"></p>
```

### Le texte

Si l'on connaît d'avance une partie du contenu de notre page on peut le
communiquer à emmet avec l'opérateur `{}`.

Pour reprendre le dernier exemple :
`p*3#mon-id-${Paragraphe n°$}`
```html
<p id="mon-id-1">Paragraphe n°1</p>
<p id="mon-id-2">Paragraphe n°2</p>
<p id="mon-id-3">Paragraphe n°3</p>
```

### Conseils pratiques

Pour paraphraser un grand philosophe du XXe siècle (Oncle Ben, non pas le riz,
Spiderman) : avec grands pouvoirs de génération de code viennent de grandes
responsabilités. 

Ce n'est pas parce qu'on peut générer tout une page avec un
seul emmet que l'on doit le faire, bien souvent il est plus intéressant
d'utiliser quelques petites étapes pour arriver à générer sa page au fil de l'eau.

Pour aller plus loin : [docs emmet](https://docs.emmet.io/)

## Créer ses propres snippets

On peut souvent se rendre compte qu'on se retrouve à saisir tout le temps les
mêmes choses sans qu'un snippet ait été prévu par VSCodium.

On se rend alors dans la barre de menu sur `File > Preference` et puis on choisit
`Configure User Snippets`. VSCodium nous propose alors de choisir un langage, si
on sélectionne `HTML` s'ouvre alors un document JSON.

Imaginons que nous ayons besoin de générer régulièrement 3 paragraphes de classe
`toto` :
```html
<p class="toto"></p>
<p class="toto"></p>
<p class="toto"></p>
```

On aurait alors dans notre fichier `html.json`:
```json
{
	"trois-p-toto": {  // Le nom du snippet qui sera affiché à l'utilisateur
		"prefix": [ // Tableau de préfixes, c'est ce que l'utilisateur peut saisir pour déclencher le snippet.
                    // une saisie partielle peut être suffisant
			"3p-toto", // Le caractère 3 est suffisant pour déclencher ce préfixe
			"trois-paragraphes" // on peut saisir uniquement tp pour déclencher ce préfixe
		],
		"body": [ // Le contenu du snippet, pour chaque ligne on ajoute un String en plus dans la liste.
			"<p class='toto'>$1</p>", 
            // $1 permet de dire de configurer une insertion par l'utilisateur en première position,
            // $2 en deuxième position, etc.
            // Au besoin on peut mettre $0 pour dire où finir renseignement du reste du snippet.
			"\t<p class='toto'>$2</p>",
            // \t permet d'identer une ligne, on peut identer autant de fois que l'on souhaite en multipliant les \t
			"<p class='toto'>$3</p>"
		],
		"description": "3 paragraphes de classe toto" // Plus de détails pour notre snippet qui peut être affiché à l'utilisateur.
	}
}
```

Pour aller plus loin : [doc vscode](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_create-your-own-snippets)