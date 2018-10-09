---
title: Ma debian grossit, vite au régime.
date: 2016-06-03 12:44
layout: post
---

<div style="text-align: center;">

![](http://download.tuxfamily.org/passionlinux/IMG/png/10png-a2d700a2d7.png){.transparent}

</div>

<div style="text-align: left;">

<div class="chapo surlignable">

Aujourd’hui, je vais parler de ce qui arrive quand on utilise une debian
sid ou simplement une stable upgrader de version en
version(4-&gt;5-&gt;6-&gt;7-&gt;8-&gt;...), au fil des mises a jour ou
des installations de programmes, celle-ci prend du poids. C’est moins
vrai si on part d’une stable propre c’est a dire d’une installation
fraîche a chaque release.

</div>

<div class="texte surlignable">

<div id="outil_sommaire" class="cs_sommaire cs_sommaire_avec_fond">

<div class="cs_sommaire_inner">

<div class="cs_sommaire_titre_avec_fond cs_done">

</div>

</div>

</div>

Ce qui se passe, c’est simple, les paquets téléchargés sont gardé dans
le cache de apt, pour être en cas de réinstallation des paquets, être
installé plus rapidement et au passage, économiser de la bande passante
aux dépôts, a condition de ne pas avoir une version plus récente dans
les dépôts ; ou simplement revenir a une version plus vieille, utile
sous sid. Cette base peut devenir vraiment très grosse sur une sid… Sous
debian, il y a deux layouts de cache, le cache des paquets viables, encore
présent dans les dépôts (même version) et celui des paquets obsolètes
qui sont dans une version plus récente dans les dépôts notamment les
paquets qui ont eu des mises a jour. Sur ma stable j’avais 4.6go de
cache, 2.4go de cache des versions obsolètes et 2.2go de paquets
pressent dans la même version dans les dépôts Ce qui suit vient de la
documentation de
[debian-facile](https://debian-facile.org/doc:systeme:apt:apt-get){.spip_out}.  
<!--more-->

### Nettoyer le cache {#outil_sommaire_0 .spip}

Les paquets téléchargés avant installation sont stockés dans
/var/cache/apt/archives. Ils y restent ad vitam aeternam. Ce dossier
peut donc rapidement devenir encombrant et faire plusieurs Giga-octets.
Utilisez [la commande
du](https://debian-facile.org/doc:systeme:du){.spip_out} dans un
terminal en simple utilisateur ainsi :  
`$ du -h /var/cache/apt/archives`{.spip_code dir="ltr"} Ce qui donne
chez moi :

``` {dir="ltr"}
$ du -h /var/cache/apt/archives 2,4K   /var/cache/apt/archives/partial 2,2G   /var/cache/apt/archives
```

Donc 4.6go pour une debian stable installé fraîchement en Avril 2016
dans sa version 8.4,ça fait beaucoup, imaginez un peu sous sid…  

### Faire un petit nettoyage {#outil_sommaire_1 .spip}

La commande ci-dessous, a faire en root, va supprimer uniquement les
paquets dont le numéro de version est obsolète par rapport à ceux des
miroirs (les vieux trucs quoi)  
`# apt-get autoclean`{.spip_code dir="ltr"}  

### Faire le ménage de printemps {#outil_sommaire_2 .spip}

<p>
**clean**  
La suivante videra entièrement le contenu du cache.  
`# apt-get clean`{.spip_code dir="ltr"} **—purge autoremove**  
Et depuis lenny, il s’est ajouté l’option **—purge autoremove** qui
supprime les paquets installés automatiquement mais devenus inutiles :  
`#  apt-get --purge autoremove`{.spip_code dir="ltr"}

</div>

Voir en ligne :
[apt-get](https://debian-facile.org/doc:systeme:apt:apt-get){.spip_out}

</div>
