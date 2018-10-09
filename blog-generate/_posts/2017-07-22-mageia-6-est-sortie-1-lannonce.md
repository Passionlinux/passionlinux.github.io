---
title: Mageia 6 est sortie 1, l'annonce
date: 2017-07-22 16:22
layout: post
---

Toute la communauté de [Mageia](https://www.mageia.org/) est très
heureuse d’annoncer la publication de [Mageia
6](https://www.mageia.org/6), le brillant résultat de notre long cycle
de publication ! Elle inclut de nombreuses nouvelles fonctionnalités, un
nouveau jeu d’images d’installation et l’utilisabilité et la stabilité
que l’on peut attendre de toute publication de Mageia. Voir les [notes
de version](https://wiki.mageia.org/en/Mageia_6_Notes_de_version-fr)
pour de plus amples détails.  
<!--more-->  
Bien que le développement de Mageia 6 fut beaucoup plus long que prévu,
nous avons pris le temps de l’affiner et de nous assurer que ce sera
notre meilleur publication à ce jour. Nous remercions notre communauté
pour sa patience, ainsi que nos empaqueteurs et notre équipe Assurance
Qualité qui ont fourni un support étendu à Mageia 5, bien au-delà du
calendrier initial. Pour les plus impatients, voici les principaux liens
qui vont vous permettre de télécharger et de bien préparer votre
installation de Mageia 6 :

-   [Télécharger Mageia 6](https://www.mageia.org/6)
-   [Instructions d’installation en
    français](https://doc.mageia.org/installer/6/fr/content/index.html)
    et dans [plusieurs autres langues](https://www.mageia.org/doc/)
    également
-   [Notes de
    version](https://wiki.mageia.org/en/Mageia_6_Notes_de_version-fr)
-   [Errata](https://wiki.mageia.org/en/Mageia_6_Errata-fr)
    (problèmes connus)

Principales nouveautés de Mageia 6
----------------------------------

Le temps supplémentaire qui a été consacré dans cette version a permis
des changements majeurs, voici une sélection des principales évolutions
pour Mageia 6 :

-   KDE Plasma 5 remplace l’ancien environnement de bureau KDE SC 4
-   Le nouveau gestionnaire de paquetages DNF est fourni comme une
    alternative à urpmi, permettant un système de paquetage hétérogène
    et exceptionnel :
    -   Support pour AppStream et donc GNOME Software et Plasma Discover
    -   Prise en charge de Fedora COPR et openSUSE Build Service pour
        fournir des paquetages tiers pour Mageia 6 et des versions
        ultérieures
    -   dnfdragora, un nouvel outil graphique pour la gestion de
        paquetages inspiré de rpmdrake
-   Nouveau thème d’icônes pour tous les outils Mageia, notamment le
    Centre de Contrôle de Mageia
-   Une intégration réussie du port ARM (ARMv5 et ARMv7) dans le système
    de construction des paquetages, permettant de configurer des
    chroots ARM. Les images d’installation ne sont pas encore
    disponibles mais seront publiées prochainement.
-   GRUB2 comme chargeur d’amorçage par défaut
-   Nouvelles images Xfce Live pour tester Mageia avec un environnement
    plus léger
-   Bien qu’il ne s’agisse pas d’une nouvelle fonctionnalité, Mageia 6
    prend en charge plus de 25 environnements de bureau et gestionnaires
    de fenêtres (les détails seront disponibles lors d’une prochaine
    publication sur le blog) !

<div id="attachment_1912" class="wp-caption alignnone">

![Centre de Contrôle de
Mageia](http://blog.mageia.org/fr/wp-content/uploads/2017/07/Mageia-6-MCC.png){.size-full
.wp-image-1912 width="952" height="725"}
Aperçu du Centre de contrôle de Mageia avec ses nouvelles icônes

</div>

Les détails complets de ces points forts peuvent être lus dans les
[notes de
version](https://wiki.mageia.org/en/Mageia_6_Notes_de_version-fr#Principales_nouveaut.C3.A9s_de_la_version),
et certains d’entre eux feront l’objet de divers articles de blog
propres à chacun dans les prochaines semaines.  

Les versions des paquetages
---------------------------

Tous les logiciels dans les dépôts ont été reconstruits et mis à jour
pour inclure les derniers et les plus important logiciels de
l’écosystème open source, vous trouverez ci-dessous quelques-uns des
principaux composants inclus dans cette version :

-   Système de base : Linux Kernel 4.9.35 (LTS), systemd 230, X.org
    1.19.3, Wayland 1.11.0, Mesa 17.1.4
-   Toolkits : Qt 5.6.2 (LTS), GTK+ 3.22.16
-   Environnements de bureau : Plasma 5.8.7 (LTS), GNOME 3.24.2, MATE
    1.18, Cinnamon 3.2.8, Xfce 4.12.1, LXQt 0.11
-   Applications : LibreOffice 5.3.4.2, Firefox 52.2.0 ESR, Thunderbird
    52.2.1, Chromium 57

La plupart des applications tournées vers l’utilisateur sont des
versions très récentes, ce qui apporte aux utilisateurs de Mageia le
meilleur des projetsde logiciels libres en 2017. Les composants
essentiels de la distribution utilisent des versions légèrement plus
conservatrices (version LTS), permettant un bon compromis entre les
nouveaux développements et la stabilité.  

Nouvelle gamme d’images ISO
---------------------------

Au cours du cycle de développement de Mageia 6, nous avons changé la
gamme des images ISO pour inclure les images avec Xfce Live (32 bits et
64 bits) et nous avons supprimé les images 32 bits de GNOME et de Plasma
Live ainsi que l’installateur dual-arch. Cela a apporté un certain
nombre de bénéfices : nous déployons dorénavant un environnement léger
Xfce Live pour l’installation à la fois 32 et 64 bits, tout en réduisant
le nombre d’ISO supportées et en précisant quels sont les choix
d’installation disponibles pour chaque cas d’utilisation. Voici la gamme
complète des ISO de Mageia :

-   32-bit Installation classique DVD
-   64-bit Installation classique DVD
-   GNOME 64-bit Live DVD
-   Plasma 64-bit Live DVD
-   Xfce 32-bit Live DVD
-   Xfce 64-bit Live DVD

Pour ceux qui souhaiteraient installer Plasma ou GNOME en 32 bits, ils
sont disponibles sur le support classique d’installation ou par
l’installation en réseau. Toutes les ISO sont hybrides, afin qu’ils
puissent être utilisés à la fois sur les clés USB et pour les DVD ; si
un CD de démarrage est requis, plusieurs images d’installation en réseau
sont disponibles et peuvent utiliser comme sources supplémentaires pour
compléter une installation incluant un miroir local, un miroir en réseau
ou une ISO en installation classique. Consultez la documentation pour
plus d’informations sur les [possibilités
d’installation](https://wiki.mageia.org/en/Mageia_6_Notes_de_version-fr#Introduction).  

La nouvelle apparence de Mageia 6
---------------------------------

Nous avons créé un nouveau thème complet pour Mageia 6 incluant des
améliorations avec la mise à l’échelle de l’image pendant le démarrage,
ainsi qu’un nouvel ensemble d’icônes et diverses évolutions dans
l’apparence de toutes les applications spécifiques à Mageia telles que
le Centre de Contrôle (MCC). Un grand merci à Timothée Giet pour son
travail de modernisation et d’uniformisation du thème général de Mageia
!

<div id="attachment_1913" class="wp-caption alignnone">

![Fond d'écran de Mageia
6](http://blog.mageia.org/fr/wp-content/uploads/2017/07/Mageia-Default-1920x1080.png){.size-full
.wp-image-1913 width="1920" height="1080"}
Fond d’écran par défaut de Mageia 6

</div>

Le nouveau thème est défini également par un nouveau fond d’écran
réalisé par Jacques Daugeron ainsi que d’autres images supplémentaires
qui ont été sélectionnées par le Conseil de Mageia lors du concours
communautaire. Les fonds d’écran des versions précédentes de Mageia
restent aussi disponibles. Il existe également de nouveaux économiseurs
d’écran créés à partir du concours de fond d’écran.  

Calendrier de maintenance
-------------------------

Pour ceux qui se posent la question de Mageia 5, elle sera encore
maintenue pendant 3 mois, avec une fin de vie prévue le 31 octobre 2017,
ce qui vous donnera un peu de temps pour effectuer une mise à niveau.
Cela fera de Mageia 5, la version la plus longtemps maintenue jusqu’à
présent, puisqu’elle a été publiée en juin 2015 ! Mageia 6 sera
maintenue pendant au moins 18 mois, c’est-à-dire jusqu’au 16 janvier
2019. Si la durée devait être prolongée comme ce fut le cas pour Mageia
5, ce sera annoncé sur ce blog et mis à jour [sur le
site](https://www.mageia.org/support/).  

Pourquoi choisir Mageia ?
-------------------------

En un mot : [Communauté](https://www.mageia.org/community/). Mageia est
une distribution Linux de premier ordre entièrement réalisée par et pour
sa communauté. Sans coopération contraignante,  sans entreprise derrière
elle, seulement des utilisateurs qui passent un bon moment à développer
la distribution qu’ils utilisent quotidiennement, à la maison ou au
travail. Et en tant qu’utilisateur de Mageia, vous faites partie de
cette expérience enrichissante, et vous pouvez [contribuer de
différentes façons](https://www.mageia.org/contribute/) pour en faire la
vôtre. Mageia est façonnée pour ses utilisateurs et convient donc dans
n’importe quel environnement : travail, maison, serveurs, loisir etc.
Tout est directement pris en charge par la communauté à travers les
dépôts officiels, sans idées préconçues. Mageia s’est toujours efforcée
d’offrir une expérience d’utilisation universelle dans un large éventail
d’environnements de bureau, avec l’intégration des meilleurs outils de
contrôle et d’administration disponibles pour certains d’entre eux.  

Hissés sur les épaules de géants
--------------------------------

Nos équipes de développeurs, de packagers, de testeurs de contrôle de la
qualité, de rapporteurs et trieurs de bugs, d’écrivains pour la
documentation, de traducteurs et d’administrateurs système ont tous
travaillé très dur dans la préparation et l’aboutissement de la
distribution afin de vous offrir Mageia 6 et nous les remercions pour
leur travail bénévole sur notre projet indépendant et communautaire !
Nous sommes tous reconnaissants du travail étonnant fait par tous les
projets de logiciels libres que nous distribuons, tels que le noyau
Linux, le projet GNU, SystemD, X.org, Mesa 3D, KDE, GNOME, Xfce,
Mozilla, LibreOffice et bien d’autres. Cela inclut également les autres
distributions GNU/Linux avec lesquelles nous collaborons et toutes les
nombreuses personnes qui écrivent et testent des logiciels libres. Merci
à vous tous de nous inspirer et de faire les excellents logiciels qui
constituent le fondement de Mageia.

<div class="sharedaddy sd-sharing-enabled">

 https://blog.mageia.org/fr/2017/07/16/mageia-6-est-la/

</div>

<div>

http://linuxfr.org/news/mageia-6-est-sortie

</div>
