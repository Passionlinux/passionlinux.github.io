---
title: IMG de SPIP m'embete un peu, beaucoup, a la folie....
date: 2016-08-09 22:03
layout: post
---

Hier, je n'ai pas fait de billet, simplement pas eu le temps d'en faire
, trop occupé a essayer de trouver une solution a mon problème de SPIP.
J’étale mon soucis, je suis hébergé par Tuxfamily,  ils sont vraiment
très bien et ne demande rien en échange sauf une mention indiquant que
c'est eux qui hébergent le site, bref rien de méchant vu la qualité du
service. Le service inclus un espace pour le site de 200mo, et un espace
de téléchargement de 1go, qui servira aux documents du site, c'est a
dire les images, sons, vidéos et autres documents du site seront stocké
sur cette espace. Le soucis est que SPIP, en bon élève qu'il est,
importe toute image non stocké chez lui dans /IMG/format-image(png,
jpeg, gif,...) dans un dossier /IMG/distant/format-image, du coup mes
images que je stocke sur l'espace téléchargement d'1go, sont aussi
rapatrié sur l'espace du site de 200mo, ce qui me bouffe très vite ce
petit espace.  
<!--more-->  
J'ai commencé a dire que [SPIP me
manquait](http://passiongnulinux.tuxfamily.org/2016/08/07/mon-spip-me-manque-2/)
de plus en plus, faut me comprendre, lui et moi c'est une longue
histoire, lui et Dotclear ont été mes premiers CMS et ce sont sur eux
que j'ai fais mes armes. Hier, j'ai donc chercher un moyen de
contrecarré ce problème, en cherchant je suis  tombé sur des pages
intéressantes qui m'expliquent comment faire avec
[Dotclear](https://faq.tuxfamily.org/WebArea/Compat/Dotclear2/Fr) et
[Wordpress](https://faq.tuxfamily.org/WebArea/Compat/Wordpress/Fr),
chose que je dirais dans deux billets qui suivent celui-ci de prés, mais
rien pour SPIP. J'ai fouillé les forums de SPIP ou le problème revient
souvent, mais pareil les réponses sont ambiguë, un coup il faut changer
une option dans un fichier, une autre est de faire des liens symbolique
du dossier /IMG vers l'espace de stockage. La première solution me donne
rien, la seconde me donna un peu d'espoir mais pour un court moment, en
effet apres avoir fait des liens pointant vers l'espace de 1go via SSH,
SPIP m'a dit qu'il y avait des erreurs et en effet, je ne pouvais pas
par ftp aller dans les dossiers liées. Je pense quand même être sur la
bonne voie, mais je vais exposer mon soucis sur la liste, sur IRC et en
dernier recours sur le forum. Comme vous pouvez le voir je n'abandonne
pas mon projet de revenir a du SPIP.  
