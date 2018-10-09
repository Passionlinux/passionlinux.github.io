---
title: NuTyX , une distribution atypique
date: 2016-01-31 20:22
layout: post
---

-   ![LogoNuTyX](https://img.linuxfr.org/img/687474703a2f2f7777772e6e757479782e6f72672f67726170686963732f6c6f676f5f6e757479782e706e67/logo_nutyx.png "Source : http://www.nutyx.org/graphics/logo_nutyx.png")

NuTyX est une distribution binaire véritablement optimisée pour les
architectures i686 et x86\_64. Vous pouvez utiliser le système de ports
et installer vos propres paquets depuis les sources, ils seront intégrés
nativement au système, leur gestion sera transparente.
![capture1](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e6e757479782e6f72672f436f70696573456372616e732f7468756d626e61696c732f313431353231323434352e706e67/1415212445.png "Source : http://downloads.nutyx.org/CopiesEcrans/thumbnails/1415212445.png")
![capture2](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e6e757479782e6f72672f436f70696573456372616e732f7468756d626e61696c732f313338333037393330322e706e67/1383079302.png "Source : http://downloads.nutyx.org/CopiesEcrans/thumbnails/1383079302.png")
NuTyX est une distribution GNU/Linux basée sur LFS et ses recettes sont
très proches de celles de la distribution suèdoise CRUX. NuTyX est
maintenue par Thierry Nuttens alias Tnut. C'est certainement la
distribution la plus rapide et la plus simple à installer que j'ai pu
avoir entre les mains. Pour commencer, il n'y a pas systemd, mais un
init a l'ancienne du layout bsd. Tout aussi rapide et CARDS est le
gestionnaire de paquets utilisé par cette distribution. Il est très
vivace! Mais commençons par le début, c'est a dire l'installation!  

1. Installation: {#1-installation}
----------------

Comme dit plus haut, c'est du rapide, on télécharge [la grosse
iso](http://downloads.nutyx.org/) (je plaisante, elle fait moins de
200mo…), puis on la grave sur un cd ou mieux on la met sur une clef usb.
Je ne vais pas détailler l'installation, [un article détaillé existe sur
le site](http://www.nutyx.org/fr/install.html) et Frederic Bezies a
réalisé ![une excellente vidéo montrant une installation depuis
zéro.](https://img.linuxfr.org/img/68747470733a2f2f7777772e796f75747562652e636f6d2f77617463683f763d7169647a3150566f767130/watch?v=qidz1PVovq0 "Source : https://www.youtube.com/watch?v=qidz1PVovq0")
En gros, il suffit de choisir l'option "installer" dans le menu
principal:
![installation1](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e6e757479782e6f72672f696d672f7361726176616e652f696e7374616c6c2f66722f496e7374616c6c4e755479582e706e67/InstallNuTyX.png "Source : http://downloads.nutyx.org/img/saravane/install/fr/InstallNuTyX.png")
L'installation commence instantanément, le système de base est transféré
sur la partition de destination. L'opération dure moins de 30 secondes.
Aucun téléchargement ne sera effectué, donc pas besoin de connexion
réseau.
![installation2](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e6e757479782e6f72672f696d672f7361726176616e652f696e7374616c6c2f66722f496e7374616c6c496e50726f67726573732e706e67/InstallInProgress.png "Source : http://downloads.nutyx.org/img/saravane/install/fr/InstallInProgress.png")
Ensuite l'installateur nous demande si l'on souhaite installer la
procédure d'amorçage GRUB:
![installation3](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e6e757479782e6f72672f696d672f7361726176616e652f696e7374616c6c2f66722f436f6e666967757265426f6f744166746572496e7374616c6c2e706e67/ConfigureBootAfterInstall.png "Source : http://downloads.nutyx.org/img/saravane/install/fr/ConfigureBootAfterInstall.png")
L'installation du système de base est terminée. NuTyX se lance sans
redémarrage de la machine. La configuration du système d'exploitation
peut commencer, réglage du clavier, de la carte réseau, de la date et de
l'heure et enfin la modification du mot de passe par défaut du compte
administrateur.
![installation4](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e6e757479782e6f72672f696d672f7361726176616e652f696e7374616c6c2f66722f436f6e666967757265457468302e706e67/ConfigureEth0.png "Source : http://downloads.nutyx.org/img/saravane/install/fr/ConfigureEth0.png")
![installation5](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e6e757479782e6f72672f696d672f7361726176616e652f696e7374616c6c2f66722f436f6e6669677572655554432e706e67/ConfigureUTC.png "Source : http://downloads.nutyx.org/img/saravane/install/fr/ConfigureUTC.png")
Cette fois c'est a vous de jouer et comme on peut le voir sur la
prochaine image, l'installateur vous laisse la main SANS REDEMARRER!!!
![installation6](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e6e757479782e6f72672f696d672f7361726176616e652f696e7374616c6c2f66722f52657175697265644368616e676550617373776f726441744669727374526f6f744c6f67696e2e706e67/RequiredChangePasswordAtFirstRootLogin.png "Source : http://downloads.nutyx.org/img/saravane/install/fr/RequiredChangePasswordAtFirstRootLogin.png")
Le mot de passe par défaut est nutyx. Dès que vous aurez entrez ce mot
de passe. On vous demandera de le changer immédiatement.  

2. Première prise en main: {#2-première-prise-en-main}
--------------------------

NuTyX arrive avec le gestionnaire de paquets **cards**, tout à fait
unique écrit spécialement pour les besoins de NuTyX. **Un de ses points
fort est certainement la possibilité de trouver automatiquement les
dépendances pour le fonctionnement d'un paquet.** Pour moi il dépasse
tout ce que j'ai vu en rapidité, bien que jeune, il est très stable. Il
n'y a pas encore d'interface graphique, mais il est très simple à
prendre en main
![cards](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e74757866616d696c792e6f72672f6e757479782f61726368697665732f63617264735f302e31302e38322e39362e6a7067/cards_0.10.82.96.jpg "Source : http://downloads.tuxfamily.org/nutyx/archives/cards_0.10.82.96.jpg")
En plus d'une prise en main simple, des alias sont définis pour nous
simplifier la vie. Par exemple pour vérifier si il y a des mises à jour
disponible: **cards sync** -&gt; permet d'obtenir le dernier état des
mises à jour disponibles sur votre système. **cards diff** -&gt; affiche
une liste de paquets pouvant être mis à jour. Grâce aux alias mis en
place, la commande devient:

    check

Ce qui affiche une liste de paquets à mettre à jour: Synchronizing
/var/lib/pkg/saravane/desktop from http://..
/var/lib/pkg/saravane/desktop//MD5SUM .. Differences between installed
packages and the depot of binaries:

    Package                        Installed                 Available in the depot of binaries gcc                             4.9.1                     4.9.2 glibc                           2.20                      2.21 

Ensuite, on mettra les paquets à jour (un par un), en faisant:

    cards install -u gcc

ou

    up gcc

On installe firefox avec:

    get firefox

Mais bon je vous laisse lire la [documentation très claire de
NuTyX](http://www.nutyx.org/fr/saravane-man.html) ou
[là](http://www.nutyx.org/fr/base-commands.html).  

3. NuTyX en action: {#3-nutyx-en-action}
-------------------

Donc comme on a vu, on commence par faire les mises a jour:

    check

et

    up nom-du-paquet

Ensuite on installe son bureau. Pour chercher et installer xfce:

    search xfce

    get xfce4

Environ 7 minutes plus tard (tout dépendra de votre connexion), xorg, le
bureau et les applications de xfce, ainsi que claws-mail seront
installés pour moins de 2go. J'en profite pour installer les programmes
dont j'ai besoin:

    get firefox

    get thunderbird

    get vlc

    get transmission

    get libreoffice

Ce qui me fait une distribution passe partout pour 3.8 go… C'est très
léger. Le tout en moins de 15 minutes j'ai un ensemble complet (12
minutes a peine). On peut rajouter kde avec un simple:

    get kde

A partir de là, on a une grosse partie de kde quelques paquets manquent
comme amarok par exemple. L'ensemble (kde + firefox + vlc +
libreoffice+…) fait dans les 5.1 go. Le top du top, c'est qu'une simple
commande permet de revenir sur un système de base. Cela permet de
changer complètement son environnement graphique par exemple. On peut
donc passer de KDE vers XFCE sans devoir tout réinstaller et sans devoir
tout re-télécharger. Les paquets déjà téléchargés (et à jour) seront
simplement réinstallés.

    cards base -r

Vous donnera une NuTyX toute propre c'est à dire la base seule. Pour
ajouter un paquet, la commande **cards install** suivi du nom du paquet
à installer sera utilisée:

    cards install xfce4

Le téléchargement de l'application **xfce4** commence imnmédiatement,
une fois le paquet téléchargé, ses dépendances seront à leurs tours
téléchargées. Quand le téléchargement est terminé, tous les paquets
seront installés dans le bon ordre. Dans cet exemple, une fois la
commande terminée, vous aurez un bureau [xfce4](http://www.xfce.org/)
installé sur votre NuTyX.  

4. Ajout d'un utilisateur {#4-ajout-dun-utilisateur}
-------------------------

Pour ajouter un utilisateur sous NuTyX, c'est également très simple, la
commande :

    nu

permet d'ajouter un utilisateur, elle peut être utilisée sous 2 formes
avec et sans options, si elle est utilisée sans options, 2 questions
vous seront demandées:

    Nom de l'utilisateur: francois Description de l'utilisateur: François Perrin

Vous devez bien noter que le nom d'utilisateur ne peut pas contenir
certains caractères et ne peut pas contenir d'espace ni de majuscule. Si
par contre vous souhaitez utiliser la commande avec ses options, ces
derniers sont dans l'ordre la description de l'utilisateur suivi du nom
de l'utilisateur:

    nu "François Perrin" francois

5. Une NuTyX ressemble à quoi? {#5-une-nutyx-ressemble-à-quoi}
------------------------------

![bureaux
utilisateurs1](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e6e757479782e6f72672f436f70696573456372616e732f323031352d30332d32325f31342d32302d30332e706e67/2015-03-22_14-20-03.png "Source : http://downloads.nutyx.org/CopiesEcrans/2015-03-22_14-20-03.png")
![bureaux
utilisateurs2](https://img.linuxfr.org/img/687474703a2f2f646f776e6c6f6164732e6e757479782e6f72672f436f70696573456372616e732f4361707475726573456372616e732e6a7067/CapturesEcrans.jpg "Source : http://downloads.nutyx.org/CopiesEcrans/CapturesEcrans.jpg")

-   [Site officiel de NuTyX](http://www.nutyx.org/fr/)
-   [Documentation de NuTyX](http://www.nutyx.org/fr/documentation.html)
-   [Forum De NuTyX](http://forum.nutyx.org/index.php)

<div>

P.S : Je tiens a remercier Tnut, pour sa patience et sa relecture.

</div>
