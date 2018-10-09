---
title: Les rétroportages (dépôt « backports »)
date: 2016-06-03 12:25
layout: post
---

<div class="texte surlignable">

    Le dépôt ***backports*** propose des paquets plus récents ou absents
du dépôt principal. Ces paquets sont dérivés de la version de test et
peuvent être installé sur une <span class="scayt-misspell-word"
data-scayt-lang="fr_FR" data-scayt-word="Debian">Debian</span> stable.
Il servira à ceux qui ont absolument besoin d’une version plus récente
d’un logiciel, mais ne veulent pas compromettre la stabilité générale de
leur système en migrant vers <span class="scayt-misspell-word"
data-scayt-lang="fr_FR" data-scayt-word="testing">testing</span>. Le
<span class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="priincipe">principe</span> est que ces paquets sont
compilés sous <span class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="jessie">jessie</span>, cela évite de ramener des
bibliothèques de <span class="scayt-misspell-word"
data-scayt-lang="fr_FR" data-scayt-word="testing">testing</span> pour
les installer ce qui fait le gain dans la stabilité plutôt que de les
prendre directement dans <span class="scayt-misspell-word"
data-scayt-lang="fr_FR" data-scayt-word="testing">testing</span>.  
<!--more-->  
Si vous avez besoin d’installer un paquet depuis le dépôt <span
class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="backports">backports</span> de la branche <span
class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="jessie">jessie</span>, **ajoutez** le dépôt suivant à
votre fichier sources.list :
[/etc/apt/sources.list](https://debian-facile.org/_export/code/doc:systeme:apt:sources.list?codeblock=9 "Télécharger un extrait"){.mediafile
.mf_list}
    # Debian Jessie, dépôt principal deb http://httpredir.debian.org/debian/ jessie main # Debian Jessie, mises-à-jour de sécurité deb http://security.debian.org/ jessie/updates main # Debian Jessie, mises-à-jour "volatiles" deb http://httpredir.debian.org/debian/ jessie-updates main # Debian Jessie, dépôt de rétroportages ("backports") deb http://httpredir.debian.org/debian jessie-backports main

Pour ceux qui utilisent un sources.list non libre:
[/etc/apt/sources.list](https://debian-facile.org/_export/code/doc:systeme:apt:sources.list?codeblock=10 "Télécharger un extrait"){.mediafile
.mf_list}

    # Debian Jessie, dépôt principal + paquets non libres deb http://httpredir.debian.org/debian/ jessie main contrib non-free # Debian Jessie, mises-à-jour de sécurité + paquets non libres deb http://security.debian.org/ jessie/updates main contrib non-free # Debian Jessie, mises-à-jour "volatiles" + paquets non libres deb http://httpredir.debian.org/debian/ jessie-updates main contrib non-free # Debian Jessie, dépôt de rétroportages ("backports") deb http://httpredir.debian.org/debian jessie-backports main contrib non-free

Pour installer un paquet depuis le dépôt <span
class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="backports">backports</span>, il faut le spécifier
explicitement. Exemple: pour installer la dernière version de <span
class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="libreoffice">libreoffice</span> disponible de le dépôt
*backports*:

     apt-get -t jessie-backports install libreoffice

Par la suite, les paquets installés depuis les <span
class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="backports">backports</span> se mettront automatiquement
à jour comme pour les paquets issus de la branche principale, seule la
mise-à-jour initiale vers la version <span class="scayt-misspell-word"
data-scayt-lang="fr_FR" data-scayt-word="rétroportée">rétroportée</span>
nécessite cette déclaration explicite de la branche. Ce système est en
place pour éviter que tous les paquets proposant une version candidate
dans les <span class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="backports">backports</span> soient automatiquement
mis-à-jour dans cette version, ce qui n’est généralement pas le
comportement souhaité par l’utilisateur. Vous pourrez en apprendre plus
sur le fonctionnement de ce système (et sur les possibilités de modifier
ce comportement) dans l’article du <span class="scayt-misspell-word"
data-scayt-lang="fr_FR" data-scayt-word="wiki">wiki</span> dédié aux
priorités et aux [fichiers apt\_<span class="scayt-misspell-word"
data-scayt-lang="fr_FR"
data-scayt-word="preferences">preferences</span>](https://debian-facile.org/doc:systeme:apt:pinning "doc:systeme:apt:pinning"){.wikilink1}.

<div>

La forme **-t <span class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="backports">backports</span>** installe sans problème
les dépendances dans leur version **jessie-backports**. la forme
*nom\_paquet/<span class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="jessie-backports">jessie-backports</span>* pose des
problèmes de dépendances <span class="scayt-misspell-word"
data-scayt-lang="fr_FR" data-scayt-word="parce">parce</span> que la
version prioritaire des dépendances n'est plus plus celle des <span
class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="backports">backports</span> mais celle des autres
sources déclarées.

</div>

</div>

Voir en ligne :
[Debian-facile](http://passiongnulinux.tuxfamily.org/spip/debian-facile.org/doc:systeme:apt:sources.list#les_depots_debian_officiels){.spip_out}
