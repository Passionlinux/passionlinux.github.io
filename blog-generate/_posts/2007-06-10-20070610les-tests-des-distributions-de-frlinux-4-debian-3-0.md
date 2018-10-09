---
title: Les tests des distributions de FRlinux 4,  Debian 3.0
date: 2007-06-10 01:54
layout: post
---

*Dernière mise à jour : 19/09/2002*

Voici donc venu le test tant attendu du changement de version majeure de
Debian GNU/Linux, que je vais aussi sous titrer : "une soirée chez ma
mèere" car l'ordinateur cobaye n'est autre que la machine de mes parents
pour lesquels j'ai décidé de faire quelque chose avec Linux. La machine
est un PIII 933 avec un chipset VIA 686B (carte son integree), 128 Mo de
mémoire, une geforce 2 mx en carte vidéo, un écran 17 pouces, un graveur
SCSI et une connection internet avec un modem 56k externe. Debian nous
livre ici une version stable contenant : kernel 2.4.18, glibc 2.2.5,
XFree 4.1.0 (considéré comme le plus stable par Debian, le 4.2.0 étant
toujours en période de rôdage), Gnome 1.4.1, et grande nouveauté : KDE
2.2.2 (ici encore, philosophie de la stabilité oblige, KDE 3.0 va mettre
du temps à arriver dans la branche stable). Pour les utilisateurs avides
de dernières versions, un petit changement des apt-sources devrait les
ravir en utilisant la branche instable (qui marche plutôt bien par
ailleurs).

[![](http://frlinux.net/pictures/linux/debian30_01s.jpg)](http://frlinux.net/pictures/linux/debian30_01.jpg)

    Debian livre ici le mozilla 1.0 sauve Debian et preparé avec amour.
Certains diront encore qu'ils ne sont pas à la page mais j'aimerais
préciser que l'objectif de Debian n'est pas de courir après la dernière
version lors de la sortie d'une version de distribution stable mais
fournir une distribution sans reproches, ce qui est exactement le cas de
celle-ci. Mozilla est fournit brut de pommes, j'entends ici sans aucun
plugin, c'est à vous de fournir. Petite note pour java, ceux qui
recompilent à tout va devront recompiler le plugin si vous passez Debian
en GCC 3.2 (GCC 2.95.4 est fournit par défaut). Debian a bien sûr inclus
une page de démarrage pour vous aider à aller plus vite dans la
recherche de documentation et de liens.

[![](http://frlinux.net/pictures/linux/debian30_02s.jpg)](http://frlinux.net/pictures/linux/debian30_02.jpg)

La branche considérée stable pour alsa est la 0.5 alors que la 0.9 est
en fin de test depuis déjà quelques temps. J'ai donc tout naturellement
testé les outils Debian tels que alsaconf pour tenter de paramétrer ma
carte son mais le résultat n'était pas probant (via 686b intégrée), j'ai
donc installé les 0.9 et tout paramétré à la main. Pas de problème
notable par la suite. Toute application multimédia marche impeccablement
(CD audio, XMMS, mplayer et Quake/Wolfenstein ont été testés).

[![](http://frlinux.net/pictures/linux/debian30_03s.jpg)](http://frlinux.net/pictures/linux/debian30_03.jpg)

Les utilisateurs de Debian connaissent le fabuleux apt-get qui permet
d'installer ou de supprimer des packages sur votre système (tout comme
RPM mais en mieux pensé). J'ai donc installé enlightenment en une
commande : **apt-get install enlightenment**. Quelques secondes plus
tard, je rajoutais les epplets et cela me donne l'écran que vous pouvez
admirer dessous, j'ai rajouté Eterm pour de belles transparences.

[![](http://frlinux.net/pictures/linux/debian30_04s.jpg)](http://frlinux.net/pictures/linux/debian30_04.jpg)

Comme je le mentionnais en début d'article, Gnome 1.4.1 est également
présent dans cette version, vous donnant toute la stabilité de Gnome
sans les dernières améliorations. Cela constitue un très bon choix pour
une machine professionnelle et pour les personnes visant une grande
stabilité, je n'ai aucun reproche à faire sur l'installation, elle est
impeccable (Mandrake 8.2 avait quelques bugs assez embêtants qui
m'avaient poussé à mettre Ximian Gnome dessus). Nautilus marche
également sans aucun problème et se paramètre comme à l'accoutumée.

[![](http://frlinux.net/pictures/linux/debian30_05s.jpg)](http://frlinux.net/pictures/linux/debian30_05.jpg)

Toujours dans son soucis de perfection, Debian est livré avec Evolution
1.0.5 (vous devrez l'installer manuellement, car il ne fait pas partie
de la suite officielle de Gnome). La dernière version est la 1.0.8 qui
corrige pas mal de petits bugs enervants mais considérons la version de
Debian comme stable.

[![](http://frlinux.net/pictures/linux/debian30_06s.jpg)](http://frlinux.net/pictures/linux/debian30_06.jpg)

Enfin, toujours dans le cadre de la migration Windows vers Linux, il
fallait trouver un moyen de transferer tous les emails, c'est chose
faîte grâce à l'incorporation de KDE et donc de KImport vous permettant
dde migrer des dossiers Outlook Express ou autres vers Kmail,
l'opération s'est déroulée sans aucun problème et a permis de faire un
environnement de bureau rapidement (KDE a été choisit pour éviter une
transition de Windows trop difficile).

[![](http://frlinux.net/pictures/linux/debian30_07s.jpg)](http://frlinux.net/pictures/linux/debian30_07.jpg)

Que penser ? J'aime bien Debian, je la conseille tout de suite pour une
mise en place en tant que serveur de production. Cette dernière version
se retrouve comme à son habitude en retrait dans le monde des stations
de travail. La stabilité étant privilégiée, les mises à jour sont moins
fréquentes. De plus, XFree étant toujours fournit en 4.1.0, la plupart
des portables de moins d'un an ne pourront pas être reconnus, vous
contraignant à faire une installation manuelle ou rajouter une source
dans le apt.list gérant les packages instables de 4.2.0. Avec 3 CDs
(rien qu'en binaires, car la distribution en fait 7), elle représente
néanmoins un très bon choix pour une station stable. Tout comme mon test
sur la 2.2, je conseille Debian aux personnes expérimentées sachant ce
qu'est Linux et comment paramétrer leur système.
