---
title: Création de paquets DEB (méthode1 dpkg-buildpackage)
date: 2016-06-03 12:18
layout: post
---

<p>
    On va commencer par changer une règle de compilation d’un paquet
déjà présent dans debian :

1/ Je récupère les sources de debian, **apt-get source nom\_du\_paquet**
ou par exemple :

<div>

<div>

`apt-get source mldonkey`{.spip_code dir="ltr"}

</div>

</div>

2/ Je m’occupe donc de mettre une version différente de celle du dépôt
pour pas entrer en conflit avec ceux du dépôt, par exemple si c’est la
version 3.5.1 dans le dépôt, je change le miens en 3.5.1-scha1. Je le
fais avec **dch**, :

<div>

<div>

`dch -v 3.1.5-2.scha1`{.spip_code dir="ltr"}

</div>

</div>

3/  
J’effectue les modification, admettons que je veux seulement changer
un truc dans la compilation, par exemple la prise en charge de tout
les protocoles, faudra aller dans le fichier **rules** du dossier
**/debian**. Le fichier **control** me sers a transcrire les changements
et alleger les **dépendances** (debian aime bien donner des versions a
ses dépendances ce qui est nécessaire car elle a plusieurs versions
(stable, testing, sid))

4/ On télécharge les dépendances du paquet a construire :

<div>

<div>

`# apt-get build-dep mldonkey`{.spip_code dir="ltr"}

</div>

</div>

5/ Ensuite pour construire le paquet on rentre un

<div>

<div>

`dpkg-buildpackage -rfakeroot -us -uc`{.spip_code dir="ltr"}

</div>

</div>

(-us -uc pour ne pas chiffrer avec une clef)

on installe ce que nous demande le terminal( d’ou l’utilité d’un chroot)
ou de ne faire que pour des paquets qu’on utilise...  
et on a un joli paquet.

Dans les prochains posts, enfin j’espére, on parlera de **paquet a
partir de zéro,** ou avec **checkinstall**, et ensuite de **dépôt
privé** mais accessible par internet par exemple pour la famille. J’ai
déjà lu la doc (tres bonne au passage), il manque plus que le courage
pour se lancer.

P.S : toutes les commandes sont a taper en user simple et pas en root !
Sauf si

<div>

> <div>
>
> \#
>
> </div>

</div>

est mis avant la commande

------------------------------------------------------------------------

Changements apporté au fichier rules :

<div>

<div style="background:#eee; border:1px solid #ccc; padding:5px 10px">

  
     —enable-multinet  
     —enable-bittorrent  
     —enable-filetp  
     —enable-gnutella  
     —enable-gnutella2  
  —enable-fasttrack

</div>

</div>

Description supplémentaire apporté au fichier changelog :

<div>

<div>

<div style="background:#eee; border:1px solid #ccc; padding:5px 10px">

mldonkey (3.1.5-2.scha1) UNRELEASED ; urgency=medium

</div>

<div style="background:#eee; border:1px solid #ccc; padding:5px 10px">

 \* Activation des réseaux fasttrack, bittorrent, gnutella1&2, filetp

</div>

<div style="background:#eee; border:1px solid #ccc; padding:5px 10px">

— Sebastien CHA &lt;sebastien@xxxxxxxx.xx.xx&gt; Wed, 15 Apr 2015
14:04:01 +0200

</div>

</div>

</div>

L’adresse a été changé pour ne pas être exploité.

A la suite de quoi nos nouveaux paquets sont disponible comme on peut le
voir par un "ls" :

<div>

<div style="background:#eee; border:1px solid #ccc; padding:5px 10px">

\[ /Public/debian\] :\$ ls  
mldonkey-3.1.5                  mldonkey\_3.1.5-2.scha1.dsc  
mldonkey\_3.1.5-2.debian.tar.xz            mldonkey\_3.1.5.orig.tar.bz2  
mldonkey\_3.1.5-2.dsc             mldonkey-gui\_3.1.5-2.scha1\_amd64.deb  
mldonkey\_3.1.5-2.scha1\_amd64.changes    mldonkey-server\_3.1.5-2.scha1\_amd64.deb  
mldonkey\_3.1.5-2.scha1.debian.tar.xz

</div>

<div>

------------------------------------------------------------------------

Je viens de refaire un autre paquet, pour le moment ce ne sont qu’a
partir des sources de debian, donc le paquet doit être déjà packagé.

<div>

<div>

`apt-get source xfce4-systemload-plugin `{.spip_code dir="ltr"}

</div>

<div>

`apt-get build-dep xfce4-systemload-plugin`{.spip_code dir="ltr"}

</div>

<div>

`exit (on revient dans le terminal utilisateur)`{.spip_code dir="ltr"}

</div>

<div>

`dch -v 1.1.1-4.scha1`{.spip_code dir="ltr"}

</div>

<div>

`dpkg-buildpackage -rfakeroot -us -uc`{.spip_code dir="ltr"}

</div>

</div>

</div>

</div>

<p>
</p>

