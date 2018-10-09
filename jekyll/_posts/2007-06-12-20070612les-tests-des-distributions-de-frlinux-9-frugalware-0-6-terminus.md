---
title: Les tests des distributions de FRlinux 9, Frugalware 0.6 (Terminus)
date: 2007-06-12 10:17
layout: post
---

*Dernière mise à jour : 20/04/2007*

[Frugalware](http://frugalware.org/) est une distribution d'origine
Hongroise créée par un jeune étudiant. Elle est issue de Slackware, la
différence principale se trouvant dans le gestionnaire de paquets sur
lequel je reviendrais plus tard. Cette version de Frugalware contenait
plein de bonnes choses lors de sa sortie : glibc 2.5, binutils
2.17.50.0.6 avec support DT\_GNU\_HASH, DBUS 1.0, Python 2.5, KDE 3.5.6,
Xfce 4.4, Beryl 0.2.0, OpenOffice.org 2.1, Firefox 2.0.0.2 et Gnome
2.18. Bon rien que ca, ca fait saliver, si en plus je vous dit noyau
2.6.20, on ne peux pas vraiment se plaindre. La version finale de la 0.6
est sortie le 22/03/2007 en architectures x86 et x86\_64. J'ai testé
cette distribution sur mon portable IBM t42 et ma station AMD X2 4800+
sur laquelle j'ai tenté d'installer la version 64 bits de Frugalware,
chose que je n'ai pas réussi à faire, j'ai donc fait un tour sur le site
officiel, les documentations et finalement l'IRC (sur Freenode,
\#frugalware en Anglais et \#fr.frugalware en Francais). J'ai trouvé une
communauté enthousiaste et sympathique. Après les règles d'usage pour
s'assurer que je n'était pas un mec qui ne savait pas de quoi je
parlais, on m'a gentiment dirigé vers le [système de
bugs](http://bugs.frugalware.org/) pour lequel j'ai rentré un bug sur
lequel je n'arrive plus à mettre la main. Globalement, le DVD
d'installation 64 bits ne trouvait pas les même dépendances de modules
et m'insultait même à coup de formats invalides quand j'essayais de
régler cela à la main ... J'ai donc finalement installé la version 32
bits sur la station principale également. Mon premier problème fut le
support pour mon écran (un Samsung 22' 16/10 tout neuf), vu que la
version de X.org présente ne comprenait pas la résolution de 1680x1050
avec le pilote nv. J'ai du résoudre cela avec l'installation des pilotes
propriétaires Nvidia (9755) qui ont marchés sans encombre. Comme je vous
le disais précédemment, KDE 3.5.6 est livré de base avec la distribution
avec un petit noyau 2.6.20 (au moment de sa sortie, une des premières
distributions à le proposer). Au niveau de l'installateur, vous pouvez à
présent faire des installations par tftp et clés USB.

[![](http://frlinux.net/pictures/linux/frugalware06_01s.png)](http://frlinux.net/pictures/linux/frugalware06_01.png)

    Comme je l'ai évoqué un peu plus haut, Frugalware est basée sur
Slackware mais n'utilise pas pour autant pkgtool ou swaret pour gérer
ses paquets. Elle
utilise [pacman](http://physics.bu.edu/~youssef/pacman/). Cela vous dit
quelque chose ? Eh bien à moi aussi, et pour cause, le même gestionnaire
est utilisé dans Arch Linux (testé dans cette section). Enfin le même
c'est beaucoup dire, en fait au début il s'agissait de la même version
puis au fil du temps, l'équipe de Frugalware a ajouté pas mal de
fonctionnalités tout en fournissant les patches au projet officiel mais
le projet officiel étant un peu statique, nous avons à présent deux
versions de pacman dont la plus riche se trouve dans Frugalware. Notez
que vous pouvez aussi utiliser un gestionnaire graphique (Frugalware
Package Manager) pour installer des paquets de manière conviviale. Ceci
dit, j'aurais tendance à conseiller pacman directement en lignes de
commandes qui avoine en terme de performances.

[![](http://frlinux.net/pictures/linux/frugalware06_02s.png)](http://frlinux.net/pictures/linux/frugalware06_02.png)

    J'ai aussi joué à mon fameux jeux : "quel périphérique ne sera pas
détecté sur cette distribution" et j'ai perdu ... Tout ce que j'ai testé
(nokia n95, scanner usb, appareil photo, etc ...) a été détecté et
installé correctement. pacman étant très intelligent (jusqu'à un certain
point), il sait gérer les conflits et dépendances. Pour installer un
nouveau logiciel, un petit **pacman -S sane** par exemple suffit à vous
installer ce que vous recherchez (c'est bien de connaître le nom du
paquet tout de même).

[![](http://frlinux.net/pictures/linux/frugalware06_03s.png)](http://frlinux.net/pictures/linux/frugalware06_03.png)

    Un problème gênant dans les toutes premières versions de Frugalware
concernait les mises à jour de sécurité des paquets, j'ai donc tout
naturellement testé cela dans cette nouvelle version. Après avoir scandé
un **pacman -Sy** pour mettre à jour ma base, il m'a suffi de faire
un **pacman -Su **pour mettre à jour les paquets vulnérables. On est ici
arrivé à la même simplicité que la plupart des grosses distributions. Ne
reste plus qu'un utilitaire de notification automatique de mises à jour
et cette partie sera sans failles (ayant un parc d'utilisateurs ayant
comme philosophie "si ça marche, pourquoi mettre à jour", c'est
important).

[![](http://frlinux.net/pictures/linux/frugalware06_04s.png)](http://frlinux.net/pictures/linux/frugalware06_04.png)

    Frugalware est très rapide à proposer des paquets récents pour sa
distribution et c'est super appréciable. Ainsi wireshark (ex ethereal)
était non seulement présent dans les paquets mais dans sa dernière
version lors de mon test. C'est une des raisons de mon attachement a
Gentoo, si on veut la dernière version Y du projet Z, une petite
commande plus tard, c'est réglé. Frugalware propose à peu près la même
chose, avec tout autant de simplicité. J'ai aussi testé pour vous le
streaming audio (radio internet) sur lequel j'ai enlevé le plugin
firefox pour installer kaffeine qui sous KDE représente mon lecteur
favori pour les médias internet. Ici encore aucun souci à signaler. Il
en va de même pour la lecture de DVDs protégés, libdvdcss2 faisant
partie des paquets, j'ai pu lire tous mes DVDs.

[![](http://frlinux.net/pictures/linux/frugalware06_05s.png)](http://frlinux.net/pictures/linux/frugalware06_05.png)

    J'ai joué rapidement avec les autres gestionnaires et environnements
de bureau présents comme Gnome qui n'a pas voulu se lancer correctement,
j'avoue ne pas vraiment avoir cherché où se situait le problème et je
présume juste un problème avec mon installation plutôt qu'un problème de
distribution. XFCE est également disponible et en version 4.4, oui
monsieur ! Cela marche très bien, ici encore rien à redire. A conseiller
pour ceux qui veulent un environnement réactif.

[![](http://frlinux.net/pictures/linux/frugalware06_06s.png)](http://frlinux.net/pictures/linux/frugalware06_06.png)

    On en vient à la fin de cette reconnaissance de la 0.6, qui est une
distribution léchée et facile à installer en 32bits. J'aurais bien sûr
des réserves sur la version 64 bits étant donné que je n'ai juste pas
réussi à l'installer et ce même en tentant un CD netinstall de la
version 0.5 qui doit récupérer la dernière version des paquets stables
lors de l'installation. Pour ce qui est de l'utilisation et des paquets
disponibles, j'ai trouvé le tout simple à utiliser mais les développeurs
de frugalware précisent bien que leur distribution est axée utilisateurs
intermédiaires plutôt que débutant, donc il ne faut pas avoir peur de la
ligne de commande au cas où :) Si vous cherchez une alternative à
Slackware, recompilée en 686 avec un gestionnaire de paquets plus
puissant, cette distribution est faite pour vous.
