---
title: Alors quoi de beau sur Calculate?
date: 2017-01-27 00:54
layout: post
---

Je vous annonce de suite la couleur, je commence a être attaché a cette
distribution, j'ai plusieurs billets en cours sur la gestion des paquets
sous Calculate mais pour le moment c'est un peu juste. Alors quoi de
beau sur Calculate, je dirais que la base Gentoo est encore plus
frileuse que Debian, Si on compare une Sid et une Gentoo, il y a
certains choix très inattendu, mais bon, on voit ça comme un gage de
stabilité, bizarre mais quand c'est Debian, on dit tout de suite que
c'est de l'obsolescence ! Bon parlons pas de ce qui fâche, parlons de ce
qui me plait vraiment sur cette gentoo-like, ce que j'appel la
compilation a la chaîne, avec de simple useflags on change quelques
principes d'optimisation pour la compilation des différents programmes
et composants, en enlevant ou ajoutant des options.   
<!--more-->  
Dans mon cas, j'en utilise déjà pas mal, pour Mldonkey, pour Amule, pour
Gwenview, pour Scumm... J'ai enfin un OS qui permet de gérer les options
de compilations de mes programmes sans passer par de lourdes
manipulations. Je reprend un exemple que je vais détailler plus tard
dans un billet sur Emerge, je reprends le cas de Mldonkey, si je reprend
[le billet sur Debian et le rebuild d'un
paquet](http://passiongnulinux.tuxfamily.org/2016/06/03/20160603creation-de-paquets-deb-methode1-dpkg-buildpackage/),
en l'occurrence le même (Mldonkey), on s'aperçois que pour changer des
options de compilation de notre paquet, il faut simplement le rebuilder.
C'est simple mais pas automatique, ça demande du temps et de refaire pas
mal de chose a la mimine, je cite ici les différentes étapes:

1.  Je récupère les sources de debian, apt-get source nom\_du\_paquet ou
    par exemple :

        apt-get source mldonkey

2.  Je m’occupe donc de mettre une version différente de celle du dépôt
    pour pas entrer en conflit avec les paquets du dépôt, par exemple si
    c’est la version 3.5.1 dans le dépôt, je change le miens
    en 3.5.1-scha1. Je le fais avec dch, :

        dch -v 3.1.5-2.scha1

3.  J’effectue les modification, admettons que je veux seulement changer
    un truc dans la compilation, par exemple la prise en charge de tout
    les protocoles, faudra aller dans le fichier rules du
    dossier /debian. Le fichier control me sers a transcrire les
    changements et alleger les dépendances (debian aime bien donner des
    versions a ses dépendances ce qui est nécessaire car elle a
    plusieurs versions (stable, testing, sid))Changements apporté au
    fichier rules :

         enable-multinet  enable-bittorrent  enable-filetp  enable-gnutella  enable-gnutella2  enable-fasttrack

    Description supplémentaire apporté au fichier changelog :

        mldonkey (3.1.5-2.scha1) UNRELEASED ; urgency=medium  * Activation des réseaux fasttrack, bittorrent, gnutella1&2, filetp  Sebastien CHA <sebastien@xxxxxxxx.xx.xx> Wed, 15 Apr 2015 14:04:01 +0200

4.  On télécharge les dépendances du paquet a construire :

        # apt-get build-dep mldonkey

5.  Ensuite pour construire le paquet on rentre un

        dpkg-buildpackage -rfakeroot -us -uc

    (-us -uc pour ne pas chiffrer avec une clef) A la suite de quoi nos
    nouveaux paquets sont disponibles comme on peut le voir par un « ls
    » :

        [ /Public/debian] :$ ls mldonkey-3.1.5 mldonkey_3.1.5-2.scha1.dsc mldonkey_3.1.5-2.debian.tar.xz mldonkey_3.1.5.orig.tar.bz2 mldonkey_3.1.5-2.dsc mldonkey-gui_3.1.5-2.scha1_amd64.deb mldonkey_3.1.5-2.scha1_amd64.changes mldonkey-server_3.1.5-2.scha1_amd64.deb mldonkey_3.1.5-2.scha1.debian.tar.xz

    <p>
    Ce sont des étapes faciles mais pas anodines, je m'explique, a
    chaque mise a jour de ce paquet, on devra recommencer a refaire les
    étapes, ça va sur une Debian Stable qui bouge peu mais ça peu
    devenir vite lassant pour les autres versions. Je précise vite fait
    que les paquets RPM sont dans le même cas que Debian...

Alors c'est vrai qu'on peut se faciliter la vie et passer par debuild,
mais ça reste quand même quelque chose qui devra être recommencé a
chaque changement ou mise a jour des dépendances de compilation ou du
logiciel en lui même. Et c'est là où je veux en venir, sous Gentoo, donc
sous Calculate, on informe le fichier /etc/portage/package.use/custom
pour lui dire ce qu'on veut comme option de compilation, de cette
manière:

    Mldonkey net-p2p/mldonkey gnutella fasttrack

Puis on réinstalle le paquet normalement avec un *emerge
-avq net-p2p/mldonkey*, ce qui va lancer la compilation avec les
nouvelles options. Et a chaque mise a jour du paquets ou d'une de ses
dépendances, le paquets sera automatiquement recompilé avec les options
qu'on a donné. Du coup, je me suis amusé a mettre des useflags dans
certains de mes paquets habituels:

    ##fichier qui permet de changer les options de compilation differents # THUNDERBIRD #mail-client/thunderbird -linguas_* linguas_fr #mail-client/thunderbird -L10N_* L10N_fr # LANGUES #app-text/hunspell -linguas_* linguas_fr #app-text/hunspell -L10N_* L10N_fr app-text/aspell -linguas_* linguas_fr # SMPLAYER #media-video/smplayer -qt4 qt5 # Gwenview kde-apps/gwenview kipi # scummvm games-engines/scummvm mpeg2 # Ktorrent net-p2p/ktorrent infowidget # Kget #kde-apps/kget bittorrent ## Amule net-p2p/amule upnp geoip ## Mldonkey net-p2p/mldonkey gnutella

Bon pour ce qui est de ktorrent et de gwenview, je pense que ce sont des
oublis ou des tentatives d'alléger la distribution en retirant des
choses qui sont activés chez les autres distributions. Kipi permet a
gwenview d'avoir les modules-externes et infowidget permet a ktorrent de
nous donner pas mal d'infos sur le torrent. Si j'y pense je ferais peut
être une demande de bugs pour ces deux là.  Celui qui m’intéresse le
plus, celui que j'ai déjà parlé, c'est bien sur Scumm avec Mpeg2, qui
permet de lire les vidéos de nos jeux... Primordiale et pourtant aucunes
distributions n'activent cette option. Bon que dois je penser de cette
semaine sur Calculate? Je m'y sens vraiment bien, c'est pas le grand
coup de foudre comme j'ai pu avoir avec Frugalware, NuTyX et surtout la
désormais morte 0linux mais c'est une belle découverte. Je m'y sens pas
aussi serein que sous 0linux où je savais ou du moins j'arrivais a
pondre des paquets avec des recettes de ma création, mais au moins
j'arrive a avoir ce que je veux dans le grand nombre de paquets issus de
Gentoo. Pour ce qui est de la création de paquets, il faudrait déjà que
je comprenne quelque chose aux recettes de Gentoo.... :-) Je pense pas
gagner quoique ce soit par rapport a mon openSUSE, la Tumbleweed est
bien plus a jour, a plus de paquets, consomme moins de ressources mais
je m'y sens bien sur cette Calculate. Sur [IRC](#calculate-fr), on est
pas nombreux mais l'ambiance est sympathique. Voila pour ce qui est de
ma semaine de plus sur cette distribution. Je pense que cette semaine
j'aurais réussi a pondre un tuto sur la base d'emerge, mais bon, les
weeks sont courts et les semaines se ressemblent et ne me laissent pas
beaucoup de répits ;).
