---
title: Frugalware une rolling release ? Passer en current
date: 2014-11-16 20:14
layout: post
---

<div class="main">

<div class="texte surlignable">

Je vais encore une fois parler de frugalware, cette fois c'est pour
faire taire certaines mauvaises langues qui disent à tord et à travers
que fw n'est pas une rolling. Donc, il y a deux dépôts seulement, un
dépôt stable et un current, c'est celui ci qui nous intéresse pour ce
soir. Current est celle de développement mais c'est surtout et avant
tout celle utilisé par tous ceux qui sont sur fw. C'est pas comme debian
avec sa sid, on est plus dans l'esprit d'arch et sa current. Et pour les
grosses mises a jour qui peuvent tout casser c'est dans des dépôts
personnels que ça se passe ou dans un des nombreux dépôts testing. Donc
frugalware est intéressante que si on passe en version current, voyons
ensemble comment faire. Une grosse partie voir la totalité viens du
[wiki de
fw](https://wiki.frugalware.org/index.php/Passer_de_stable_en_current).  
Passer de "stable" à "current"
------------------------------

Vous venez d'installer Frugalware en version stable et vous désirez
passer en current afin d'avoir les paquets les plus récents : la
dernière version de firefox, de thunderbird, des drivers, du
kernel…etc... Rien de ne plus simple, il vous suffit en root d'éditer le
fichier /etc/pacman-g2.conf de cette façon :

<div
style="background-color: #ffe9e9; border: 1px solid #cccccc; padding: 4px 6px; background-position: initial initial; background-repeat: initial initial;">

<div>

**\# nano /etc/pacman-g2.conf**

</div>

</div>

Puis dans le fichier commentez la ligne des paquets stable et
décommentez celle des paquets current, voilà à quoi doit ressembler
cette partie dans votre fichier :

     # -current  Include = /etc/pacman.d/frugalware-current

\# -stable  
\#Include = /etc/pacman.d/frugalware Sauvegarder votre fichier. Voilà
vous êtes en
current ! ![:-D](http://passiongnulinux.tuxfamily.org/plugins/auto/couteau_suisse/v1.9.10/img/smileys/mort_de_rire.png ":-D"){.no_image_filtrer
.format_png width="19" height="19"} Bon maintenant on force la mise a
jour des depots :

    pacman-g2 -Syy

puis on fait les mises a jour :

    pacman-g2 -Syu

Simple non?

</div>

</div>
