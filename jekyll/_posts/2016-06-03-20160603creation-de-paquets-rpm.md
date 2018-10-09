---
title: Création de paquets RPM
date: 2016-06-03 12:16
layout: post
---

<div>

Je me suis lancé dans le rpm, bon quelle simplicité par rapport aux
DEB ! On commence par faire un répertoire rpm ou rpmbuild comme on veut,
avec des sous dossiers, pour cela on va faire la commande suivante :
`$ mkdir -p ~/rpmbuild/{BUILD,RPMS/{i586,noarch,x86_64},SOURCES,SRPMS,SPECS}`{.spip_code
dir="ltr"} Puis on installe les paquets nécessaires :
<div>

`urpmi rpm-build rpm-sign`{.spip_code dir="ltr"}

</div>

Bon pour faire un simple rétro-portage il suffit de télécharger le
rpm.source du paquet désiré :

<div>

<div>

`$ wget http://mirror.internode.on.net/pub/mageia/distrib/cauldron/SRPMS/core/release/pbzip2-1.1.8-3.mga3.src.rpm`{.spip_code
dir="ltr"}

</div>

</div>

Ensuite, la deuxième étape consiste à télécharger les build-requires,
c’est à dire les paquets nécessaires au bon fonctionnement de la future
application à packager :

<div>

<div>

<span
class="marker">`# urpmi --buildrequires pbzip2-1.1.8-3.mga3.src.rpm`{.spip_code
dir="ltr"}</span>

</div>

</div>

Dernière étape, on build notre paquet :

<div>

<div>

`$ rpmbuild --rebuild pbzip2-1.1.8-3.mga3.src.rpm`{.spip_code dir="ltr"}

</div>

</div>

on aura un joli rpm !!!  
<!--more-->  
Si maintenant on veut mettre a jour un paquet présent dans le dépôt mais
pas dans sa dernière version c’est presque pareil : Dans un premier
temps, on télécharges le rpm source :

<div>

<div>

`$ wget http://mirror.internode.on.net/pub/mageia/distrib/2/SRPMS/core/release/playonlinux-4.0.15-2.mga2.src.rpm`{.spip_code
dir="ltr"}

</div>

</div>

Ensuite, la deuxième étape consiste à télécharger les build-requires,
c’est à dire les paquets nécessaires au bon fonctionnement de la future
application à packager :

<div>

<div>

<span
class="marker">`# urpmi --buildrequires playonlinux-4.0.15-2.mga2.src.rpm`{.spip_code
dir="ltr"}</span>

</div>

</div>

On extrait ensuite notre paquet source :

<div>

<div>

`$ rpm -ivh playonlinux-4.0.15-2.mga2.src.rpm`{.spip_code dir="ltr"}

</div>

</div>

Après cette opération, les fichiers sources se situent dans
*\$HOME/rpmbuild/SOURCES* et le fichier SPEC dans
*\$HOME/rpmbuild/SPECS/*, les fameux dossiers qu’on a fait plus haut
![big\_smile](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L15xH15/big_smilepngff3e-adb86.png?1464956098){width="15"
height="15"} Nous téléchargeons le nouveau .tar.gz dans le dossier
SOURCES :

<div>

<div>

`$ cd $HOME/rpmbuild/SOURCES &amp;&amp; wget http://www.playonlinux.com/script_files/PlayOnLinux/4.1.9/PlayOnLinux_4.1.9.tar.gz`{.spip_code
dir="ltr"}

</div>

</div>

Ensuite, on édite le fichier SPEC :

<div>

<div>

`$ nano $HOME/rpmbuild/SPECS/playonlinux.spec`{.spip_code dir="ltr"}

</div>

</div>

On change le numéro de version avec celle du paquet nouvellement
téléchargée :

<div>

<div>

`Version: 4.1.9`{.spip_code dir="ltr"}

</div>

</div>

Aussi, si l’on souhaite modifier le changelog en dessous en respectant
la mise en forme :

<div>

<div>

`* Mon Jul 22 2014 pseudo &lt;pseudo&gt; 4.1.9-1.mga4<br>+ Revision:<br>- New 4.1.9 version`{.spip_code
dir="ltr"}

</div>

</div>

On enregistre les modifications. On lance la création du RPM et SRPM
dans la console :

<div>

    $ rpmbuild -ba $HOME/rpmbuild/SPECS/playonlinux.spec

</div>

<div>

ou si on veut signer son paquet :
    $ rpmbuild -ba -sign $HOME/rpmbuild/SPECS/playonlinux.spec

</div>

Le RPM sera crée selon l’architecture du système :

<div>

<div>

*/rpmbuild/RPMS/x86\_64/*

</div>

</div>

ou

<div>

<div>

*/rpmbuild/RPMS/i586/*

</div>

</div>

Et la source :

<div>

<div>

*/rpmbuild/SRPMS/*

</div>

</div>

<p>
Il ne sera pas possible de créer le RPM pour l’autre architecture, sauf
depuis une machine virtuelle ou un autre ordinateur. Vous ne reste qu’à
installer et partager ! Tout a été fait grace a ce tuto :
[http://www.mageialinux-online.org/wiki/ …
vec-mageia](http://www.mageialinux-online.org/wiki/compiler-ses-propres-paquets-rpm-avec-mageia)
Sauf que j’ai fait ça avec les paquet mldonkey pour le rétroportage(en
faite simplement changer certaines options de compilation.) Et  
pour la seconde, c’est a dire mettre à jour le paquet déjà présent dans  
les dépôts mais dans une version obsolète, c’est avec playonlinux 4.2.6
-&gt; 4.2.7 C’est fait sous Mageia rc5, mais c’est valable sur n’importe
quelle distributions RPM, en adaptant bien sur, les outils, comme
l’utilisation de *yum* ou *zypper* a la place de *urpmi*,... Tres
simple ;) et maintenant j’essaye de faire pareil sous debian avec les
paquets debian ;)

</div>
