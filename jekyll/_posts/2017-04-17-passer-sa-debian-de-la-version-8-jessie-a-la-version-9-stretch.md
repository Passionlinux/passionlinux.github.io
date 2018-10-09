---
title: Passer sa Debian de la version 8 Jessie à la version 9 Stretch.
date: 2017-04-17 00:07
layout: post
---

Je vais vous parler aujourd'hui de Debian, chose rare sur ce blog, mais
surtout de ce qu'on appel un dist-upgrade ou saut de version. On entend
souvent comme défauts des distributions de layout version fixed release
qu'elles sont obsolètes et qu'il faut se taper une réinstallation tous
les 6 mois, 2 ans ou plus pour certaines. Pour le coté obsolète, j'en ai
longuement parlé ici même, comme quoi on est pas tous fanatique de la
course à la version, cette course à la plus grosse; et que certains
préféraient être plus tranquille en étant sur des distributions stables
et bougeant peu, c'est le cas de Debian. Aussi car on peu le souligner,
Debian a un dépôt backport (rétro-portage) qui est un peu particulier
puisque il ne suffit pas de l'activer mais il faut implicitement
ordonner à APT d'utiliser la version dans backport pour installer un
logiciel, ensuite seulement ce paquet sera mis à jour depuis ce même
dépôt et ne suivra plus la version des dépôts classiques. On installera
un paquet depuis backport de la façon suivante:

    apt-get -t jessie-backports install libreoffice 

J'en avais parlé
[ici](http://passiongnulinux.tuxfamily.org/2016/06/03/20160603les-retroportages-depot-backports/).  
<!--more-->  
Pour le coté chiant de la grosse réinstallation tous les 6 mois, 2ans ou
plus, c'est simplement faux! Bien sur que l'on peut si on le souhaite,
mais Debian a été pendant longtemps la seule à proposer et a être
capable de faire un saut de version +1 de chaque release, par exemple
passer de Etch (Debian 4) à lenny (Debian 5), aussi simplement qu'en
faisant une mise à jour classique. Encore un avantage que les
détracteurs des fixeds releases oublient facilement planqué derrière
leurs saintes rollings releases... J'exprime un avis personnel, de mon
point de vue, c'est plus facile de gérer des systèmes fixes et de migrer
une fois tous les deux ans comme je fais avec ma Debian depuis 2007 que
de gérer des rollings et leurs conséquentes mises a jour. Quand c'est
notre système, il y a pas de soucis, surtout que l'on trouve facilement
des distributions rollings qui sont calme coté mises a jour, comme
Calculate linux qui tourne entre 20 et + de 50 mises a jour par semaine
mais quand c'est un système ou on joue le rôle du technicien, de
l'informaticien de service ou de réparateur, c'est autre chose. J'ai
vraiment pensé que Calculate chez mes parents allait être la perle rare,
celle qui allait gentiment se mettre a jour en continu mais en suivant
un flux gérable et pas devoir me taper la mise a jour de 400 paquets, je
me suis trompé. Je me suis trompé et le réseau de chez mes parents a
fini par me démoraliser, je peux dire merci a SFR pour cela. Mais bon,
je leur ai remis une Ubuntu comme ils aiment, en attendant la sortie de
la Debian 9. De mon coté je me suis remis à un full Debian, fini
l'époque où je voulais être indépendant du format de paquets, ne plus
être formaté par Debian, toucher à autre chose, bref fini cette époque.
Debian et moi c'est une longue aventure, je l'ai connu en 2006 avec une
Sarge que j'ai vite abandonné pour ma Mandriva 2006, à ce moment je
n'aurais jamais cru faire de Debian ma distribution personnel. C'est
avec Etch que tout a réellement commencé, elle était de très bonne
qualité et bien fini, c'était aussi un bond pour debian qui annonça le
début d'une longue série de simplifications aussi bien dans
l'installateur que dans la maintenance de cette distribution. J'en ai
installé à tout va, par ci par là, chez des amis, des parents, des
oncles, partout, sur du vieux matos et sur du plus récents. J'ai suivi
les différentes versions de deux méthodes, sur certaines machines
c'était la méthode classique qui consiste à une réinstallation de la
nouvelle version tous les deux ans, c'était souvent la méthode que
j'utilisais quand la connexion internet était pourris comme en pleine
campagne. Généralement je prenais la deuxième méthode qui consiste a
faire une grosse mise a jour en changeant le nom de version dans le
fichier "sources.list". La seule fois où j'ai pas utilisé cette manière,
c'est pour le passage de Wheezy vers Jessie à cause de systemd, c’était
fonctionnel mais pas propre au niveau de l'init, on restait sur l'ancien
init, ou sinon il demandait quel init utiliser lors de la mise à jour,
je me souviens pas trop. Il y a des versions de Debian que j'ai gardé
longtemps, comme Etch, Lenny et Squeeze. Etch a été ma porte d'entrée
pour m'habituer et donc je l'ai gardé jusqu’à son remplacement par
Lenny, j'ai ensuite gardé cette dernière longtemps puisque ce fut la
dernière a proposer KDE3 au lieu de KDE4. J'ai ensuite migré vers
Squeeze et Gnome2 car KDE4 dans sa version Squeeze était castré de
fonctions. Pour ce qui est de Wheezy, je n'en garde pas beaucoup de
trace, je ne l'ai pas gardé longtemps, ni Gnome-shell ni KDE4 était
satisfaisant pour moi et je suis vite passé à Testing puis à SID. Voila
comment on arrive à Jessie, une révélation, juste la meilleur de toute,
je l'ai gardé longtemps, jusqu’à hier en somme. Première Debian a mettre
en avant la simplification absolue, l'ergonomie, c'est avant tout grâce
à Gnome et son bureau spécial, certes, mais tellement centré sur
l'utilisation et non sur la manière de faire. J'aurais pu garder encore
longtemps ma Jessie, j'avais tout ce qu'il me fallait et même des jeux
que je joue dans leurs dernières versions comme 0AD (backport). Je me
suis décidé à sauter le pas vu le peu de temps qu'il reste avant que
Stretch devienne la Stable, c'est l'histoire de deux a quatre mois, je
ne pense pas plus, de mon coté je mise sur Mai. Alors voila la partie
qui va faire hurler les accros des rollings, la partie où j'explique
comment passer proprement d'une version à une autre, pourquoi vont-ils
râler, simplement qu'une fois de plus je met leur théorie sur les
distributions fixed release à mal, ils disent que c'est chiant et qu'il
faut faire une réinstallation tous les deux ans, mais je leur montre que
non, ils vont alors dire que je passe par une très grosse mise à jour
peu fiable, je leur répondrais ceci: calculez vos mises à jour sur deux
ans, je suis sur que vous faite plus de mises à jour que moi et ma
debian stable. Là je pars sur de l’hypothétique, si ma debian Jessie a
eu 1000 mises a jour sur deux ans (c'est énorme, je pense plutôt qu'on
est a la moitié seulement) + les 1719 du saut de version que je fais, la
sommes tourne dans les 2719 mises à jour pour deux ans, à titre de
comparaison, sur Calculate en trois mois j'avais allégrement dépassé les
1000 mises a jour rien qu'avec ceux de Plasma5. Faut quand même que je
mette entre parenthèse la procédure pour expliquer deux ou trois choses.
Tout d'abord cette procédure est officiellement supporté par Debian, qui
garantie le passage entre chaque version. Autre chose qui n'est pas des
moindres, cette procédure est réalisable à condition de rester avec les
paquets venant des dépôts officiels, on oublie donc les dépôts externes
du layout de ceux de Google, les PPA qui sont normalement pour Ubuntu, les
deb-multimédia et autres dépôts. Pour finir cette méthode est exactement
la même que pour passer de stable a testing ou sid. Donc pour commencer
avant toute chose, il faut ajouter les dépôts de la stretch, donc je
reprend mon sources.list:

    # Debian Jessie, dépôt principal + paquets non libres deb http://httpredir.debian.org/debian/ jessie main contrib non-free # Debian Jessie, mises-à-jour de sécurité + paquets non libres deb http://security.debian.org/ jessie/updates main contrib non-free # Debian Jessie, mises-à-jour "volatiles" + paquets non libres deb http://httpredir.debian.org/debian/ jessie-updates main contrib non-free # Debian Jessie, dépôt de rétroportages ("backports") deb http://httpredir.debian.org/debian jessie-backports main contrib non-free # depots sources deb-src http://ftp.fr.debian.org/debian/ jessie main contrib non-free deb-src http://security.debian.org/ jessie/updates main contrib non-free deb-src http://ftp.fr.debian.org/debian/ jessie-updates main contrib non-free deb-src http://ftp.fr.debian.org/debian/ testing main contrib non-free deb-src http://security.debian.org/ testing/updates main contrib non-free deb-src http://ftp.fr.debian.org/debian/ sid main contrib non-free # testing #deb http://ftp.fr.debian.org/debian/ testing main contrib non-free #deb http://security.debian.org/ testing/updates main contrib non-free # unstable #deb http://ftp.fr.debian.org/debian/ unstable main contrib non-free # experimental #deb http://ftp.fr.debian.org/debian/ experimental main contrib non-free

Et je rajoute donc ceux de Stretch qui sont du même exemple que ceux de
Jessie:

    deb http://ftp.fr.debian.org/debian/ stretch main contrib non-free deb-src http://ftp.fr.debian.org/debian/ stretch main contrib non-free deb http://security.debian.org/ stretch/updates main contrib non-free deb-src http://security.debian.org/ stretch/updates main contrib non-free # Stretch-updates, previously known as 'volatile' deb http://ftp.fr.debian.org/debian/ stretch-updates main contrib non-free deb-src http://ftp.fr.debian.org/debian/ stretch-updates main contrib non-free # Debian Stretch, dépôt de rétroportages ("backports") deb http://ftp.fr.debian.org/debian stretch-backports main contrib non-free

En gros vous l'auriez compris, il suffit de changer jessie par stretch
dans les mêmes lignes. Voila ce que ça donne dans nano:
![](http://download.tuxfamily.org/passionlinux//2017/04/Capture-décran-de-2017-04-16-140624b-922x1024.png){.aligncenter
.size-large .wp-image-1197 width="525" height="583"} Ensuite c'est de la
logique, on ouvre un TTY diffèrent de celui qu'on a notre session et on
lance la commande de mise a jour:

    #apt update && apt dist-upgrade

On ne lance surtout pas la commande dans sa propre session graphique
sans ça c'est sur qu'il y aura des soucis!!! Dans l'exemple ci-dessous
je lance la mise à jour dans un terminal de ma session graphique Gnome,
juste pour voir ce que donnait la mise à jour mais je ne la fait
réellement qu'en dehors de celle-ci.
![](http://download.tuxfamily.org/passionlinux//2017/04/Capture-décran-de-2017-04-16-140624-1024x337.png){.aligncenter
.size-large .wp-image-1198 width="525" height="173"}
![](http://download.tuxfamily.org/passionlinux//2017/04/Capture-décran-de-2017-04-16-140624c-909x1024.png){.aligncenter
.size-large .wp-image-1199 width="525" height="591"} On redémarre la
machine et on aura une Debian 9 fonctionnelle. Est ce si difficile?
![](http://download.tuxfamily.org/passionlinux//2017/04/Capture-décran-de-2017-04-15-18-28-42-1024x337.png){.aligncenter
.size-large .wp-image-1201 width="525" height="173"}
![](http://download.tuxfamily.org/passionlinux//2017/04/Capture-décran-de-2017-04-15-18-29-26.png){.aligncenter
.size-full .wp-image-1203 width="740" height="512"}
