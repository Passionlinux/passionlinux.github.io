---
title: "Billet Linuxfr pour opensuse Leap 15 est sortie !"
date: 2018-03-17T16:54:08+01:00
layout: post
---

**En cours d'écriture, je poste ici et je le mettrais à jour pour que vous puissez voir et donnez votre avis si vous ne pouvez voir et participer direcetement sur Linuxfr via votre compte (inscription est obligatoire).**

URL:     https://linuxfr.org/redaction/news/opensuse-leap-15-est-sortie
title:   openSUSE Leap 15 est sortie ! 
Authors: seb95
         Bruno Michel et sogal
date:    2018-03-14T16:47:11+01:00
License: CC by-sa
Tags:    
Score:   0


Les membres du projet openSUSE ont le plaisir de vous annoncer la publication de la dernière version de Leap : openSUSE Leap 15 ! Leap est destiné aux utilisateurs soucieux de stabilité. openSUSE Leap 15, muni du noyau Linux 4.12, est un système d'exploitation sûr, stable et fiable.

Aujourd'hui après plusieurs mois de développement en mode rolling release régulièrement testée par [openQA](https://openqa.opensuse.org/), la nouvelle version de la distribution phare du projet openSUSE s'est figée et prête à être utilisée par tous. openSUSE Leap 15.0 est le successeur annoncé d'openSUSE Leap 42.3 – si si, un effort d'abstraction est nécessaire concernant la numérotation…

## Pendant le développement.


### Le retour des Lives.


Après la sortie des images de Leap 15 Beta en mars, Le développement de la future version d'openSUSE Leap, numérotée 15, s'est poursuit activement et le projet a publié des images vous permettant de les tester, grosse surprise : des versions live GNOME et KDE étaient disponibles pour pouvoir tester encore plus facilement !


### Un nouveau look pour le site.


Le [site de téléchargement](https://software.opensuse.org/) bénéficie également d'un rafraîchissement esthétique avec un thème qui se rapproche du thème par défaut de cette future nouvelle version.


### Divers changements.


Le système de base compte sur le gestionnaire de paquets RPM, qui est mis-à-jour vers la version 4.14, et l'installateur, qui propose @/var comme sous-volume Btrfs.


Visuellement, le plus gros changement est un nouveau thème, conçu par un certain Stasiek alias [LCP](https://lcp.world/), ainsi que le bureau KDE Plasma 5.12 qui est une version au support étendu (LTS).


![theme-plasma5.12](https://www.alionet.org/attachment.php?attachmentid=3982&d=1517344581)


### openSUSE dit adieu à SuSEfirewall2


![firewall](https://www.alionet.org/attachment.php?attachmentid=3989&d=1466361250)


La vénérable et historique interface d'openSUSE à iptables laisse sa place à firewalld, un semblable plus moderne. Mais si les installateurs de Tumbleweed et de Leap 15 activent maintenant (ou activeront bientôt) firewalld par défaut, la transition ne se fait pas automatiquement sur les installations existantes.


#### SuSEfirewall2 vs. firewalld : quelles différences ?


Pas tant de choses que ça dans le principe : ce sont tous les deux des moyens de configurer facilement les fonctions de pare-feu fournies par le noyau Linux. Tous deux créent des règles [iptables](https://fr.wikipedia.org/wiki/Iptables), à partir d'une configuration modifiable via une interface graphique.


![SuSEfirewall2](https://www.alionet.org/attachment.php?attachmentid=3990&d=1425815173)


Firewalld a cependant l'avantage d'offrir une interface [D-Bus,](https://fr.wikipedia.org/wiki/D-Bus) permettant l'interaction avec d'autres applications – par exemple [NetworkManager](https://fr.wikipedia.org/wiki/NetworkManager) – ainsi qu'une vraie interface en ligne de commande.


En outre, il est utilisé – du moins disponible – sur d'autres distributions GNU/Linux, notamment Fedora, alors que SuSEfirewall2 n'était utilisé, à ma connaissance, qu'au sein de la famille SUSE.


Source: https://www.alionet.org/content.php?808-openSUSE-dit-adieu-%E0-SuSEfirewall2


### Autour de la distrisution.



#### [Open Build Service (OBS)](https://build.opensuse.org/)


Notre outil de construction qui crée tous nos paquets ainsi que des paquets pour SUSE Linux Enterprise, Arch, Debian, Fedora, Scientific Linux, RHEL, CentOS, Ubuntu et bien plus encore.


#### [openQA](http://openqa.opensuse.org/)


Outil de test automatisé pour *tout* système d'exploitation, qui est capable de lire un écran et de contrôler la machine de test de la même manière qu'un utilisateur le ferait.


#### [YaST](http://yast.opensuse.org/)


![Yast-logo](http://yast.opensuse.org/assets/images/yast-logo.png)
Le seul et unique outil complet d'installation et de configuration d'un système Linux prédominant depuis 1996. 


YaST est l'outil d'installation et de configuration pour openSUSE et les distributions SUSE Linux Enterprise. Il dispose d'une interface facile à utiliser et de puissantes capacités de configuration. 


**De l'installation à l'optimisation**


YaST est à la fois un installateur extrêmement flexible et un centre de contrôle puissant. C'est un outil polyvalent pour l'informatique. 


![Yast installateur](http://yast.opensuse.org/assets/images/screenshots/screenshot_1.png)


**Configure tout**


YaST inclut des modules pour configurer presque tous les aspects d'un système Linux et fournit un cadre solide pour un développement ultérieur.


![Yast2](http://yast.opensuse.org/assets/images/screenshots/screenshot_2.png)


**Une interface complètes et multilibs**


YaST propose une interface graphique basée sur [libyui](https://en.opensuse.org/SDB:YaST_tricks) c'est à dire, que si vous avez un environnement Qt du layout KDE, vous aurez un Yast en Qt, si vous êtes sur un environnement GTK comme GNOME, Xfce ou Mate, ça sera alors un Yast en GTK. Aussi si vous êtes sans environnement graphique (serveur par exemple), Yast aura une interface [Ncurse](https://fr.wikipedia.org/wiki/Ncurses) basée sur un terminal, parfaite pour l'administration à distance.


![Yast-interface](http://yast.opensuse.org/assets/images/screenshots/screenshot_3.png)


**Installation sans surveillance**


AutoYaST vous permet d'exporter les paramètres de configuration du système et de les installer automatiquement sur des milliers d'autres systèmes.


![Autoyast](http://yast.opensuse.org/assets/images/screenshots/screenshot_5.png) 


#### [Kiwi](http://opensuse.github.io/kiwi/)


Créez des images de systèmes Linux pour du déploiement sur du matériel réel, de la virtualisation ou des systèmes de conteneurs comme Docker. Kiwi est notamment utilisé dans SUSE Studio.



Have fun !

----

[Communauté francophone openSUSE](https://www.alionet.org/)

----

