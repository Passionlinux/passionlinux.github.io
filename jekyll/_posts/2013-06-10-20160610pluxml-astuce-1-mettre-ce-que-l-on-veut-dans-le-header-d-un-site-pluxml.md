---
title: PluXml Astuce 1, Mettre ce que l'on veut dans le header d'un site PluXml
date: 2013-06-10 23:09
layout: post
---

Pour commencer, c'est la première fois que je touche au
[CSS](/index.php?tag/CSS) de mon site, d'habitude que ça soit
[Dotclear](/index.php?tag/Dotclear) ou [Joomla](/index.php?tag/Joomla)
pour ne citer qu'eux, je laisse le CSS tranquille et je modifie le
[thème](/index.php?tag/thème) avec le sélecteur de thème! Ceci étant
dit, J'ai galéré pour avoir ce que je voulais, déjà un thème qui perd
pas trop sur les cotés, et ensuite mettre ma petite bannière qui me suit
déjà depuis pas mal de temps.

En farfouillant sur la toile et en tapant les mots magiques de *pluxml*
et *theme*, je suis tomber sur [pluxml pour les
nuls](http://tuto-pluxml.reseauk.info/) et sur l'article [tricher avec
le
header](http://tuto-pluxml.reseauk.info/article23/tricher-avec-le-header).
J'ai pu faire à peu près ce que je voulais et tout ça très simplement
grâce à la "*balise miracle"*:

      <?php $plxShow->staticInclude(2) ?>

<div>

<div>

 

</div>

</div>

D'abord, on va créer une [page statique](/index.php?tag/page%20statique)
avec ceux qu'on veut voir apparaître dans le *header*, ça peut être
l'image de la bannière, un code qui donne la météo, etc... Pour moi ça
sera le "*[logo](/index.php?tag/logo)*" de mon
[site](/index.php?tag/site):

<figure style="margin: 0 auto; display: table;">
![banner.png](https://download.tuxfamily.org/passionlinux/site/.banner_m.png){.media}  

<figcaption>
banner.png, oct. 2017

</figcaption>
</figure>
![](http://download.tuxfamily.org/passionlinux/images/firefoxgnulinuxdistribes.png){.transparent}

une fois que c'est fait, on enregistre la page et on lui donne un nom
qui a un rapport avec ce que c'est (pour se souvenir dans six mois de ce
qu'elle fait), "tête d'affiche" ou "*header*" fera l'affaire, et surtout
on la masque dans le menu.

Ensuite, on se rend dans *paramètre d'affichage* pour modifier le
fichier *header.php* de notre thème et on rajoute la balise miracle dans
le *body* juste avant le menu, en remplaçant le (2) par le numéro de
notre page statique (dans mon cas c'est toujours (2)).

Une fois enregistré on peut aller voir ce que ça donne!

Du coup sans toucher vraiment au CSS du thème, on peut avoir ce que l'on
veut sans prises de tête. On peut très bien faire pareil pour fabriquer
une [sidebar](/index.php?tag/sidebar), un
[footer](/index.php?tag/footer), ou ce que l'on veut très simplement.

[Source](http://tuto-pluxml.reseauk.info/article23/tricher-avec-le-header)
