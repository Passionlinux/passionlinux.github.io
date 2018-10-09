---
title: Développer pour Frugalware 4, Créer son propre dépôt pour ses paquets
date: 2014-06-12 23:00
layout: post
---

Ceci est une adaptation fait a partir du wiki de Frugalware pour une
version http au lieu de ftp. Vous savez désormais concevoir des
FrugalBuild et compiler des paquets .fpm, vous pouvez donc si vous le
désirez créer votre propre dépôt pour une utilisation personnelle ou
publique.  

Organisation du dépot
---------------------

Le dépot doit suivre une certaine hierarchie. En effet au même niveau
vous devez avoir deux dossiers, l'un contenant les FrugalBuilds répartie
dans des dossiers portant le même nom que le groupe du paquet puis dans
un dossier portant le même nom que le paquet lui étant associé et
l'autre dossier doit contenir vos paquet FPM. **Exemple:** Appellons
//source// le dossier avec les FrugalBuild et *frugalware-i686* le
dossier contennat les paquets FPM pour architecture i686. Supposons que
vous ayez qu'un seul paquet, par exemple le jeu Ri-li. Voici à quoi
devrait ressembler votre dépôt:

      /source      |-----/games-extra                 |---/ri-li                        |-------FrugalBuild  /frugalware-i686       |-----ri-li-2.0.0-1-i686.fpm

Ensuite il vous faudra créer un fichier .fdb c'était un fichier de base
de données nécéssaire à la synchronisation de pacman avec votre dépôt.
Pour cela il vous utiliser la commande **gensync** Il faut que gensync
génère un fichier .fdb en se basant sur le contenu de du dossier
*source* de notre exemple puis qu'il crée le fichier .fdb à l'intérieur
du dossier *frugalware-i686*. Voici un exemple de la commande à
utiliser:

<div
style="background: #ffe9e9; border: 1px solid #cccccc; padding: 4px 6px; text-align: left;">

<div>

**\# gensync /chemin/source/ /chemin/frugalware-i686/monfichier.fdb
/chemin/frugalware-i686/**

</div>

</div>

Le fichier monfichier.fdb sera donc crée dans le dossier
*frugalware-i686*.

-   Note: pour que gensync fontionne, assurez-vous d'avoir dans votre
    makepkg.conf la ligne suivante:

<!-- -->

      export BUILDSCRIPT="FrugalBuild"

Mise en place du dépôt
----------------------

Pour une utilisation personnelle, vous garder le contenu votre dépôt sur
votre ordinateur ou même le graver sur un média amovibe (CD-Rom par
exemple). Pour une utilisation orienté publique le mieux est d'envoyer
le contenu de votre dépôt sur un serveur ftp. Ensuite vous devez activer
votre dépôt avec pacman. Deux possibilités s'offrent à vous.

-   Pour une utilisation perso, vous pouvez éditer directement
    **pacman-g2.conf**

<div
style="background: #ffe9e9; border: 1px solid #cccccc; padding: 4px 6px; text-align: left;">

<div>

**\# nano /etc/pacman-g2.conf**

</div>

</div>

et y ajoutez la ligne suivante: exemple pour un dossier sur votre
ordinateur

      [mondepot]  Server=file:///chemin/mondepot/frugaware-x86_64

sans le \# devant \[mondepot\] sinon erreur de syntaxe \[mondepot\]
correspond au nom du fichier sync mondepot.fdb se trouvant dans
/chemin/mondepot/frugaware-x86\_64/ exemple pour un cd-rom

      Server=file:///mnt/cdrom.

-   Par contre pour un serveur ftp, au cas où vous aurez la possibilité
    d'avoir des mirroirs, le mieux serait de créer un fichier portant le
    nom de votre dépôt dans le dossier \*\*/etc/pacman-g2/repos/\*\*

<div
style="background: #ffe9e9; border: 1px solid #cccccc; padding: 4px 6px; text-align: left;">

<div>

**\# nano /etc/pacman-g2/repos/mondepot**

</div>

</div>

Puis dans ce fichier vous y ajouter toutes les adresses ftp des mirroirs
dans cette forme:

      Server = ftp://mon.adresse.org/chemindemondepot/dossieravecpaquets-i686

Puis dans pacman-g2.conf vous indiquer votre fichier mondepot ayant la
liste des miroirs

<div
style="background: #ffe9e9; border: 1px solid #cccccc; padding: 4px 6px; text-align: left;">

<div>

**\# nano /etc/pacman-g2.conf**

</div>

</div>

et ajoutez:

      Include = /etc/pacman-g2/repos/mondepot

Tester votre dépôt avec pacman
------------------------------

<div
style="background: #ffe9e9; border: 1px solid #cccccc; padding: 4px 6px; text-align: left;">

<div>

**\# pacman-g2 -Syu**

</div>

</div>

puis essayer d'installer vos paquets comme d'habitude avec pacman  

Version pour serveur http:
--------------------------

Voila la partie qui est interessante, la partie rajouté pour une
utilisation avec un serveur http, dans mon cas apache.

-   créer un fichier portant le nom de votre dépôt dans le dossier
    \*\*/etc/pacman-g2/repos/\*\*

<div
style="background: #ffe9e9; border: 1px solid #cccccc; padding: 4px 6px; text-align: left;">

<div>

**\# nano /etc/pacman-g2/repos/mondepot**

</div>

</div>

Puis dans ce fichier vous y ajouter toutes les adresses ftp des mirroirs
dans cette forme:

      Server = http://mon.adresse.org/chemindemondepot/dossieravecpaquets-i686

Puis dans pacman-g2.conf vous indiquer votre fichier mondepot ayant la
liste des miroirs

<div
style="background: #ffe9e9; border: 1px solid #cccccc; padding: 4px 6px; text-align: left;">

<div>

**\# nano /etc/pacman-g2.conf**

</div>

</div>

et ajoutez:

      Include = /etc/pacman-g2/repos/mondepot

On demarre le serveur avec un

<div
style="background: #ffe9e9; border: 1px solid #cccccc; padding: 4px 6px; text-align: left;">

<div>

**\# systemctl start httpd.service**

</div>

<div>

<div>

**\# systemctl enable httpd.service**

</div>

</div>

</div>

Enfin on teste le tout en allant sur
<http://localhost/mespaquets/frugalware-x86_64/>
