---
title: MLDonkey, le serveur P2P.
date: 2016-06-03 10:26
layout: post
---

<p>
**MLDonkey** est un
client [P2P](http://doc.ubuntu-fr.org/p2p "p2p"){.wikilink1} multiplate-forme,
pour les
réseaux [eDonkey](http://fr.wikipedia.org/wiki/EDonkey2000 "http://fr.wikipedia.org/wiki/EDonkey2000"){.interwiki
.iw_wpfr}, [BitTorrent](http://fr.wikipedia.org/wiki/BitTorrent_%28protocole%29 "http://fr.wikipedia.org/wiki/BitTorrent_(protocole)"){.interwiki
.iw_wpfr} mais
aussi [FTP](http://doc.ubuntu-fr.org/ftp "ftp"){.wikilink1},
les [téléchargement
direct](http://fr.wikipedia.org/wiki/Direct_download "http://fr.wikipedia.org/wiki/Direct_download"){.interwiki
.iw_wpfr} et bien d’autres encore.  

MLDonkey est écrit en
langage [OCaml](http://fr.wikipedia.org/wiki/OCaml "OCaml"). C’est un
langage assez peu répandu, et de ce fait, les évolutions nécessitent de
connaitre  
le langage utilisé. Cela dit, le logiciel est tout de même  
régulièrement et rapidement mis à jour, comme l’a prouvé le groupe de
développeurs en étant les deuxièmes à implémenter le réseau
chiffré [FastTrack](http://fr.wikipedia.org/wiki/FastTrack "FastTrack") dans  
la liste de leurs protocoles supportés. De plus les développements  
suivent d’assez près les dernières évolutions des
protocoles [eDonkey](http://fr.wikipedia.org/wiki/EDonkey "EDonkey"){.mw-redirect}/[eMule](http://fr.wikipedia.org/wiki/EMule "EMule").

Le fondateur de MLDonkey est Fabrice Le Fessant de
l’[INRIA](http://fr.wikipedia.org/wiki/Institut_national_de_recherche_en_informatique_et_en_automatique "Institut national de recherche en informatique et en automatique").  

Par rapport aux clients classiques
de [Peer-to-peer](http://fr.wikipedia.org/wiki/Peer-to-peer "Peer-to-peer"){.mw-redirect},
MLDonkey a été conçu pour fonctionner
en [daemon](http://fr.wikipedia.org/wiki/Daemon_%28informatique%29 "Daemon (informatique)"),  
ce qui signifie que le logiciel fonctionne en arrière plan, et n’a pas  
besoin d’interface graphique pour fonctionner. Ce mode de
fonctionnement  
a comme avantage d’économiser les ressources mémoire/processeur liées à
l’affichage d’une fenêtre. MLDonkey est idéal à placer sur un serveur
commandé à distance.  

Le cœur de l’application est donc accessible par plusieurs biais :

-   Un terminal de
    layout [telnet](http://fr.wikipedia.org/wiki/Telnet "Telnet") ;
-   Un [navigateur
    web](http://fr.wikipedia.org/wiki/Navigateur_web "Navigateur web") ;
-   Une interface graphique dédiée (voir ci-dessous).

Installation :
--------------

Comme d’habitude sur notre debian, un petit

    apt-get install mldonkey-server

suffira pour installer le « core » ou « serveur ». Lors de
l’installation une question vous sera posée : **Faut-il lancer MLDonkey
au démarrage du système ?**

Si vous découvrez MLDonkey,  
il est préférable de laisser décocher l’option. Vous pourrez l’activer  
plus tard lorsque vous aurez connaissances des différentes manière de  
l’utiliser.

Si on veut ajouter l’interface qui va avec(qui n’est pas la
meilleur...), on fera :

    apt-get install mldonkey-gui

Sous Frugalware :

`pacman-g2 -S mldonkey-server`{.spip_code dir="ltr"}

Et sous 0linux, un simple :

`0g mldonkey`{.spip_code dir="ltr"}

Vous installera l’ensemble:p

Et c’est tout ! 

Utilisation :
-------------

Nous venons d’installer MLDonkey. Vous ne trouverez pas d’entrée dans le
menu applications concernant MLDonkey puisque c’est
un [démon](http://fr.wikipedia.org/wiki/Disk_and_execution_monitor "http://fr.wikipedia.org/wiki/Disk_and_execution_monitor"){.interwiki
.iw_wpfr}. Ensuite vous utiliserez un client graphique qui permettra de
contrôler ce démon.

Pour démarrer l’application, on tape dans un terminal :

    mlnet

Mais pour être tranquille, je le rajoute aux application a démarrer
automatiquement dans gnome, kde, xfce.

On pourra utiliser une meilleur interface que celle d’origine en
téléchargeant [sancho](http://sancho.awardspace.com/).

<p>
</p>

