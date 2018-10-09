---
title: "Mate 1.18 sous Debian"
date: 2018-01-31T04:10:28+01:00
layout: post
---
Vous avez bien lu, je vais dire comment installer un Mate 1.18, qui est la dernière version stable à ce jour et qui est sortie le 13/03/2017, sur une Debian Stretch.

Comme vous le savez, Debian Stretch est sortie avec un Mate en version 1.16 et généralement il faut attendre une nouvelle version de Debian pour profiter d'un nouveau bureau, mais dans ce cas non. En effet le Mate dans sa version 1.18 est disponible dans les [backports](https://wiki.debian.org/fr/Backports) et il est donc bien plus facile de l'installer que de se faire son propre rétro-portage.

Pour se faire, on vérifie bien qu'on a dans notre *sources.list*, la ligne des *backports*:

	deb http://ftp.debian.org/debian stretch-backports main contrib non-free

Puis enfin on lance l'installation du bureau par un:

	apt-get -t stretch-backports install mate-desktop-environment-extras

Et c'est tout!!! Elle est pas belle la vie avec Debian?
