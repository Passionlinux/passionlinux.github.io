---
title: Changer le dossier media de Wordpress
date: 2016-08-09 23:06
layout: post
---

Après la [défaite sur
SPIP](http://passiongnulinux.tuxfamily.org/2016/08/09/img-de-spip-membete-un-peu-beaucoup-a-la-folie/),
la facilité de le faire [avec
Dotclear](http://passiongnulinux.tuxfamily.org/2016/08/09/changer-le-dossier-media-de-dotclear/),
voila le tour de Wordpress. Je vous met en garde de suite, ce qui peut
paraître simple va vite devenir moins simple avec Wordpress. Tout
d'abord on se rend sur [cette
page](https://faq.tuxfamily.org/WebArea/Compat/Wordpress/Fr).  
<!--more-->  
A partir de WordPress 3.5, [les options ont disparues de la
page](https://codex.wordpress.org/Settings_Media_Screen#Changelog){.external
.text}. Cependant, il est possible avec quelques efforts non seulement
de s'en passer, mais aussi de les faire réapparaître. Pour se faire, il
va falloir modifier la base de données à la main. Connectez-vous à votre
base de données WordPress (par exemple via PphMyAdmin, voir
[DbMySQL/Fr](https://faq.tuxfamily.org/DbMySQL/Fr "DbMySQL/Fr")), et
sélectionnez la table *wp\_options*. Trouvez les champs *upload\_path*
(ID 50 sur mon installation fraîche) et *upload\_url\_path* (ID 57 sur
mon installation), qui correspondent respectivement au chemin local et à
l'URL décrits plus haut.
![wordpressphpmyamdin](http://download.tuxfamily.org/passionlinux//wordpressphpmyamdin-1024x300.png){.aligncenter
.wp-image-635 .size-large width="840" height="246"} Remplissez ces
champs avec les valeurs appropriées comme expliqué plus haut. Une fois
les champs remplis, les deux options appariassent et dans la page de
configuration *Settings ? Media* et fonctionnent comme dans les
anciennes versions.
![wordpressmediaoption1](http://download.tuxfamily.org/passionlinux//wordpressmediaoption1-1024x435.png){.aligncenter
.wp-image-636 .size-large width="840" height="357"} Et c'est enfin fini!
Voila qui me permet de gérer mes medias par Wordpress tout en utilisant
l'espace d'1go mis a ma disposition par Tuxfamily. Prochaine étape, être
en mesure d'arriver a la même chose avec SPIP.
