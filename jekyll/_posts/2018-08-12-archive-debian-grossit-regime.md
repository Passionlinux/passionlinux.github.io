---
title: "Debian Grossit Regime"
date: 2017-12-02T20:04:28+01:00
layout: post
---
Ma debian grossit, vite au régime.
<div class="chapo surlignable">

Aujourdhui, je vais parler de ce qui arrive quand on utilise une debian
 sid ou simplement une stable upgrader de version en 
version(4-&gt;5-&gt;6-&gt;7-&gt;8-&gt;...), au fil des mises a jour ou 
des installations de programmes, celle-ci prend du poids. Cest moins 
vrai si on part dune stable propre cest a dire dune installation 
fraîche a chaque release.

</div>
<div class="texte surlignable">
<div id="outil_sommaire" class="cs_sommaire cs_sommaire_avec_fond">
<div class="cs_sommaire_inner">

</div>
</div>
Ce qui se passe, cest simple, les paquets téléchargés sont gardé dans 
le cache de apt, pour être en cas de réinstallation des paquets, être 
installé plus rapidement et au passage, économiser de la bande passante 
aux dépôts, a condition de ne pas avoir une version plus récente dans 
les dépôts&nbsp;; ou simplement revenir a une version plus vieille, utile 
sous sid. Cette base peut devenir vraiment très grosse sur une sid Sous
 debian, il y a deux layouts de cache, le cache des paquets viables, 
encore présent dans les dépôts (même version) et celui des paquets 
obsolètes qui sont dans une version plus récente dans les dépôts 
notamment les paquets qui ont eu des mises a jour. Sur ma stable javais
 4.6go de cache, 2.4go de cache des versions obsolètes et 2.2go de 
paquets pressent dans la même version dans les dépôts

Ce qui suit vient de la documentation de <a class="spip_out" href="https://debian-facile.org/doc:systeme:apt:apt-get" rel="external">debian-facile</a>.

</div>

<div class="texte surlignable"><h3 id="outil_sommaire_0" class="spip">Nettoyer le cache</h3>
Les paquets téléchargés avant installation sont stockés dans 
/var/cache/apt/archives. Ils y restent ad vitam aeternam. Ce dossier 
peut donc rapidement devenir encombrant et faire plusieurs Giga-octets. 
Utilisez <a class="spip_out" href="https://debian-facile.org/doc:systeme:du" rel="external">la commande du</a> dans un terminal en simple utilisateur ainsi&nbsp;:<br class="autobr"> <code class="spip_code" dir="ltr">$ du -h /var/cache/apt/archives</code>

Ce qui donne chez moi&nbsp;:
<pre dir="ltr">$ du -h /var/cache/apt/archives
2,4K   /var/cache/apt/archives/partial 
2,2G   /var/cache/apt/archives</pre>
Donc 4.6go pour une debian stable installé fraîchement en Avril 2016 
dans sa version 8.4,ça fait beaucoup, imaginez un peu sous sid
<h3 id="outil_sommaire_1" class="spip">Faire un petit nettoyage</h3>
La commande ci-dessous, a faire en root, va supprimer uniquement les 
paquets dont le numéro de version est obsolète par rapport à ceux des 
miroirs (les vieux trucs quoi)<br class="autobr"> <code class="spip_code" dir="ltr"># apt-get autoclean</code>
<h3 id="outil_sommaire_2" class="spip">Faire le ménage de printemps</h3>
<strong>clean</strong><br class="autobr"> La suivante videra entièrement le contenu du cache.<br class="autobr"> <code class="spip_code" dir="ltr"># apt-get clean</code>

<strong>purge autoremove</strong><br class="autobr"> Et depuis lenny, il sest ajouté loption <strong>purge autoremove</strong> qui supprime les paquets installés automatiquement mais devenus inutiles&nbsp;:<br class="autobr"> <code class="spip_code" dir="ltr"># &nbsp;apt-get --purge autoremove</code>

</div>
<p class="hyperlien">Voir en ligne : <a class="spip_out" href="https://debian-facile.org/doc:systeme:apt:apt-get">apt-get</a></p>
