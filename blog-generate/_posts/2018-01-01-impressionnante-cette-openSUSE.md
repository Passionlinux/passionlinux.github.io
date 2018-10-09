---
title: "Impressionnante cette openSUSE"
date: 2018-03-16T23:40:53+01:00
layout: post
---

J'explique un peu le pourquoi de ce titre de billet. J'ai donc testé une openSUSE Leap 15 bêta, ce qui m'a donné envie d'installer une Leap à la place de ma tendre Debian (une Tumbleweed aussi mais c'est pour un autre billet) mais je n'avais pas la dernière en date c'est-à-dire la 42.3 mais une 42.2 traînant encore sur une de mes clés, je l'ai donc installé et j'ai appliqué les dernières mise-à-jour de cette version, qui de mémoire faisaient dans les 800 paquets. J'ai ensuite changé les dépôts pour passer de la 42.2 à la 42.3 en sauvegardant/déplaçant les dépôts précédents:

    mkdir /etc/zypp/repos.d/old

    cp -Rv /etc/zypp/repos.d/*.repo /etc/zypp/repos.d/old
    
    sed -e 's/42.2/42.3/g' -i *
    

De là, comme un porc et en ne prenant aucune précaution donc sans passé en console (tty), j'ai lancé un `zypper dup` et laissé faire. Enfin une fois les quelques 2300 paquets mis-à-jour, j'ai redémarré avec un `reboot`.

Une fois cela fait, j'ai ajouté [les dépôts KDE-Frameworks, KDE-extra, KDE-applications et QT](https://fr.opensuse.org/D%C3%A9p%C3%B4ts_KDE) pour profiter de la dernière version de Plasma (5.12), aussi j'ai ajouté les dépôts de Mozilla, Games, Emulators puis fait une belle mise-à-jour via `zypper dup`. J'ai installé les paquets qui me fallait comme l'intégrale des jeux de KDE, des jeux, des logiciels de pirates, d'autres de multimédia, d'autres encore d'émulation... Ça monte vite quand on ne regarde pas... J'ai aussi installé GNOME.

Puis ce soir, au bout de 5 jours, j'ai encore voulu voir les limites de Zypper, je me suis dis que ça serait bien de passer de la même manière en Tumbleweed... À nouveau sauvegarde de la liste des dépôts mais cette fois en les déplaçant:

    mv /etc/zypp/repos.d/*.repo /etc/zypp/repos.d/old
    
Puis ajout des nouveaux dépôts:

    zypper ar -f -c http://download.opensuse.org/tumbleweed/repo/oss repo-oss
    zypper ar -f -c http://download.opensuse.org/tumbleweed/repo/non-oss repo-non-oss
    zypper ar -f -c http://download.opensuse.org/tumbleweed/repo/debug repo-debug
    zypper ar -f -c http://download.opensuse.org/update/tumbleweed/ repo-update
    zypper ar -f -d -c http://download.opensuse.org/tumbleweed/repo/src-oss repo-src-oss
    zypper ar -f -d -c http://download.opensuse.org/tumbleweed/repo/src-non-oss repo-src-non-oss
    
En *root*, on regarde si la liste est bonne avec un `zypper lr -u` ce qui devrait donner un tableau récapitulant les différents dépôts et leurs valeurs, voir [cette page.](https://en.opensuse.org/openSUSE:Tumbleweed_upgrade)

Puis comme au dessus, je n'ai pas pris la peine de sortir de ma session KDE, juste désactivé la mise en veille ainsi que l'économiseur d'écran et j'ai relancé `zypper dup`. Après 6000 paquets mis à jour, j'ai relancé et me suis retrouvé sur Tumbleweed de fonctionnel!

Avec le peu de soin que je lui ai apporté, elle n'a pas bronché, pas eu le moindre soucis, rien et je dirais même plus, pendant tout ce temps j'attendais patiemment en regardant sur ma TV un film directement depuis mon PC via le serveur DLNA MiniDLNA, attendant que ça se coupe signe que le service était mit à jour comme c'est le cas sur d'autres distributions, Debian pour ne pas citer. Mais non, j'ai pu aller jusqu'à la fin du film et une fois fini, je me suis quand même inquiété sur cette upgrade en ne voyant pas MiniDLNA se couper, en allant voir de quoi il retournait, j'ai pu comprendre que c'était fini... En redémarrant j'ai vu que mon GNOME est passé en 3.28, deux jours seulement après [l'annonce de sa sortie](https://www.gnome.org/news/2018/03/gnome-3-28-released/).
