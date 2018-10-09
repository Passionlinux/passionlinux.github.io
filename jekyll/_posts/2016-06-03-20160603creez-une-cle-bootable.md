---
title: Créez une clé bootable
date: 2016-06-03 12:30
layout: post
---

<p>
    Merci a [Tnut](http://www.nutyx.org/fr/installation.html)

Si vous êtes déjà sous GNU/Linux :

<div>

![\[Important\]](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L10xH10/cautiongif-88815-7dfcc.gif?1464957024){width="10"
height="10"}En root

</div>

A l’aide de fdisk, déterminez où se trouve votre clé USB :

    fdisk -l

A l’aide de **dd**, créez votre clé bootable :

    dd if=NuTyX_x86_64-saravane-14.11.iso of=/dev/sdX

La valeur **sdX** est donnée par la commande :

    fdisk -l

Si vous êtes sous Windows :

Utilisez votre outils de gravure favori pour graver l’iso sur un CD-RW
(si possible) ...

<p>
</p>

