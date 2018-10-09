---
title: Bon, me voici sur Calculate linux #2 choses a faire
date: 2017-01-15 01:35
layout: post
---

J'ai été un peu gourmand et j'avais installé tout et n'importe quoi, je
me dis donc que je vais tout remettre a plat et réinstaller que
l'essentiel puis je verrais sur le coup pour installer ce dont j'ai
besoin.  
<!--more-->  
Donc lancement de l'installation en image, pas trop besoin de commenter
car ça coule de source:
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170113_003644.png){.aligncenter
.size-full .wp-image-1001 width="928" height="753"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170115_011731.png){.aligncenter
.size-large .wp-image-1002 width="525" height="426"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170115_011801.png){.aligncenter
.size-large .wp-image-1003 width="525" height="426"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170115_011919.png){.aligncenter
.size-large .wp-image-1004 width="525" height="503"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170115_012140.png){.aligncenter
.size-large .wp-image-1005 width="525" height="503"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170115_012202.png){.aligncenter
.size-large .wp-image-1006 width="525" height="503"} A noter un petit
bug, ou peut être pas, mais si on ajoute un second utilisateur, le
premier n'a plus de certificat pour ouvrir les outils calculate-console
en graphique, c'est le deuxième utilisateur qui aura les
droits.![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170115_012231.png){.aligncenter
.size-large .wp-image-1007 width="525" height="503"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170115_012255.png){.aligncenter
.size-large .wp-image-1008 width="525" height="503"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170115_012310.png){.aligncenter
.size-large .wp-image-1009 width="525" height="503"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Screenshot_20170115_012334.png){.aligncenter
.size-large .wp-image-1010 width="525" height="503"} J'ai ensuite fait
une mise a jour, j'aurais voulu choper de suite le miroir de notre ami
Adrien.d de Linuxtricks.fr mais malgré ma demande de chercher un miroir
le plus proche et rapide, je suis resté avec celui de Russie. J'ai donc
changé le serveur directement dans le fichier
/var/lib/calculate/calculate.env et j'ai remplacer le serveur russe par
celui de notre ami:

    # nano /var/lib/calculate/calculate.env ... cl_update_binhost = http://miroir.linuxtricks.fr/calculate

J'ai lancé pour la mise a jour un cl-update en root bien sur:

    # cl-update Synchronisation des dépôts  * Synchronisation du dépôt Distros ... [ ok ]  * Synchronisation du dépôt Calculate ... [ ok ]  * Synchronisation du dépôt Gentoo ... [ ok ]  * Synchronisation terminée Configuration système  * Correction des paramètres ... [ ok ]  * Mise à jour des fichiers de configuration ... [ ok ]  * Update server http://mirror.yandex.ru/calculate Vérification de mises à jour  * Calcul des dépendances ...  * Liste des paquets à installer   .... * 35 paquets à installer, 150874 KiB à télécharger Voulez-vous installer ces paquets ? (Yes/No): yes

J'ai coupé volontairement la sortie, mais l’essentiel est là. Ensuite,
j'ai installé un pare feu un peu plus compréhensible pour moi que
shorewall, j'ai nommé UFW et j'en ai profité pour installer mon
minidlna:

    # emerge -avq minidlna ufw [binary N ] net-misc/minidlna-1.1.4 USE="-netgear -readynas" [binary N ] net-firewall/ufw-0.35 USE="ipv6 -examples" PYTHON_TARGETS="python2_7 python3_4" Would you like to merge these packages? [Yes/No] yes >>> Running pre-merge checks for net-firewall/ufw-0.35 --2017-01-13 00:05:12-- http://mirror.yandex.ru/calculate/grp/x86_64/net-firewall/ufw/ufw-0.35-1.xpak Resolving mirror.yandex.ru (mirror.yandex.ru)... 213.180.204.183, 2a02:6b8::183 Connecting to mirror.yandex.ru (mirror.yandex.ru)|213.180.204.183|:80... connected. HTTP request sent, awaiting response... 200 OK Length: 336036 (328K) [application/octet-stream] Saving to: /var/calculate/packages/x86_64/net-firewall/ufw-0.35.tbz2.partial /var/calculate/packages 100%[=============================>] 328.16K 826KB/s in 0.4s 2017-01-13 00:05:13 (826 KB/s) - /var/calculate/packages/x86_64/net-firewall/ufw-0.35.tbz2.partial saved [336036/336036]  * Checking for suitable kernel configuration options... [ ok ] >>> Emerging binary (1 of 2) net-misc/minidlna-1.1.4::gentoo >>> Emerging binary (2 of 2) net-firewall/ufw-0.35::gentoo >>> Installing (2 of 2) net-firewall/ufw-0.35::gentoo >>> Installing (1 of 2) net-misc/minidlna-1.1.4::gentoo >>> Recording net-firewall/ufw in "world" favorites file... >>> Recording net-misc/minidlna in "world" favorites file... >>> Jobs: 2 of 2 complete Load avg: 1.67, 1.79, 1.76  * Messages for package net-firewall/ufw-0.35:  * To enable ufw, add it to boot sequence and activate it:  * -- # rc-update add ufw boot  * -- # /etc/init.d/ufw start  * If you want to keep ufw logs in a separate file, take a look at  * /usr/share/doc/ufw-0.35/logging.  * /usr/share/ufw/check-requirements script is installed.  * It is useful for debugging problems with ufw. However one  * should keep in mind that the script assumes IPv6 is enabled  * on kernel and net-firewall/iptables, and fails when it's not.  * Note: once enabled, ufw blocks also incoming SSH connections by  * default. See README, Remote Management section for more information.  * Messages for package net-misc/minidlna-1.1.4:  * minidlna now runs as minidlna:minidlna (bug 426726),  * logfile is moved to /var/log/minidlna/minidlna.log,  * cache is moved to /var/lib/minidlna.  * Please edit /etc/conf.d/minidlna and file ownerships to suit your needs.

Une fois installé, j'ai ajouté le service UFW au démarrage comme indiqué
plus haut:

    # rc-update add ufw boot  * service ufw added to runlevel boot

Puis j'ai lancé le service:

    # /etc/init.d/ufw start ufw| * Caching service dependencies ... [ ok ] ufw | * Starting ufw ... [ ok

J'ai ajouté une liste de ports a autoriser de cette manière:

    # ufw allow port:port/tcp La règle a été ajoutée La règle a été ajoutée (v6)

Pour autoriser une série de ports en tcp ou autoriser un port en udp et
tcp:

    # ufw allow port

Je recharge le pare feu:

    # ufw reload Pare-feu rechargé

J'ai ensuite configuré minidlna car par défaut il tourne avec
l'utilisateur minidlna et le groupe qui va avec. J'ai aussi [changé sa
configuration de son fichier
principal](http://passiongnulinux.tuxfamily.org/2016/06/03/20160603minidlna-le-serveur-multimedia/),
puis je l'ai lancé et ajouté a la liste des service a démarrer au boot
de la machine:

    # /etc/init.d/minidlna restart minidlna | * Caching service dependencies ... [ ok ] minidlna | * Stopping MiniDLNA ... [ ok ] minidlna | * Starting MiniDLNA ... [ ok ] # rc-update add minidlna  * service minidlna added to runlevel default

Enfin j'ai ajouté une petite liste de paquets a installer, ce n'est pas
la totalité de mes besoins mais c'est déjà une bonne partie, du moins
c'est l'essentiel de mes besoins:

    # emerge -avq porthole kdegames-meta amule filezilla thunderbird vivaldi net-p2p/mldonkey 0ad minetest scummvm scummvm-tools wine dgen-sdl nestopia fceux stella hp

Ce qui fait 106 paquets tout de même... Commencé a 00h21 et fini a 1h05
donc 44 minutes pour ce faire. Je reste a dire que mon openSUSE ou ma
Debian me l'aurait fait en 5 minutes mais au moins une fois installé ça
ne bougera plus et je profite de la flexibilité de emerge. Voila, on a
vue une installation et une pots-installation dans mon cas, je vous dis
a bientôt pour de nouvelles aventures sous Calculate.
