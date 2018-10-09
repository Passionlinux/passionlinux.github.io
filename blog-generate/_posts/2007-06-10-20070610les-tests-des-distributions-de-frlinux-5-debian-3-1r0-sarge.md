---
title: Les tests des distributions de FRlinux 5, Debian 3.1r0 (sarge)
date: 2007-06-10 01:56
layout: post
---

*Dernière mise à jour : 26/06/2005*

Eh oui, vous l'attendiez depuis un moment, j'ai finalement fait ce test
pour la nouvelle Debian que personne n'attendait plus (enfin façon de
parler). Donc quoi de neuf au pays du libre ? Eh bien nous commencerons
par [l'annonce
officielle](http://www.fr.debian.org/News/2005/20050606.fr.html). Vous
noterez au passage les changements suivants : noyau 2.6.8 sauce Debian,
KDE 3.3, Gnome 2.8.3, XFree 4.3.0 (oui, vous avez bien lu, mais je vais
y revenir), Gimp 2.2.6, Mozilla 1.7.8, Firefox 1.0.4, Thunderbird 1.0.2,
PosgreSQL 7.0.4, MySQL 4.0.24, GCC 3.3.5, Apache 2.0.54 (il est possible
d'utiliser 1.3.33 si vous le désirez), Python 2.3/2.4, Perl 5.8.4 et
bien plus encore. Il faut préciser que Debian est disponible sur
beaucoup d'architectures, d'où une des raisons de sa sortie retardée. Au
rayon des tests, j'utilise Debian dans un cadre professionnel, je vous
ferais donc part de cette partie à la fin de l'article. Je vais d'abord
me concentrer sur la partie station de travail pour utilisateur moyen.
J'ai testé cette distribution sur de nombreuses machines avec des succès
généralement très bons (sauf certains serveurs Dell que j'ai du
redémarrer en kernel 2.4 pour accéder au lecteur de CD-ROM). Ma machine
principale de test était un Athlon XP 2600+ avec 1GO de RAM, une geforce
6800GT avec écran Samsung 171P LCD 17", une SBLive Creative et un disque
SATA 250GO sur carte Silicon (sil3112). Des tests divers et variés ont
aussi été fais sur un portable IBM T42 et un Pentium III 500Mhz avec
512MO de RAM. J'ai effectué toutes mes installations avec la
commande **linux26** au démarrage du CD (netinstall) sinon il démarre
avec le 2.4.27 dont je n'ai plus grand besoin. Commençons par
l'installation, qui n'a pas posée de problèmes. Ce qui est sûr c'est que
l'installateur n'est pas un modèle de simplicité. Déployant beaucoup de
serveurs, on va pas se plaindre, j'aime bien le mode texte mais cela
peut rebuter quelques uns. L'installateur supporte à présent la création
de partitions RAID pour faire une installation directe, ce qui est
vraiment bien. Premier démarrage et choix des paquets, je prends station
de travail, ce qui demande environ 350MO de téléchargement (KDE + Gnome
+ le système XFree), sur une ligne 2MO, j'en ai eu pour environ 20
minutes. Vient ensuite le paramétrage de X, je savais que 4.3 était
ancien. Pour des problèmes de licence, 4.4 n'a jamais été porté dans
sarge et X.org (son successeur libre dans l'esprit de la licence GPL)
n'arrivera que dans la prochaine version de Debian. J'ai donc rusé et
installé les pilotes non officiels d'un mainteneur Debian. Il vous
faudra donc éditer votre **/etc/apt/sources.lists** et ajouter :

-   *deb http://people.debian.org/\~rdonald/nvidia unstable/i386/ deb
    http://people.debian.org/\~rdonald/nvidia unstable/all/*

Vous pouvez aussi recompiler votre kernel mais vu le travail de cette
personne, je trouve plus judicieux de s'en servir. Il vous faut alors
ensuite recompiler le pilote pour votre carte, j'ai pour cela utilisé
ce [petit script](http://frlinux.net/files/debian_mk_nvidia.txt) fait
maison. J'ai alors pu configurer et démarrer mon interface X qui ne
voulait pas de mon 1280x1024 car il était un peu perturbé par mon
moniteur LCD. J'ai dû ici aussi modifier mon fichier de configuration
pour entrer les bonnes résolutions et ModeLines. Quelques peu irritant
si l'on considère que les autres distributions le font correctement (une
des raisons pour lesquelles Ubuntu, projet dévié de Debian, a intégré
X.org dans sa distribution). Premier démarrage sous Gnome (choix par
défaut de Debian). La version 2.8.3 est celle fournie par la
distribution, qui se veut d'ailleurs de très bonne facture, je n'ai pas
trop besoin de revenir sur cet environnement.

[![](http://frlinux.net/pictures/linux/debian31_01s.png)](http://frlinux.net/pictures/linux/debian31_01.png)

Une fois les bons pilotes installés, l'accélération 3D est correcte,
mais pas top. Bon ok, une moyenne de 8800fps c'est bien, mais sur ma
gentoo, la même machine obtient 11000fps en 24bits. Principalement car
j'active le Fast Write et le Side Bandwidth. Synaptic est un
gestionnaire de paquets en mode graphique (pour le mode texte, préférer
aptitude qui fait du très bon travail). Synaptic a été bien retravaillé
et je considère maintenant à l'utiliser alors que je préférait le mode
texte auparavant. Pour la partie son, j'ai eu quelques soucis. En effet
l'installation station de travail n'installe pas les pilotes ALSA, mais
le correctif est simple, faîtes un simple : **apt-get install alsa-base
alsa-utils && alsaconf** ce qui va vous paramétrer tout seul comme un
grand votre carte (si celle-ci est bien supportée par Linux). Vous
pouvez ensuite changer les niveaux sonores par la
commande **alsamixer** et appuyez sur M si le volume sonore principal
marque Mute.

[![](http://frlinux.net/pictures/linux/debian31_02s.png)](http://frlinux.net/pictures/linux/debian31_02.png)

L'installation station de bureau vous donne aussi KDE 3.3, je sais que
KDE 3.4 est dans les bacs mais la philosophie Debian et de rendre le
plus stable possible les applications proposées dans la version stable
et c'est exactement ce qu'ils font. A signaler que pour sarge et XFree.
des paquets X.org existent que vous pouvez trouver ici
: [http://www.debian-desktop.org/](http://www.debian-desktop.org/pub/linux/debian/xorg-6.8.2/).
Je vous déconseille l'intégration des paquets Ubuntu. Pour la petite
histoire, j'utilise sarge en installation depuis plus d'un an sur des
stations d'université et cela marche vraiment bien, tout le matériel se
fait généralement détecter sans aucun problème et les stations sont
relativement stables.

[![](http://frlinux.net/pictures/linux/debian31_03s.png)](http://frlinux.net/pictures/linux/debian31_03.png)

Toujours dans la section multimédia, totem est disponible pour lire des
DVDs et autres médias. J'ai installé libdvdcss pour lire les DVDs des
méchants d'hollywood. J'utilise pour cela les paquets de [Christian
Marillat](http://sft.if.usp.br/debian-marillat/), qui sont disponibles
pour x86. La même page contient des sources pour PPC et AMD64, donc je
vous conseille un petit passage par ce site pour récupérer des paquets
tels que mplayer, libdvdcss, etc ...

[![](http://frlinux.net/pictures/linux/debian31_04s.png)](http://frlinux.net/pictures/linux/debian31_04.png)

Debian livre Evolution 2.0.4 (suite logicielle comparable à Outlook) qui
vous permettra de gérer efficacement votre vie professionnelle et
recevoir ces emails super importants sur la réunion de 15h.
OpenOffice.org est livré en version 1.1.3 ce qui se fait un peu vieux
(en effet la 1.1.4 est la dernière stable et la 2.0 est en passe de
devenir la nouvelle stable) mais il faut encore ici resituer la rigidité
de Debian en ce qui concerne la correction de bogues. Resituons
également le contexte en précisant qu'ils maintiennent 11 architectures
(fortement ouvert à discussion en ce moment d'ailleurs), et que les
bogues sont différents selon les plateformes.

[![](http://frlinux.net/pictures/linux/debian31_05s.png)](http://frlinux.net/pictures/linux/debian31_05.png)

Le support des périphériques USB n'a posé aucun problème, enfin presque.
Il n'aime pas que je ne sois pas root, notamment pour mon scanner. La
solution est de bien préciser votre utilisateur dans le /etc/groups pour
hal, audio, cdrom, scanner, etc ... Il est bien sûr possible de modifier
les permissions de **/proc/bus/usb** mais pour une raison obscure, il
n'a pas voulu. La gestion multimédia a sinon marchée sans aucun souci.

[![](http://frlinux.net/pictures/linux/debian31_06s.png)](http://frlinux.net/pictures/linux/debian31_06.png)

Une petite note à présent concernant le déploiement de Debian en
environnement de serveurs. J'utilise Debian depuis 5 ans et sid
(instable) depuis 3 ans en serveurs, ainsi que plusieurs variétés de
stable (potato, woody et sarge) et je dois dire que pour du serveur,
Debian marche excessivement bien, une fois installé, plus aucun besoin
de réinstaller quoique ce soit, toutes les mises à jour sont par le
réseau mais là où certaines distributions rendent la mise à jour
incompatible, Debian a toujours mis un point d'honneur à faire de chaque
mise à jour l'opération la plus simple possible. Enfin, pour ce test, je
dois dire que Debian Sarge est quand même très loin de Woody (dont
j'avais fait le test en septembre 2002). Sarge contient plein de bonnes
choses qui devraient faire le bonheur des administrateurs en ce qui
concerne l'administration par le réseau d'un parc de machines (que cela
soit stations ou serveurs). Les plus fous tourneront en sid (j'ai
plusieurs serveurs sous sid) ce qui marche franchement pas trop mal si
ce n'est un bug critique tous les 6 mois ou plus. Donc sarge a beaucoup
pour plaire, et pourra séduire beaucoup de personnes par sa simplicité
d'administration. Elle ne fait pas partie des distributions les plus
simples à installer mais une fois en place, sa communauté a suffisamment
à apporter pour contenter.
