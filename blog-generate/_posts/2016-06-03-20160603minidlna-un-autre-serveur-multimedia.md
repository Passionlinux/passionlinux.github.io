---
title: Minidlna, un autre serveur multimedia.
date: 2016-06-03 10:25
layout: post
---

Il y a un peu plus de 1 an maintenant,
j’écrivais [ceci](http://passiongnulinux.tuxfamily.org/?p=85) :  

> Nous avons tous de superbes TV a ecran plat avec des tonnes de
> fonctions integrées et des ordinateurs a recycler. Du coup ce qui va
> suivre va certainement vous interesser ! Qui  
> n’a jamais eu la flemme de se lever pour changer de dvd ? Qui n’a
> jamais  
> dit "il n’y a rien ce soir a la télé" ? Et qui n’a jamais dit a quoi
> bon  
> payer la redevance télé ? Maintenant imaginez un peu ce qui suit(tiré
> de  
> fait réél), vous etes  
> chez vous, vous venez de raccompagner vos amis, il est tard et il n’y
> a  
> rien a la tv mais aucune envie d’aller vous coucher. Vous avez une  
> collection impressionnante de divx(seulement des copies légale de vos
> dvd)sur le pc du 1er etage  
> mais aucune envie d’aller la haut, vous préféré regarder sur votre  
> canapé devant la belle tv led branché a un ordinateur relié au reseau
> par wifi. Et si je vous disais que c’est possible et tres simplement ?
> Mediatomb est le logiciel qui permet de realiser ce reve.
> </p>

Entre temps, les manières de regarder ses fichiers multimédia ont
explosé, de la tv relié a la bulle internet, aux boîtiers multimédia
comme le WD TV, en passant par les téléphones portables... Et Mediatomb
n’a pas eu de nouvelle version depuis des lustres et il est patché a ne
plus savoir quoi faire... Donc j’ai fini par le remplacé par rygel et
puis par minidlna, c’est celui ci qui nous intéresse pour aujourd’hui.
Minidlna n’est pas aussi complet que mediatomb, il ne fait pas de
transcodage par exemple, mais par contre c’est celui qui est le moins
gourmand( un peu plus de 6 mo en fonction contre jusqu’à 300mo pour
rygel et 60mo pour mediatomb... dû en partie au transcodage...) et qui
marche la ou certain ne marche pas, par exemple ushare et rygel (pas
testé avec mediatomb...) n’est pas vu sur xbox360 alors que minidlna
oui. Ce programme n’a pas non plus d’interface web pour le piloter comme
c’est le cas pour mediatomb et ushare ou d’interface graphique comme
pour rygel, mais un simple fichier de conf qui est très simple. Pour
l’installer, c’est simple comme bonjour avec pacman sous arch ou
frugalware :

    pacman-g2 -S minidlna

sous ubuntu ou debian :

    apt-get install minidlna

Enfin sous opensuse, avec le dépôt de packman activé :

    zypper install minidlna

Pour la configuration suffit d’aller sur
[ubuntu](http://doc.ubuntu-fr.org/minidlna), mais en gros on change :
wlan0 pour le wifi ou le nom du reseau comme enp4s0 au lieu de eth0.

    network_interface=eth0

dossier des fichiers.

    media_dir=V,/repertoire/films

le nom qu’on donne au serveur.

    friendly_name=My DLNA Server

le port

    port=49200

et pour le reste c’est pas trop utile...
