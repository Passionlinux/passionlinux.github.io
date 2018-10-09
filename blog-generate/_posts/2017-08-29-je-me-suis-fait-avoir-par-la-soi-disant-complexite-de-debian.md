---
title: je me suis fait avoir par la soi-disant complexité de Debian
date: 2017-08-29 18:31
layout: post
---

Je faisais depuis quelque temps des apt dist-upgrade précédé par un apt
update et il ne se passait rien, aucune mise-à-jour... A force de
toujours faire tout par soi-même et avec aucun automatisme, on en oublie
que Debian peut tout automatiser si on le souhaite. Je m'en suis rappelé
un peu tard.  
<!--more-->  
Il y a deux ou trois jours, j'avais fait la commande pour mettre à jour
mon OS, il y avait enfin une mise-à-jour, une seule, je la refuse car
j'avais un doute sur le pourquoi j'en avais si peu. Je relance quelques
heures plus tard la commande, de là il n'y a plus rien, l'unique update
avait disparue comme elle était venu, sans rien dire... Puisque je
voulais en avoir le cœur net, j'ai été de mon sujet sur le forum
[Debian-Facile](https://debian-facile.org/viewtopic.php?id=18983), entre
nous ce site est une mine, pour sa documentation, son ambiance, son côté
"on est sous Debian mais on est tous le con de quelqu'un", bref c'est LE
site francophone pour Debian! Comme ça m'est sortie ou en tout cas, je
n'ai pas cherché du côté d'Apt tellement persuadé que c'était soit mon
sources.list soit le miroir français qui merdait, je n'avais pas pris la
peine de regarder les logs de Apt, grosse erreur, je montre ici comme je
l'ai fait la bas, une partie de ce log qui compte un bon millier de
lignes, la partie qui nous révèle la cause:

    Start-date: 2017-08-22 06:56:42 Commandline: /usr/bin/unattended-upgrade Upgrade: libaugeas0:amd64 (1.8.0-1, 1.8.0-1+deb9u1), libraw15:amd64 (0.17.2-6+b1, 0.17.2-6+deb9u1), augeas-lenses:amd64 (1.8.0-1, 1.8.0-1+deb9u1) End-date: 2017-08-22 06:56:56 Start-date: 2017-08-24 06:59:09 Commandline: /usr/bin/unattended-upgrade Upgrade: libxml2-utils:amd64 (2.9.4+dfsg1-2.2, 2.9.4+dfsg1-2.2+deb9u1), libxml2-dev:amd64 (2.9.4+dfsg1-2.2, 2.9.4+dfsg1-2.2+deb9u1), python-libxml2:amd64 (2.9.4+dfsg1-2.2, 2.9.4+dfsg1-2.2+deb9u1), libxml2:amd64 (2.9.4+dfsg1-2.2, 2.9.4+dfsg1-2.2+deb9u1), libxml2:i386 (2.9.4+dfsg1-2.2, 2.9.4+dfsg1-2.2+deb9u1) End-date: 2017-08-24 06:59:27 Start-date: 2017-08-28 06:56:02 Commandline: /usr/bin/unattended-upgrade Upgrade: libmariadbclient18:amd64 (10.1.23-9+deb9u1, 10.1.26-0+deb9u1) End-date: 2017-08-28 06:56:14

Le coupable est simplement unattended-upgrade, qui fait passer les
mises-à-jour de sécurités en automatique, bon maintenant, je ne l'ai pas
installé de moi-même, mais c'est une dépendance à un paquet que j'ai
installé. Pour revenir à mon titre de billet, c'est un clin d’œil pour
ceux qui trouvent Debian trop compliqué, trop technique, sans
automatisme, un truc de barbus... Je me suis fait avoir bêtement en ne
cherchant pas du côté de l'automatisme et donc de la simplification (ou
facilité) des actions d'Apt. Encore une raison pour aimer toujours un
peu plus ce système.
