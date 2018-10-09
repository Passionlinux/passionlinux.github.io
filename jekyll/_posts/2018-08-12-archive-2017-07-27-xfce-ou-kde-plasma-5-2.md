---
title: "Xfce ou KDE Plasma5? 2"
date: 2017-07-27T19:54:49+01:00
layout: post
---
Dans le billet précédent, je parlais de mes petits soucis graphiques
avec Plasma, alors j'ai trouvé le responsable de mes déboires et je met
ici ce qui m'a rendu mon Plasma incassable. En faite par défaut dans
Debian et sûrement chez les autres, Plasma arrive avec les effets de
bureau activés et paramétrés pour utiliser la méthode mise à l'échelle
précise or cette méthode n'est pas prise en charge par tous les
matériels et peut provoquer des dégradations de performances et des
artefacts de rendu.
![](http://download.tuxfamily.org/passionlinux//2017/07/Screenshot_20170726_194541-1024x553.png){.aligncenter
.size-large .wp-image-1420 width="525" height="284"} Pour changer, il
faut se rendre dans *"configuration du système"* puis descendre dans la
rubrique *"matériel"* et aller sur *"affichage et écran"*, dedans on va
sur *"compositeur"* et on choisi une méthode autre que **"précise"**,
dans mon cas j'ai pris "direct". Voila, depuis plus aucuns soucis
d'artefacts ou de bureau qui s'affichait pas.
