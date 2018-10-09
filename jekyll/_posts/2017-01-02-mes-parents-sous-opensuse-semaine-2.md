---
title: Mes parents sous openSUSE semaine 2
date: 2017-01-02 18:38
layout: post
---

Dans le billet précédent, [Mes parents sous openSUSE : semaine
1](http://passiongnulinux.tuxfamily.org/2017/01/01/mes-parents-sous-opensuse-semaine-1/),
je racontais un soucis de droits sur les photos venant de l'appareil
photo, je disais ceci en l’occurrence:  

> Il y a aussi un soucis de droits sur certaines photos prissent avec
> leur appareil photo, je ne sais pas trop pourquoi, peut être un groupe
> différent, va falloir que je regarde de plus prés.
> </p>

<!--more-->  
J'ai vérifié sous XFCE et je n'avais pas eu de soucis, l'appareil
connecté s'ouvrait directement via
[Thunar](https://fr.wikipedia.org/wiki/Thunar) dans le dossier /DCIM et
on pouvait tout faire avec les bon droit dés le départ. En revanche avec
Plasma5, ce n'était pas du tout la même histoire, l'appareil s'ouvrait
dans [Dolphin](https://fr.wikipedia.org/wiki/Dolphin_(logiciel)) mais
dans un autre dossier amont, /camera en l’occurrence et une fois copié
les photos dans un dossier local, ils n'avaient plus les bonnes
permissions. Encore une fois ce que j'ai fait est très simple, me
doutant que KDE voulait trop bien faire, j'ai ouvert l'appareil photo
via l’icône USB en bas dans le panel, puis au lieu de faire comme
habituellement ouvrir via le gestionnaire de fichier j'ai fait ouvrir
avec [digikam](https://fr.wikipedia.org/wiki/DigiKam) et la miracle,
l'importation fut bien plus rapide, les actions sur les photos et vidéos
aussi comme supprimer et surtout une fois les fichiers (photos ou
vidéos) importés, ils avaient les bon droits... Donc il ne reste plus
que cette histoire de traduction, Plasma ayant par moment des parties
anglophones comme "coller" qui devient "paste", et bien d'autre. Oh bien
sur dans mon cas ce n'est pas gênant, je ne suis pas un grand fan de
l'anglais dont je fuyais les court en séchant mais je comprend la langue
assez facilement mot par mot, c'est tout autre chose pour mes parents
qui eux sont réfractaire aux langues étrangères. Il va falloir que je
fasse certainement une entorse de mes principes sur le fait de sacrifier
un peu de stabilité en activant les dépôts KDE d'openSUSE. On verra ça
un peu plus tard. Ce qui se profile a l'horizon, en tout cas ce que j'ai
pu entendre/comprendre entre les lignes/mots, c'est que son portable
marche vraiment bien, qu'il fallait pas que je change sur le portable,
donc en gros, ne touche pas a Ubuntu sur le portable et tant que tu y es
remet la moi sur le desktop... Globalement, ils sont content de Plasma5
et d'openSUSE leap, je suis sur que XFCE leur conviendrait mieux mais
faudrait que je fasse ça en douce de telle manière que cela passe
inaperçus et c'est bien plus dur que l'on croit. Ce que j'aime bien avec
openSUSE, c'est simplement
[YAST](https://fr.wikipedia.org/wiki/OpenSUSE#Centre_de_contr.C3.B4le_YaST),
en plus d’être LE centre de contrôle "fait tout" de la distribution,
c'est aussi un outils très pratique a distance via SSH qui permet de
faire pratiquement tout ce qu'on ferait en temps normale via des
commandes dans un terminal de façon graphique. Voila la semaine 2 est
fini, il n'y a plus de soucis a part cette traduction non fini de
Plasma5, je vais regarder comme déjà dit, si l'activation de dépôts
supplémentaires arrange ou non ce souci.  De mon coté, je ne pense plus
bouger, j'ai enfin un truc qui me fait lâcher Debian pour de bon, je
teste néanmoins des distributions, Mageia principalement pour voir ce
qu'elle devient, si oui ou non elle arrive a sortir une version 6 et
puis les gentoo-likes qui m'attirent de plus en plus, notamment
[Calculate-linux](https://fr.wikipedia.org/wiki/Calculate_Linux) et
[Sabayon linux](https://fr.wikipedia.org/wiki/Sabayon_Linux).
