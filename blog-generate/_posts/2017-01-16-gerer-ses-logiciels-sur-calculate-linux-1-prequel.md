---
title: Gérer ses logiciels sur Calculate linux #1 Préquel
date: 2017-01-16 22:51
layout: post
---

![](http://www.calculate-linux.org/attachments/77/calculatelinux-142x82.gif){.aligncenter}
Je n’arrête plus avec cette distribution, me voila que je la met un peu
partout, pourtant [ça avait plutôt mal
commencé](http://passiongnulinux.tuxfamily.org/2017/01/11/calculate-linux-la-gentoo-pour-humain-oui-mais-pas-pour-moi/)
mais comme une belle histoire d'amour, il faut accorder [une deuxième
chance](http://passiongnulinux.tuxfamily.org/2017/01/12/bon-me-voici-sur-calculate-linux/).
Le point faible de la distribution est sa lenteur dans les mises a jour
et l'installation des paquets; hériter de Gentoo n'a pas que des
avantages, mais comme je l'ai ensuite dis, une fois installé les paquets
vont être mis a jour de temps en temps et même si c'est plus long que
sur des distributions dite binaires, ça reste dans le supportable par
rapport a Gentoo qui peuvent durer des nuits entières! Le point fort de
cette distribution, toujours hérité de Gentoo, c'est son excellent
gestionnaire de paquets, certes un peu lent mais tellement flexible et
sa communauté a l'écoute de ses utilisateurs. Par exemple, je veux
installer un programme qui est dans les dépôts mais dans différentes
versions, je peux choisir la version a installer, je peux aussi
recompiler le logiciel avec des options différentes, je peux lui dire
d'installer toutes versions inférieures a X ou supérieurs... Bref, il
n'y a pas vraiment de limites. Nous verrons ensemble tous ses cas en
condition réel avec des exemples de manipulations concrètes.  
<!--more-->  
Je dois dire que emerge sans connaissance et utilisé comme un simple APT
ou YUM, est très réducteur. Donc pour prendre plaisir et surtout avoir
la pleine puissance de cette distribution, il faut apprendre et
comprendre emerge, c'est pas aussi simple que mon vieux APT ou mon petit
Zypper mais une fois qu'on a un bon tuto c'est que du bon... Sur
Calculate, il y a un nom qui revient toujours, c'est celui d'Adrien.d,
le webmestre de [MLO](https://www.mageialinux-online.org/mlo/) (forum
pour Mageia) mais aussi le blogueur de
[Linuxtricks](http://www.linuxtricks.fr/pages/bienvenue-sur-linuxtricks),
un site ou il rapporte ses connaissances comme dans un pense bête pour
les partager avec tous. C'est donc naturellement là-bas que j'ai cherché
un tuto pour emerge et/ou la gestion de paquets, après tout c’était là
que j'ai eu le déclic pour installer Calculate. Je suis donc allé
naturellement sur ce site et j'ai vu [un tuto toujours en
brouillon](http://www.linuxtricks.fr/wiki/brouillon-calculate-gerer-ses-logiciels),
ce qui est compréhensible vu les possibilités de emerge ! Ce billet
étant toujours en cours et donc incomplet, il ne montre que les
commandes les plus importantes et surtout ceux qui font office d'APT et
de YUM ( ou Zypper, DNF, URPMI...), c'est a dire l'installation simple
d'un paquet, la désinstallation de celui-ci, les mises a jour, la
recherche de paquets... et puis pas grand chose d'autre qui changerait
par rapport a tout autre gestionnaire de paquets. Je dois dire que je me
sentais pas a l'aise avec emerge, je me sens toujours pas a la pointe
avec ce gestionnaire mais depuis ça va quand même bien mieux grâce a une
vidéo que **The Phoenix** m'a conseillé, [une d'Adrien qui m'a
simplement échappé](https://www.youtube.com/watch?v=uYgK6z0QU0k):
https://youtu.be/uYgK6z0QU0k Excellente vidéo qui explique bien avec des
mots compréhensibles sans partir dans du technique a tout va, Adrien
sait de quoi il cause et ça se ressent dans sa tranquillité de nous
montrer le produit! J'ai compris notamment la raison de certain blocage
quand on installe un paquet ayant un "\~" devant son nom, j'ai pigé le
comment on installe une version différente, bref c'est une vidéo qui
mériterait d’être directement dans la documentation de Calculate-fr. Je
vais donc dans les billets qui suivent, faire un tuto ou plutôt tenter
de continuer ce qu'Adrien.d a commencé a faire avec son tuto écrit, car
la vidéo est vraiment top et mérite une version papier.
