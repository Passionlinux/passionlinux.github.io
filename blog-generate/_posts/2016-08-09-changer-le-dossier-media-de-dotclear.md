---
title: Changer le dossier media de Dotclear
date: 2016-08-09 22:44
layout: post
---

Avec le [précédent
billet](http://passiongnulinux.tuxfamily.org/2016/08/09/img-de-spip-membete-un-peu-beaucoup-a-la-folie/)
je vous disais a quel point je galère avec mon bon vieux SPIP:  

> Hier, je n'ai pas fait de billet, simplement pas eu le temps d'en
> faire , trop occupé a essayer de trouver une solution a mon problème
> de SPIP. J’étale mon soucis, je suis hébergé par Tuxfamily,  ils sont
> vraiment très bien et ne demande rien en échange sauf une mention
> indiquant que c'est eux qui hébergent le site, bref rien de méchant vu
> la qualité du service. Le service inclus un espace pour le site de
> 200mo, et un espace de téléchargement de 1go, qui servira aux
> documents du site, c'est a dire les images, sons, vidéos et autres
> documents du site seront stocké sur cette espace. Le soucis est que
> SPIP, en bon élève qu'il est, importe toute image non stocké chez lui
> dans /IMG/format-image(png, jpeg, gif,...) dans un dossier
> /IMG/distant/format-image, du coup mes images que je stocke sur
> l'espace téléchargement d'1go, sont aussi rapatrié sur l'espace du
> site de 200mo, ce qui me bouffe très vite ce petit espace.
> </p>

<!--more-->  
Donc en farfouillant, je suis tombé sur [cette
page](https://faq.tuxfamily.org/WebArea/Fr#Copier_des_fichiers_vers_les_espaces_de_t.C3.A9l.C3.A9chargements)
qui parle de ce qui m’intéresse, changer le dossier des documents ou
médias du CMS pour celui prévu par Tuxfamily. Sur cette page, en bas, je
vois Dotclear et Wordpress, bref passons a celui qui nous intéresse pour
ce billet:
[Dotclear](https://faq.tuxfamily.org/WebArea/Compat/Dotclear2/Fr). Sous
celui-ci c'est tres simple de le faire, il suffit d'aller dans
`about:config `de votre interface d'administration Dotclear. Les
réglages intéressants sont :
![dotclearurlmedia](http://download.tuxfamily.org/passionlinux//dotclearurlmedia-1024x549.png){.aligncenter
.wp-image-632 .size-large width="840" height="450"}

<ul>
-   **public\_path**

</ul>
cette variable indique le chemin pour accéder au répertoire sur le
serveur. Pour utiliser votre espace de téléchargement, il faut indiquer
le chemin `/data/repository/mon_projet/`.

<ul>
-   **public\_url **

</ul>
cette variable indique l'URL publique sous laquelle le répertoire
précédent est accessible. Pour un espace de téléchargement, il s'agit de
`http://download.tuxfamily.org/mon_projet/` Et c'est tout, comment
pourrais-je dire ça autrement, Dotclear est très complet et simple
d'utilisation, et comme on pourra le voir dans le prochain billet sur
Wordpress, celui-ci est bien plus compliqué dans certaine action
pourtant simple et fréquente a faire.  
