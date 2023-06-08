+++
title = "Git sur Windows - SSL certificate problem"
date = "2023-06-08T11:50:16+02:00"
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
summary = "Vos papiers, s'il vous plaît!"
+++

## SSL certificate problem: self-signed certificate

Si vous travaillez dans une grande organisation, il est tout à fait possible que
vous ayez affaire à certificats cryptographiques autosignés. 

Cela permet à votre organisme qui maîtrise les postes de travail et qui dispose
de son propre certificat racine de générer des certificats pour les sites et
serveurs internes sans devoir recourir à un prestataire extérieur.

Sous Windows ces certificats sont stockés dans un dépôt appelé le [magasin des certificats](https://learn.microsoft.com/fr-fr/windows-hardware/drivers/install/certificate-stores). 

Malheureusement Git sous Windows par défaut n'utilise pas ce dépôt mais utilise
un le dépôt de la librairie OpenSSL. 

Un premier réflexe pourrait être de désactiver complètement la vérification des
certificats par Git. C'est une solution à proscrire en raison de l'impact sur la
sécurité. En effet, on n'a plus aucune garantie sur le destinataire de nos push
et pull Git.

Une solution propre existe fort heuresement : il suffit de dire à Git d'utiliser
le magasin de certificats Windows. Pour ce faire, il suffit de saisir la
commande suivante : `git config --global http.sslBackend schannel`.

Source de la solution : [How do I configure Git to trust certificates from the Windows Certificate Store?](https://stackoverflow.com/a/48212753).