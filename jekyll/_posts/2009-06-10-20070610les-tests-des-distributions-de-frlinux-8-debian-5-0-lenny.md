---
title: Les tests des distributions de FRlinux 8, Debian 5.0 (Lenny)
date: 2009-06-10 02:07
layout: post
---

*Dernière mise à jour : 22/04/2009* Debian Lenny est [sortie le jour de
la saint valentin](http://www.fr.debian.org/News/2009/20090214.fr.html),
le 14 février 2009. Cette nouvelle mouture apporte un très beau lot de
nouveautés parmi lesquelles : installateur graphique, KDE 3.5.10, GNOME
2.22.2, Xfce 4.4.2, LXDE 0.3.2.1, GNUstep desktop 7.3, X.Org 7.3,
OpenOffice.org 2.4.1, GIMP 2.4.7, Xen 3.2.1, Kvm 7.2 et un noyau 2.6.26.
Vu que j'ai mis un peu de temps à écrire cet article, une [mise à
jour](http://www.fr.debian.org/News/2009/20090411) est sortie entre
temps corrigeant une trentaine de problèmes de sécurité et 93
correctifs. Debian est disponible sur de nombreuses architectures et en
différents formats (CD, DVD, installation réseau, etc ...) J'ai testé
quasiment toutes les méthodes d'installation étant donné que j'ai un
parc de serveurs (voici un lien en Anglais avec les problemes rencontres
lors de la mise a jour par une autre personne
:<http://www.tchetch.net/wiki/debian/maintenance/upgrade_to_lenny>,
merci a Etienne Bagnoud) et de stations tournant sous Debian. J'ai aussi
installé des serveurs sous Xen (virtualisation semi et complète). La
version dont les captures d'écran apparaissent ici est une i386 de layout
netinst. J'utilise également Lenny sur ma station de travail (dual Xeon
avec Nvidia 6800 et dual 24" Dell avec les pilotes propriétaires).
Pensez bien à lire [les notes de mise à
jour](http://www.us.debian.org/releases/stable/i386/release-notes/ch-upgrading.fr.html) avant
de continuer La star de cette nouvelle version est sans conteste son
installateur graphique. Je suis personnellement un pur fan de la version
curses, que je pratique depuis beaucoup d'années mais je comprends tout
à fait la motivation de faire un installateur graphique.

[![](http://frlinux.net/pictures/linux/debian50_01s.png)](http://frlinux.net/pictures/linux/debian50_01.png)

    Les options disponibles dans l'installateur graphique sont les mêmes
que celles disponibles en mode ncurses. Vous pourrez donc configurer
votre nouveau système exactement comme vous le feriez en mode texte.
Comme je le précisais un peu plus tot, j'utilise Debian pour beaucoup de
serveurs, y compris Xen. Xen vient en version 3.2.1 sur le noyau de
cette version soit le 2.6.26. Je n'ai rencontré aucun problème et les 5
serveurs de production que je tourne actuellement sous Lenny utilisent
les paquets Debian (alors que je tournais précédemment une version
compilée maison). J'ai aussi testé Kvm afin de pouvoir comparer avec
Xen. Le développement de ce dernier avance à grands pas et je dois dire
que l'installation de VMs sur ma machine se sont faites sans aucun
problème.

[![](http://frlinux.net/pictures/linux/debian50_02s.png)](http://frlinux.net/pictures/linux/debian50_02.png)

Lors de l'installation en mode graphique, j'ai rencontré un problème
récurrent lors de la sélection en Français (ISO netinst), le paquet
dictionnaries-common n'a pas pu se configurer correctement. J'ai utilisé
la version netinst qui a priori fonctionne correctement à présent, je ne
peux conclure qu'à un paquet mis à jour... J'ai aussi installé Debian
Lenny sur mon portable (mon petit dernier est un IBM/Lenovo x61s, dont
le test sera bientôt disponible). J'ai choisi d'encrypter /home / et le
swap. Toute l'installation a fonction née correctement et le portable se
comporte admirablement en mode veille et veille prolongée. Les
périphériques sont tous supportés correctement (en particulier la carte
graphique, et carte son, plateforme Intel).

[![](http://frlinux.net/pictures/linux/debian50_03s.png)](http://frlinux.net/pictures/linux/debian50_03.png)

Le problème dont je parlais dans le paragraphe précédent a donc généré
la capture ci-dessous. Cela ressemble étrangement à
ce [bug](http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=401876) qui en
théorie a été corrigé il y a fort longtemps (fin 2006). J'ai refait une
installation en mode texte et tout a fonctionné correctement.

[![](http://frlinux.net/pictures/linux/debian50_04s.png)](http://frlinux.net/pictures/linux/debian50_04.png)

Le premier démarrage vous présente un bel écran GDM. L'installateur
propose aussi à présent des installations alternatives (en appuyant sur
plus d'options) qui vous permettront d'installer : KDE, XFCE ou LXDE. En
ce qui concerne les paquets multimédia et les codecs supplémentaires non
libres, je vous conseille d'ajouter le dépôt [Debian
Multimédia](http://debian-multimedia.org/). Ce dépôt vous permettra
d'accéder à beaucoup de codecs supplémentaires, notamment pour la vidéo.
Je m'en sers beaucoup sur ma station et mon portable. Ainsi que pour
certaines stations utilisateurs chez nous.

[![](http://frlinux.net/pictures/linux/debian50_05s.png)](http://frlinux.net/pictures/linux/debian50_05.png)

Comme la plupart des distributions récentes, vous aurez la joie de
pouvoir installer LXDE, ce gestionnaire ultra léger qui vous permettra
de faire tourner une configuration modeste à bonne vitesse. La
traduction en Français marche correctement et vous donne un ensemble
cohérent. L'apport du noyau 2.6.26 avec les dernières version de udev et
hal est considérable. J'ai eu très peu de choses à faire manuellement
pour faire marcher mes différents périphériques.

[![](http://frlinux.net/pictures/linux/debian50_06s.png)](http://frlinux.net/pictures/linux/debian50_06.png)

Gnome 2.22.2 est également fourni dans cette nouvelle version de Debian.
C'est le bureau par défaut si vous ne changez rien à votre installation.
Debian choisissant la stabilité plutôt que la nouveauté (je vous laisse
deviner ce que vous pouvez tester pour remédier à cette situation si
elle vous déplaît), Gnome a deux trains de retard mais ce n'est pas très
dérangeant. Il en est de même pour Gimp (en 2.4 dans cette version) et
OpenOffice.org (2.4 alors que la 3.0 est disponible). SELinux est
installé par défaut, mais je n'ai pas eu l'occasion de le tester.

[![](http://frlinux.net/pictures/linux/debian50_07s.png)](http://frlinux.net/pictures/linux/debian50_07.png)

KDE 3.5.10 est la version présentée sur cette nouvelle révision de
Debian. Ceux voulant 4.2 peuvent passer en testing qui a commencée à
migrer vers cette version progressivement. Je n'ai pas grand chose à
dire sur KDE 3.5.10, c'est stable, épuré et le support est là. Ne pas
avoir migré vers KDE 4.x (comme beaucoup de nouvelles distributions) est
une bonne idée. Il y eu beaucoup de débats
sur [iceweasel](http://times.debian.net/1022-iceweasel) (la version
Debian de Firefox). Je fait partie de ceux pensant que Firefox se
comporte mieux avec Flash et Java. Ceci est un choix personnel et j'ai
pu le vérifier sur ma station de travail et mon portable. Je ne conteste
en rien le travail fait par les développeurs d'Iceweasel, ce n'est juste
pas mon truc.

[![](http://frlinux.net/pictures/linux/debian50_08s.png)](http://frlinux.net/pictures/linux/debian50_08.png)

En conclusion, Lenny est une belle réussite, près de deux ans après Etch
(Debian 4.0), cette nouvelle version tient ses promesses et propose une
offre logicielle bien complète et supportant beaucoup d'architectures
différentes. Je n'ai rencontré presque aucun problème sur les migrations
réseau Etch et Lenny (aptitude safe-upgrade est votre ami). Pour le
moment, elle est capable de supporter la plupart des machines récemment
sorties. Je la recommande les yeux fermés surtout pour ceux voulant une
alternative à Ubuntu et voulant un système stable.
