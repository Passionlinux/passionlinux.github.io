---
title: Mldonkey, le client multiplateforme, multiprotocole.
date: 2016-06-03 09:51
layout: post
---

<div class="texte surlignable">

### Mldonkey, qu’est ce que c’est ? {#outil_sommaire_0 .spip}

**MLdonkey** est une application de **Peer-to-peer multi-plateforme,
muti-protocole (multi-réseaux) et open-source**. A l’origine, le projet
était développé sous **Linux**, bien qu’à présent il soit disponible
pour de nombreux systèmes d’exploitations. **MLDonkey** a été écrit en
**Objective Caml**, un langage très puissant développé par l’**INRIA**,
capable de concurrencer le C++, son fondateur est **Fabrice Le Fessant
de l’INRIA.** **Mldonkey** est différent des autres clients p2p mais
ressemble a **GIFT**(Gift s’en inspire) car comme lui c’est un **noyau
P2P**, ce qui signifie qu’il se pilote à la ligne de commande, sans
interface graphique. Quoique cela puisse paraître être un inconvénient à
première vue, une telle architecture ouverte permet une grande souplesse
en faite, permettre à des tiers de mettre en œuvre et de personnaliser
la façon dont le statut affiche MLdonkey et de le tourner vers
l’utilisateur final.  
On peut ensuite l’utiliser via **telnet**, un **navigateur
internet**(opera, firefox, I.E...) et meme plusieur **interface** dont
les plus connues sont **Sancho**, **g2gui**, **mlgui**(interface par
defaut), **kmldonkey**....  
De plus, on peut parfaitement lancer un téléchargement et quitter
l’interface graphique, MLDonkey continue à tourner silencieusement,
utilisant ainsi moins de ressource mémoire.  

### Intéréssant tout ça, mais comment marche t’il ??? {#outil_sommaire_1 .spip}

Comme on a pu le voire, MLdonkey a été conçu pour fonctionner en
**daemon**. (Ce logiciel fonctionne en arrière plan, et n’a pas besoin
d’interface graphique pour fonctionner).  
Avantage : Les ressources mémoire/processeur liées à l’affichage d’une
fenêtre sont minimisés. Il peut également être piloté à distance via
**SSH** sur un serveur hébergé en data-center.  
Le cœur de l’application est donc accessible par plusieurs biais :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Un terminal de layout **telnet** en tapant dans une
console : `$ telnet localhost 4000`{.spip_code dir="ltr"}
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Un navigateur web, disponible à l’adresse
*<http://localhost:4080>*
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Une interface graphique dédiée connu sous le nom
de Gui, interface graphique et de frontend. Ensuite, on peut controler
le daemon MLNET par une interface web(firefox, opera, I.E...), par
telnet, par un frontend ou gui comme la plupart des logiciel P2P (emule,
limewire, shareaza,...), le plus connu des gui est sancho. Voila une
liste non compléte de frontend disponible :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Sancho -:Excellent interfaces multi-plateformes
Java pour mldonkey
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} KMLdonkey - une jolie interface graphique pour
KDE, écrit en C + + Image
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} MLdonkeyGtkUi - L’original mldonkey interface
graphique (fourni avec CVS)
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} G2Gui - Ecrit dans le but de fournir une jolie
interface graphique pour débutants (morts)
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} CocoDonkey - une interface graphique pour Mac OS
X, écrit en Cocoa
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} XDonkey - une autre plus récente interface
graphique pour Mac OS X, écrit en Cocoa
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} MlMac - Nice interface graphique pour Mac OS X,
écrit en Cocoa
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} MLdonkeyWatch - Nice Delphi app pour MS Windows
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} PhpEselGui - Une interface graphique pour
mldonkey écrit en PHP
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Saman - Une autre interface graphique pour
mldonkey écrit en PHP
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Platero - Un mldonkey interface graphique pour
KDE
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Alemula - autre interface mldonkey graphique en
PHP
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Zuul - PHP Front-End pour mldonkey
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} JMoule - Une interface graphique très simple,
écrit en Java,
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Web-GMUI - Une interface graphique web inclus
dans un simple serveur web L’installation de ce logiciel est tout de
même à réserver à un public averti, car l’application n’est fournie
qu’avec ses sources. Cela dit, le paquet est très bien fait, et il n’est
nul besoin de posséder le compilateur Ocaml (il est téléchargé et
compilé automatiquement à la demande lors du processus principal de
compilation). De plus la documentation est complète et très bien faite.
L’installation doit ensuite se faire manuellement.  
On pourra même le compiler avec des option comme *—enable-gui* pour
avoir l’interface graphique mlgui. Sur la plupart des distributions
GNU/Linux, Ubuntu, Debian par exemple ou Mandriva, Opensuse, avec
lesquelles faut rajouter des depots(PLF pour Mandriva, et Packman pour
Opensuse), il faut simplement télécharger les paquets mldonkey-server et
mldonkey-gui.  

### Développement {#outil_sommaire_2 .spip}

MLdonkey est écrit en langage Ocaml. C’est un langage assez peu répandu,
et de ce fait, les évolutions nécessitent de connaitre le langage
utilisé. Cela dit, le logiciel est tout de même régulièrement et
rapidement mis à jour, comme l’a prouvé le groupe de développeurs en
étant les deuxièmes à implémenter le réseau chiffré FastTrack dans la
liste de leurs protocoles supportés. De plus les développements suivent
d’assez près les dernières évolutions des protocoles eDonkey/eMule. Sa
licence est GPL v2.  

### Multiprotocole, multi-plateforme, c’est quoi ? {#outil_sommaire_3 .spip}

**Multi-protocol** car il permet de se connecter à tous les protocoles
majeurs existants. Un seul client, et on télécharge les fichiers via
eDonkey, BitTorrent, Gnutella, Soulseek, FastTrack, et même FTP en
simultané ! Les réseaux supportés sont :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **EDonkey**, la première utilisée par MLdonkey
(Sherlock m’appeler !). Elle pourrait également être appelée eMule,
parce que le client est libre de les amener sur les poignées. Aussi
Overnet et eMule Kademlia (officielle mise en œuvre est encore beta) de
protocoles. C’est le meilleur réseau P2P pour la plupart des objectifs,
avec une large variété et la quantité des sources.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **BitTorrent**, Un protocole très novateur, le
meilleur pour les gros fichiers (1GB +). Vous avez besoin d’un bon
tracker avec beaucoup de clients pour que ça fonctionne bien, cependant.
Ce n’est pas un réseau P2P, vous devez donc trouver les trackers en
utilisant d’autres supports, pour la plupart des sites Web et Gnutella.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **Gnutella** (Formerly LimeWire), déjà ancienne,
a récemment fixé à l’échelle bien, a un gros nombres d’utilisateurs.
Travail, les problèmes de démarrage Gwebcache
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **Gnutella2**, un protocole remanié par les gens
de Shareaza le client. Il essaie de surmonter les problèmes avec le G1,
et probablement le fait, mais a encore un long chemin à parcourir grâce
à la popularité (spécialement avec les autres clients G1 développeurs).
Travail, les problèmes de démarrage Gwebcache.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **DirectConnect** , DC groupes d’utilisateurs
dans les petites communautés, appelées plaques tournantes, en essayant
d’imposer le partage pour tous les utilisateurs. Habituellement, vous
avez besoin d’un nombre minimal de partage GB se connecter, et le privé,
de nouvelles plates-formes de filtrage de ses utilisateurs, en exigeant
l’enregistrement. Donc, même si elles n’ont pas assez variés, vous
pouvez obtenir une bonne performance dans un contexte bien géré moyeu.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **OpenNapster** ? Abandon / Enlevée
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **FastTrack**, le réseau utilisé par Kazaa. Eh
bien, outre Altnet. Faiblesse de hachage permet des inaperçue faux et
corruption. Les changements dans le protocole (\_security\_ mises à
jour), rend difficile pour les clients de substitution de rester
compatible. Formé d’un nombre assez important d’utilisateurs, bien.
C’est le diable, éloignez-vous ! :lol :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **SoulSeek**, serveur centralisé regroupant les
collectivités dédié à la musique des minorités principalement. Abandon /
supprimées - Téléchargement travaille parfois avec « slsk option »
upload off.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **Audiogalaxy**, audiogalaxy est mort, Vive
Audiogalaxy !
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **OpenFT** Nés après le giFT folks, on eu assez
de FastTrack \_security\_ upgrades.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **FileTP** ,met en oeuvre des protocoles de
transfert de fichiers de base, actuellement HTTP, FTP et SSH. Rien de
mieux qu’un téléchargement direct.  

### Fonctionne très bien {#outil_sommaire_4 .spip}

<p>
Multi-plateforme car fonctionne sous divers systeme comme GNU/Linux,
MacOS et Windows, au début, il étais uniquement sous linux d’ou le
Core(daemon) séparé du Gui(frontend) qui est typiquement l’esprit de
Linux.  
Il doit aussi tourner sous différent unix comme les Bsd, les unix de sun
(opensolaris et solaris) et ceux d’IBM.. Voila pour la présentation
c’est finie, bientot une démontration de comment le compiler, astuce et
une configuration.

</div>

Voir en ligne : [Utilisation de
MLdonkey](http://passiongnulinux.tuxfamily.org/?p=79)
