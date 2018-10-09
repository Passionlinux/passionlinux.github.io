---
title: Les tests des distributions de FRlinux 7, Debian 4.0 (Etch)
date: 2007-06-10 02:05
layout: post
---

<div>

**Ma premiere debian...**

</div>

<div style="text-align: center;">

</div>

*Dernière mise à jour : 27/05/2007*

Debian 4.0 (Etch) a remplacée la 3.1 (Sarge) 21 mois après la sortie de
la version précédente. Elle contient un bon lot de nouveautés parmi
lesquelles : noyau 2.6.18, GNOME 2.14, KDE 3.5, Xfce 4.4, OpenOffice.org
2.0.4a, Xorg 7.1, iceweasel (Firefox) 2.0, Apache 2.2, MySQL 5.0, Gaim
2.0 et aussi Xen 3 avec les bons noyaux qui vont bien (tm). J'utilise
Debian depuis déjà quelques années et j'ai donc pu comparer les
procédures de mises à jour, différentes nouvelles installations ainsi
que le mode station de travail ou bien encore serveur simple ou avec Xen
(dont je parlerais plus bas). Ces tests ont été effectués autant sur du
x86\_64 (mon X2 amd64 4800+ dont les captures d'écran ci-dessous sont
tirées) ainsi que des plateformes x86 standard. Il faut aussi noter que
cette version officialise le support amd64 dans la branche stable de
Debian. Je n'ai rencontré aucun souci au niveau de l'installation. Cette
nouvelle version comporte également un nouvel installateur en mode
graphique que j'ai eu l'occasion d'utiliser une seule fois et qui marche
relativement bien (en tout cas, pour moi, vu que l'installation était
d'une simplicité déconcertante). J'avoue être toujours aussi fan de la
version curses que l'ont peux lancer de partout (j'ai quelques serveurs
en KVM par IP). J'ai rencontré un seul problème (et pas qu'avec cette
distribution) lié à Xorg 7.1 concernant mon nouveau moniteur Samsung
226bw. Celui-ci est en effet automatiquement configuré en 1280x1024 lors
de l'installation. J'ai ensuite tenté de passer en 1680x1050 toujours
avec le pilote libre nv ce qui n'a pas fonctionné. J'ai du me rabattre
sur le pilote propriétaire nvidia (1.0-9755-x86\_64) qui se sont très
bien comportés. J'ai fait mon premier démarrage graphique sous Gnome
2.14 (qui contient tout de même quelques paquets 2.16). C'est très
fonctionnel et relativement plus propre que Sarge au niveau de la
détection périphérique avec udev. D'ailleurs, pour ceux migrant d'une
version précédente, lisez bien les [notes de mise à
jour](http://www.us.debian.org/releases/stable/i386/release-notes/ch-upgrading.fr.html).

[![](http://frlinux.net/pictures/linux/debian40_01s.png)](http://frlinux.net/pictures/linux/debian40_01.png)

    Debian vient également avec les belles améliorations graphiques
telles que beryl et le composite pour Xorg mais je n'ai pas vraiment
trouvé l'intérêt de jouer avec. Sachez néanmoins que c'est disponible et
qu'il existe plusieurs guides si vous voulez stresser votre carte
graphique. KDE 3.5 est fourni également dans une version suffisamment
récente pour mon utilisation. Vous trouverez également IceWeasel
également connu sous le nom de Firefox. Pour des raisons légales, Debian
a décidé de renommer la bête afin d'éviter tout problème juridique. Pour
plus d'info sur le sujet, consultez la [nouvelle hebdomadaire du
31/10/06](http://www.debian.org/News/weekly/2006/40/index.fr.html).

[![](http://frlinux.net/pictures/linux/debian40_02s.png)](http://frlinux.net/pictures/linux/debian40_02.png)

XFCE 4 (4.4 rc2) est également disponible. Vous pouvez demander lors du
login graphique de l'intégrer avec Gnome, KDE ou tout autre
environnement. A noter que lors de l'installation de base qui ne pose
plus de questions si on fait une installation de bureau classique, les
polices Bitstream Vera ne sont pas installées, vous devez les
télécharger par la suite. J'ai pu tester pour vous les noyaux à base de
Xen, les tutoriaux sur le web sont nombreux, je compte d'ailleurs
bientôt publier le miens vu que j'ai eu quelques demandes et que
j'utilise Xen depuis quelques années à présent. Toujours est-il qu'une
fois tous les bons paquets installés, j'ai pu faire tourner plusieurs
domaines invités qui tournaient tous avec des adresses publiques et
privées selon les environnements. Les performances sont similaires que
sur les autres distributions que j'ai pu tester.

[![](http://frlinux.net/pictures/linux/debian40_03s.png)](http://frlinux.net/pictures/linux/debian40_03.png)

Venons à une partie intéressante de cette distribution : le multimédia.
Comme tous les noyaux 2.6, ALSA règne en maître lorsqu'on en vient à la
gestion sonore. J'ai du sélectionner la sortie numérique de ma carte son
(Creative Audigy 2) afin de pouvoir entendre quelque chose, ensuite un
: **alsactl store 0** plus tard pour garder l'état, j'ai du aussi éditer
le **/etc/group** afin de m'ajouter dans les bons groupes. Une fois ce
détail réglé, kaffeine et mplayer ont gentiment joués mes fichiers
multimédia y compris toute la partie vidéo (DVD, DivX, etc ...).

[![](http://frlinux.net/pictures/linux/debian40_04s.png)](http://frlinux.net/pictures/linux/debian40_04.png)

J'ai voulu voir quelle version de Enlightenment était disponible sous
cette distribution. Debian étant conservatrice, vous trouverez donc la
branche 0.16 dans les paquets, j'ai trouvé quelques références de la
0.17 pour Debian et Ubuntu mais vu que c'est toujours un travail en
cours, cela ne semble pas très actif. 0.16 reste encore pour moi une
version stable et rapide pour votre bureau, cela faisait un bon moment
que je ne l'avais pas utilisée. J'ai également testé le streaming radio
par internet et c'est l'une des premières fois que je vois Totem
m'accepter et m'ouvrir une stream sans m'insulter. Bref, content.

[![](http://frlinux.net/pictures/linux/debian40_05s.png)](http://frlinux.net/pictures/linux/debian40_05.png)

J'ai rencontré quelques soucis avec mon scanner. Ceci dit dans le bon
environnement de bureau (KDE) et une fois que je me suis rajouté dans le
groupe scanner, KDE a été très content de me dire que kooka avait bien
trouvé un scanner millénaire sur mon système et était prêt à l'utiliser
si j'étais psychologiquement prêt. Pour revenir rapidement sur les
passages de sarge vers etch, pensez bien à lire le guide de mise à jour
en lien en début de cet article, j'ai passé pas mal de serveurs de mon
travail de sarge vers etch et le soft raid m'a posé problème (soft raid
sur du LVM) que j'aurais pu résoudre si j'avais lu plus en avant, j'ai
donc perdu 1.5To de données, qu'il m'a fallu quelques heures pour
récupérer (enfin le soft raid lui était mort, j'ai du reprendre d'un
autre système), donc pas la faute à Debian mais bien une faute
utilisateur vu que je n'ai pas tout lu.

[![](http://frlinux.net/pictures/linux/debian40_06s.png)](http://frlinux.net/pictures/linux/debian40_06.png)

Debian prouve encore ici sa grande stabilité malgré le dernier point que
je viens de souligner. Elle est de plus enfin disponible en version
stable pour les plateformes x86\_64 donc que du bonheur. Le passage en
Xorg était attendu pour les utilisateurs de la version stable. La liste
des paquets est assez importante pour satisfaire tout le monde.
L'installation est pour sa part bien plus simple en mode graphique
(attention, le mode par défaut est toujours curses, vous devez
sélectionner l'installateur graphique au démarrage du CD/DVD) pour les
débutants, les vétérans comme moi préféreront le bon vieux mode texte.
Enfin, Debian se comporte toujours aussi bien en mode serveur (85% de
mon parc serveurs est Debian et j'en ai mis à jour environ 70% vers
Etch) et la station est un peu moins simple à configurer qu'ubuntu mais
vous avez l'original ici, pas la copie.
