---
title: Bon, me voici sur Calculate linux
date: 2017-01-12 12:16
layout: post
---

Contrairement a ce que je disais sur le billet [Calculate linux, la
Gentoo pour humain, oui mais pas pour
moi!,](http://passiongnulinux.tuxfamily.org/2017/01/11/calculate-linux-la-gentoo-pour-humain-oui-mais-pas-pour-moi/)
je n'ai pu rester sur une défaite surtout que le monde Gentoo m'attire
de plus en plus. Alors hier (mardi 22h30) après ma journée de travail et
après avoir pris un petit repas du soir, je me suis attelé a réinstaller
la distribution sur le PC principale, une installation rapide via une
clef USB, en 8 minutes c'était torché.
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170109_102134-1024x576.png){.aligncenter
.size-large .wp-image-994 width="525" height="295"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170109_102935-1024x576.png){.aligncenter
.size-large .wp-image-995 width="525" height="295"} Au premier
démarrage, j'ai lancé une mise a jour pour synchroniser ma distribution
aux différents dépôts (si dépôt est le terme qui convient?), cette
première mise a jour fut longue pour seulement une quarantaine de
paquets mais les installations suivantes fut plus rapide, notamment mes
192 paquets a rajouter qui ont été assez vite en comparaison, toujours
pas aussi vite que sur une distribution binaire mais toute de même assez
rapide pour me permettre d'aller "seulement" prendre ma douche et pas
plus! Oui les 192 paquets, environs bien sur, ont prit un peu moins de
30 minutes, bon c'est sur que sous Opensuse on aurait mis 5 ou 10
minutes a tout casser car le plus long est le téléchargement sur les
serveurs de SUSE,  mais la je suis assez content.
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170111_124227-1024x336.png){.aligncenter
.size-large .wp-image-998 width="525" height="172"} Vers 3 heure
(mercredi matin), j'avais un système qui ressemble plus ou moins a ce
que j'ai habituellement sur une distribution binaire, c'est a dire, tout
kde, avec un pare-feu (ufw), mldonkey et amule, soundkonverter,
virtualbox (non fonctionnel car non trouvable dans les menu ou dans la
console), vlc, mes jeux comme 0ad, minetest, flightgear... et mes
émulateurs dgen, gens, scummvm, stella, nestopia, fceux, fusion et
arnold via les archives des sites, d'autres choses aussi que je n'ai pas
en tête.  
<!--more-->  
Je ne pige pas tout, je dois bien l'avouer, des fois le terminal me dit
un truc sur emerge et je suis la a essayer de comprendre, l'autre chose
c'est que j'ai rien pigé a l'installation de virtualbox, il est bien
installé mais totalement absent de la liste des programme de KDE et
quand je tente de le lancer dans une console, il n'est pas trouvé... Il
faut cependant comme sous suse, se rajouter dans le groupe vboxusers
avec la commande:

    usermod -G vboxusers -a utilisateur

Rien de transcendant ou de compliquer vu que tout est dit a la fin de
l'installation. Par contre il reste totalement absent! Je verrais sur
IRC si une bonne âme peut me dépanner. Alors tout n'est pas rose, je ne
cesse de le dire, cette lenteur est rédhibitoire, je ne maîtrise pas
assez emerge pour pouvoir en profiter a fond, pour le moment je
l'utilise comme j'utiliserais APT ou Zypper, c'est a dire un simple
gestionnaire de paquets! J'ai aussi du mal a comprendre comment on
installe une version précise, j'ai compris qu'il fallait utiliser emerge
de cette façon:

    emerge =net-firewall/ufw-frontends-0.3.2-r3

Mais a chaque fois j'ai une impossibilité de le faire, je pense qu'il
faut ajouter des "écarts de conduite" a un fichier. Alors quoi de beau,
j'ai installé tout mes paquets, plus de 200 paquets en tout et pour
tout, mais ça m'a pris une bonne partie de la nuit et du petit matin, si
je compare avec une Debian ou openSUSE, j'aurais eu pour une vingtaine
de minutes pour tout faire mais bon. Pour être honnête encore une fois
et cela jusqu'au bout, c’est que la compilation avant l’installation
permet de faire gagner du temps lors du lancement des programmes et de
leur utilisation, mais il faut regarder les secondes ou minutes gagnées
avec le temps perdu précédemment en compilation. Gagner 20 secondes lors
de chaque lancement de fligthgear vaut-il la perte de 60 minutes de
compilation à chaque mise à jour… Je ne suis pas convaincu. L'autre
point qui me déplaît est l'embonpoint de la distribution, sous openSUSE
je suis dans les 14 Go avec en plus mes sauvegarde Snapper (sauvegarde
de mon système), avec Calculate je suis directement a 18 Go (sur la
capture suivante je suis un peu moins mais avec quelques paquets qui me
manquaient) pour bien moins de paquets installés, je n'ai pas installé
tous mes jeux, ni mes applications... Le dernier point est simplement
que je ne vois pas d'amélioration de vitesse de mon PC, je ne remarque
rien.
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170111_125052-1024x576.png){.aligncenter
.size-large .wp-image-999 width="525" height="295"} Vu que je suis têtu,
je garde la Calculate xfce sur le portable mais pour le fixe c'est autre
chose, on verra, pour le moment à chaque fois que je met la galette
d'openSUSE dans le tiroir de mon PC, j'ai un sentiment de gâchis et de
facilité, du coup j’arrête aussitôt le boot de l'installateur et je
relance ma Calculate, combien de temps va durer ce sentiment?
