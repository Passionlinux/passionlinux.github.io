---
title: Interagir avec son téléphone Android sous Linux et KDE, c'est avec KDEconnect
date: 2016-10-07 21:58
layout: post
---

Cela fait un bon moment que je voulais me faire un petit pense bête sur
cette application que j'utilise depuis openSUSE 13.2. Un petit réglage
est nécessaire du coté pc et pare-feu et aussi sur l'appareil Android,
pour le rendre fonctionnel, après c'est que du bonheur.  
<!--more-->  
**KDE Connect** permet une interaction entre son téléphone Android et
son PC sous KDE**:**

-   <div class="li">

    D'envoyer des fichiers depuis le téléphone vers le dossier personnel
    du PC,

    </div>

-   D'envoyer des fichiers depuis le PC vers le téléphone,
-   <div class="li">

    Copier-coller du texte dans les deux sens (PC - Téléphone), très
    pratique pour des liens ou numéros de téléphone,

    </div>

-   <div class="li">

    Recevoir par notification sur le PC les SMS, Facebook, alerte d'état
    de batterie faible…

    </div>

-   Recevoir par notification sur Téléphone les alertes de KDE...
-   <div class="li">

    de commander les logiciels multimédias (amarok, spotify, Vlc…)

    </div>

-   <div class="li">

    de se servir du smartphone comme d'un touchpad ou d'un clavier

    </div>

-   de répondre au SMS directement sur son PC (depuis plasma 5.8)

On va commencer par installer le programme sur le PC et sur le
téléphone, je passe l'installation sur le téléphone puisqu'il suffit de
chercher KDEconnect dans le
[googleplaystore.](https://play.google.com/store/apps/details?id=org.kde.kdeconnect_tp)
Pour openSUSE (sous leap, il faudra activer le dépôt kde:extra):
`zypper install kdeconnect-kde sshfs ` Pour Debian:
`apt-get install kdeconnect` Ensuite, il faut faire un petit réglage
dans le pare-feu de la distribution, on autorise les ports 1714:1764 et
c'est tout. Sur le tel, on active le Bluetooth ou le wi-fi et on demande
l'appareillage a notre PC qui doit être visible sur le réseau. Sur le
PC, on autorise cette demande, rien de plus.

<div class="level4">

Pour copier des fichiers de l'ordinateur vers le périphérique :
-   <div class="li">

    Il faut que
    ***[sshfs](https://doc.ubuntu-fr.org/sshfs "https://doc.ubuntu-fr.org/sshfs"){.urlextern}*
    soit installé afin que *Dolphin* puisse se connecter** directement à
    l'appareil via *KDE Connect* .

    </div>

-   <div class="secedit editbutton_section editbutton_5">

    On peut également charger rapidement des fichiers sur le téléphone
    en les sélectionnant dans *Dolphin* , puis *Menu clic droit ? Send
    to Mon\_Peripherique via kde connect* . Les fichiers seront alors
    copiés sur le téléphone dans un dossier nommé *kdeconnect/* .

    </div>

    <div class="secedit editbutton_section editbutton_5">

    </div>

    <div class="secedit editbutton_section editbutton_5">

    </div>

C'est court mais que dire de plus si il n'y a pas plus de réglage que
ça?  

</div>
