---
title: Handylinux; Debian plus simple qu'Ubuntu ! À la découverte d'Handylinux...
date: 2016-04-30 20:01
layout: post
---


<div class="main">

<div class="chapo surlignable">

La dernière fois que j’ai parlé de Debian fut pour les deux articles
consacrés aux débutants et Debian. On peut reprocher beaucoup de chose a
cette distribution mais pas sa stabilité qui est un gage de
tranquillité. On peut voir de plus en plus de distributions qui se
basaient sur Ubuntu faire des versions sur Debian, comme Mint Linux
Debian Edition (LMDE) pour ne citer qu’elle… Celle-ci a raté le coche,
d’abord elle a fait une première version de lmde basé sur testing de
Debian avec une temporisation des paquets permettant, en théorie, de
stabiliser la bête sauf que préoccupé par le succès de sa Mint basé sur
Ubuntu, elle l’a délaissé tellement que l’écart entre testing et lmde
s’agrandit, qu’il n’était plus possible pour l’équipe de proposer des
mises a jour sans casser la distribution, que même les corrections de
failles n’étaient pas appliqué et qu ’elle fut abandonné sans un mot par
ses développeurs... Elle a essayé de remédier a cette erreur de
jeunesse, en faisant pour sa LMDE2, le choix de stable comme base,
malheureusement le mal était fait et la priorité donné a sa version
Ubuntu a fini par tuer cette version.  
<!--more-->  
C’est vraiment très mal pensé quand on sait que la base Debian aurait
permis d’être totalement libéré d’Ubuntu et de ses choix surtout quand
on connaît le succès d’une certaine Manjaro qui part du même principe
que LMDE mais en prenant Archlinux comme base…

</div>

<div class="texte surlignable">

On a vu aussi, le succès que pouvait avoir des distributions basées sur
d’autres et qui ont de différent que l’ajout d’un dépôts contenant des
thèmes ou quelques améliorations et surtout un installateur simple,
comme Antergos qui est une Archlinux avec des thèmes et des paquets
venant de AUR directement dans un dépôt propre a Antergos en plus des
dépôts de Archlinux, ou Sabayon et Calculate pour Gentoo. Dans le monde
des distributions linux, il y en a une qui a fait le pari un peu fou, de
rendre Debian accessible pour tous, les moins jeunes et les pas très
doués, d’avoir une bonne reconnaissance matériel, et plein de bonne
chose qui facilite la vie comme le handymenu, handyupdate et bien
d’autre,…  
On va voir de plus prés celle-ci.  
### Découvrir HandyLinux {#outil_sommaire_0 .spip}

Tout est parti d’un simple constat :  
**les informaticiens et les utilisateurs ne parlent pas le même
langage…**

<dl class="spip_document_4 spip_documents spip_documents_center">
<dt style="text-align: center;">
![JPEG -
42.1 ko](http://download.tuxfamily.org/passionlinux/IMG/distant/jpg/langage20inf4e9f.jpg)
</dt>
<dt class="spip_doc_titre" style="width: 340px;">
**langage informatique**
</dt>
</dl>
**Mais alors ... comment va-t-on faire ?**  
**Simple : on lit la documentation d’Handy Linux !** HandyLinux c’est
**l’accessibilité** pour tous et la **liberté** pour chacun
**d’évoluer** à son gré. Basée sur **Debian GNU/Linux** avec **XFCE**,
un environnement de bureau rapide, léger et stable. HandyLinux est
**sûre, pratique et gratuite.** Conçue pour **faciliter l’accès à
l’informatique** à ceux qui débutent : les enfants, les seniors et ceux
qui sont en quête de simplicité. Pour cela, elle comprend :

-   un **pack simplifié d’applications** pour les tâches courantes :
    (navigation sur le net, mail, suite office, logiciels
    photo/audio/vidéo, skype en option) facilement accessibles depuis le
    [HandyMenu](https://handylinux.org/wiki/doku.php/fr/handymenu){.spip_out}
-   la **logithèque Debian** riche de milliers d’applications pour
    les aventuriers.
-   une [aide
    complète](https://handylinux.org/wiki/doku.php/fr/start){.spip_out}
    en ligne et une [initiation
    intégrée](https://handylinux.org/wiki/doku.php/fr/initiation){.spip_out}
    à la distribution afin de répondre à vos questions et accompagner
    votre progression.  
   \_\* si vous êtes en situation de handicap, la rubrique
    [“access”](https://handylinux.org/wiki/doku.php/fr/access){.spip_out}
    est là pour faciliter l’accès aux différentes fonctions de
    l’ordinateur : loupe d’écran minimale, clavier virtuel et
    synthèse vocale.

### Le but d’HandyLinux {#outil_sommaire_1 .spip}

**Le but secret d’HandyLinux ?? Vous passer d’handylinux !!**  
Cette distribution n’est là que pour faciliter l’utilisation des outils
informatiques. Une fois votre environnement apprivoisé, il vous suffit
de supprimer les options facilitantes et vous obtenez une distribution
Debian “classique” avec XFCE comme environnement de bureau grâce à
[Handy2Debian](https://handylinux.org/wiki/doku.php/fr/evolution#handy2debianle_plus_radical){.spip_out}.  

### Matériel requis et applications {#outil_sommaire_2 .spip}

-   HandyLinux s’installe sur tout ordinateur moderne (PIV ou supérieur)
    pourvu de 512Mo de mémoire et nécessite 3,4 Go d’espace disque
    minimum pour le système.
-   savoir lire : les messages affichés par HandyLinux ne sont pas de la
    publicité comme sur les OS payants... prenez le temps de les lire.

HandyLinux contient :

-   environnement de bureau :
    [XFCE](http://wiki.xfce.org/fr/start){.spip_out}
-   gestionnaire de fichiers :
    [Thunar](https://handylinux.org/wiki/doku.php/fr/fichiers#thunarvotre_gestionnaire_de_fichiers){.spip_out}
-   navigateur internet :
    [Iceweasel](https://handylinux.org/wiki/doku.php/fr/internet#iceweasel){.spip_out} (Firefox)
-   client de messagerie :
    [Icedove](https://handylinux.org/wiki/doku.php/fr/internet#icedove){.spip_out} (Thunderbird)
-   communication : [Hello sur
    Iceweasel](https://handylinux.org/wiki/doku.php/fr/internet#hello_vs_skype){.spip_out}
    ou
    [Skype-](https://handylinux.org/wiki/doku.php/fr/internet#skype){.spip_out}
    (en option)
-   lecteur vidéo :
    [VLC](https://handylinux.org/wiki/doku.php/fr/media#vlc){.spip_out}
-   client torrent P2P :
    [Transmission](https://handylinux.org/wiki/doku.php/fr/internet#transmission){.spip_out}
    &
    [Btshare](https://handylinux.org/wiki/doku.php/fr/partager#btsharele_partage_torrent_simplifie){.spip_out}
-   lecteur audio :
    [Clementine](https://handylinux.org/wiki/doku.php/fr/media#clementine){.spip_out}
-   visionneuse d’images :
    [Ristretto](https://handylinux.org/wiki/doku.php/fr/media#ristretto){.spip_out}
-   suite bureautique :
    [LibreOffice](https://handylinux.org/wiki/doku.php/fr/office#libreoffice){.spip_out}
-   éditeur de texte :
    [MousePad](https://handylinux.org/wiki/doku.php/fr/office#mousepad){.spip_out}
-   gestionnaire d’archives :
    [Xarchiver](https://handylinux.org/wiki/doku.php/fr/tools#archives){.spip_out}
-   aide et contrôle à distance :
    [TeamViewer](https://handylinux.org/wiki/doku.php/fr/aventuriers#teamviewer){.spip_out}
    (en option)
-   suite d’outils pour
    l’[accessibilité](https://handylinux.org/wiki/doku.php/fr/access){.spip_out} :
    filtre d’écran, inverseur de couleurs, loupe d’écran, clavier
    virtuel, [menu
    simplifié](https://handylinux.org/wiki/doku.php/fr/handymenu#handymenu_--_un_seul_lanceur_pour_tout_faire){.spip_out}
-   gestionnaire d’impression, de numérisation et principaux drivers
    intégrés
-   aide française complète en ligne et initiation intégrée

<p>
On a pu découvrir ensemble une partie de cette formidable distribution,
dans le [prochain article on verra
l’installation](http://passiongnulinux.tuxfamily.org/?p=14){.spip_in}.

</div>

</div>

 
