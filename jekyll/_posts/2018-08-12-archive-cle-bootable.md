---
title: "Créez une clé bootable"
date: 2017-11-18T00:55:31+01:00
layout: post
---
Merci a [Tnut](http://www.nutyx.org/fr/installation.html)

Si vous êtes déjà sous GNU/Linux :
En root

A l'aide de `fdisk`, déterminez où se trouve votre clé USB :

    	fdisk -l

A l'aide de dd, créez votre clé bootable :

    	dd if=NuTyX_x86_64-saravane-14.11.iso of=/dev/sdX

La valeur sdX est donnée par la commande :

    	fdisk -l

Si vous êtes sous Windows :

Utilisez votre outils de gravure favori pour graver l'ISO sur un CD-RW (si possible) ...
