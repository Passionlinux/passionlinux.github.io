---
title: Améliorer KDE4 sous Debian.
date: 2016-06-03 22:44
layout: post
---

Installer KDE4
--------------

<div>

*Plusieurs versions sont disponibles*
-   <div>

    [kde-full, la version complète
    de KDE.](http://packages.debian.org/fr/wheezy/kde-full "http://packages.debian.org/fr/wheezy/kde-full"){.urlextern}

    </div>

-   <div>

    [kde-standard, la version standard
    de kde.](http://packages.debian.org/squeeze/kde-standard "http://packages.debian.org/squeeze/kde-standard"){.urlextern}

    </div>

-   <div>

    [kde-plasma-desktop, la
    version minimale.](http://packages.debian.org/fr/wheezy/kde-plasma-desktop "http://packages.debian.org/fr/wheezy/kde-plasma-desktop"){.urlextern}

    </div>

-   <div>

    [Environnemnt de bureau Debian avec
    KDE](http://packages.debian.org/fr/wheezy/task-kde-desktop "http://packages.debian.org/fr/wheezy/task-kde-desktop"){.urlextern}

    </div>

*Pour installer*

     apt-get update && apt-get install kde-full kdm kde-l10n-fr

ou

     apt-get update && apt-get install kde-standard kdm kde-l10n-fr

ou

     apt-get update && apt-get install kde-plasma-desktop kdm kde-l10n-fr

ou

     apt-get update && apt-get install task-kde-desktop task-french-kde-desktop

<div>

kdm, est le gestionnaire de connexion de kde et kde-l10n-fr permet la
localisation de kde pour le français.

</div>

<p>
*Et voilà*
![:-)](http://localhost/spip/sites/default/local/cache-vignettes/L15xH15/icon_smilegib868-95d6c.gif){.icon
width="15" height="15"}
[![](http://localhost/spip/sites/default/IMG/distant/png/file-Rea32d708d3.png?1468442459){.mediacenter
width="500"
height="282"}](https://debian-facile.org/images/file-Rea32d7ecf34f50755eaeb97e92d7c8be.png "/file-Rea32d7ecf34f50755eaeb97e92d7c8be.png"){.media}

</div>

Le menu Kickoff
---------------

<div>

**Le menu *Kickoff* est un menu à partir duquel vous aurez accès à tout
votre système.** *Onglet *Favoris** Ici on pourra avoir sous la main nos
logiciels favoris. Certains sont déjà positionnés par défaut.
-   <div>

    Configuration du système

    </div>

-   <div>

    Gestionnaire de fichiers

    </div>

-   <div>

    Navigateur Web (Konqueror)

    </div>

Pour ajouter un logiciel dans les Favoris, il faut faire un clic droit
sur l’icône de celui-ci et de cocher: ***Ajouter aux Favoris*** .
*Onglet *Applications** On trouve dans cet onglet tous les logiciels,
ils sont classés par catégories. *Onglet *Poste de Travail** Avec cet
onglet on navigue dans tout l'ordinateur, de la racine jusqu'aux plus
petits des sous-répertoires et fichiers en passant par la corbeille. Il
permet aussi d'ouvrir le *Centre de configuration*. *Onglet *Utilisé
récemment** Tout est dit dans l'intitulé, on accède aux fichiers
utilisés récemment mais aussi aux applications utilisées récemment.
*Onglet *Quitter** Pour arrêter l'ordinateur, redémarrer, changer
d'utilisateur, fermer la session, etc…
[![](http://localhost/spip/sites/default/local/cache-vignettes/L477xH546/file-R9fbd26c11a-db00c.jpg){.mediacenter
.alignnone width="477"
height="546"}](https://debian-facile.org/images/file-R9fbd26eaaed5375269f854e0bdcd6af9.png "/file-R9fbd26eaaed5375269f854e0bdcd6af9.png"){.media}

<div>

Vous pouvez préférer un ***menu classique***. Pour cela il suffit de
faire un *clic-droit* dans le lanceur d'applications tout en bas à
gauche. Ensuite, ***Déverrouiller les Plasmoïdes*** puis choisir,
***Style de menu classique***. Pour revenir au menu Kickoff il faut
refaire la même manipulation et sélectionner ***Style de menu
Kickoff***.

</div>

<p>
[![](http://localhost/spip/sites/default/local/cache-vignettes/L425xH81/file-R13f6ba8aab-6f10d.png){.mediacenter
width="425"
height="81"}](https://debian-facile.org/images/file-R13f6ba5cf5cf3d48d25d4ef76d58791e.png "/file-R13f6ba5cf5cf3d48d25d4ef76d58791e.png"){.media}
[![](http://localhost/spip/sites/default/local/cache-vignettes/L426xH136/file-Rb8b590e8b5-e5dc7.png){.mediacenter
width="426"
height="136"}](https://debian-facile.org/images/file-Rb8b5906af47daba0bf1060220fbb6b48.png "/file-Rb8b5906af47daba0bf1060220fbb6b48.png"){.media}
*Le *Menu classique**
[![](http://localhost/spip/sites/default/local/cache-vignettes/L316xH359/file-Rbd6644c1a1-037bb.png){.mediacenter
width="316"
height="359"}](https://debian-facile.org/images/file-Rbd6644fc488076619d64f1e3298c1ead.png "/file-Rbd6644fc488076619d64f1e3298c1ead.png"){.media}

</div>

Les Composants Graphiques anciennement Plasmoïdes
-------------------------------------------------

<div>

</div>

### C'est quoi?

<div>

Ils sont la grande nouveauté de KDE4. Les ***Composants Graphiques***
sont des objets que l'on peut placer sur le *Bureau* ou sur le *Tableau
de bord*. -On peut leur donner la taille que l'on veut, les positionner
où l'on veut, les faire pivoter et les configurer. -Les Composants
Graphiques peuvent être n'importe quoi: le contenu d'un dossier, une
icône pour le lancement d'une application, une horloge, le menu Kickoff,
le nombre de courriels non lus, la météo, les performances du système,
la barre de tâche etc…

</div>

### Ajouter des Composants Graphiques

<div>

Pour ajouter des *Composants Graphiques*, il faut d'abord les
*Déverrouiller*. Pour cela, il faut cliquer sur le menu situé sur un
bord de l'écran. Un écran apparaît, il suffit de cliquer sur
***Déverrouiller les composants graphiques***:
[![](http://localhost/spip/sites/default/local/cache-vignettes/L300xH343/file-R35a644afbe-d0bf5.jpg){.mediacenter
width="300"
height="343"}](https://debian-facile.org/images/file-R35a644099718dabcebf97b922f8f0bdf.png "/file-R35a644099718dabcebf97b922f8f0bdf.png"){.media}
Il suffit ensuite de choisir, ***Ajouter des Composants Graphiques***.
[![](http://localhost/spip/sites/default/IMG/distant/png/file-R9a35be75ef.png?1468442463){.mediacenter
width="500"
height="92"}](https://debian-facile.org/images/file-R9a35be64aba9ac54a39d4459a13d93ea.png "/file-R9a35be64aba9ac54a39d4459a13d93ea.png"){.media}
Pour les ajouter, il faut les faire glisser à l'endroit voulu, sur le
*bureau* ou sur le *tableau de bord*.

</div>

### Manipuler les Composants Graphiques

<div>

Lorsque les ***Composants Graphiques sont déverrouillés***, vous pouvez
les manipuler. Il suffit de passer la souris sur le *Composant
Graphique* et une petite languette apparaît sur le côté. *Dans l'exemple
ci-dessous nous pouvons observer cinq symboles.*
-   <div>

    Le symbole du haut sert à redimensionner le *Plasmoïde*.

    </div>

-   <div>

    Juste en dessous , ce symbole sert à faire pivoter le *Composant
    Graphique*.

    </div>

-   <div>

    La clef à mollette ouvre une fenêtre pour paramétrer le *Composant
    Graphique*.

    </div>

-   <div>

    Le carré avec quatre flèches ouvre le dossier dans *Dolphin*.

    </div>

-   <div>

    La croix, quant à elle, supprime le *Composant Graphique*.

    </div>

<p>
[![](http://localhost/spip/sites/default/local/cache-vignettes/L364xH167/file-Rfb08a340ac-96482.png){.mediacenter
width="364"
height="167"}](https://debian-facile.org/images/file-Rfb08a3f8c8b90c7e7c756a35bb6538b4.png "/file-Rfb08a3f8c8b90c7e7c756a35bb6538b4.png"){.media}

</div>

Les Activités
-------------

<div>

</div>

### Qu'est que c'est

<div>

**Les Activités sont un moyen d'organiser son travail.** Nous avons
l'habitude des bureaux virtuels et nous pouvons passer de l'un à l'autre
pour avoir accès à différents programmes qui sont ouverts dans ces
derniers. Malgré tout, ils sont tous identiques. Avec les *Activités*,
tout est différent. Imaginez que vous ayez une activité dans une
**association**, activité **loisir** passionnante, que vous utilisez
votre ordinateur pour le **travail** ou bien que vous ayez un **projet**
important. Hé bien, vous pourrez **créer des *Agencements* ou
*Activités* pour chacun d'eux**. Vous aurez alors quatre *Activités*.
1.  <div>

    Association

    </div>

2.  <div>

    Loisir

    </div>

3.  <div>

    Travail

    </div>

4.  <div>

    Projet

    </div>

<p>
*Chaque Activités peut avoir avoir sa propre organisation, son propre
fond d'écran, ses propres Composants Graphiques ou icônes.*

</div>

### Changer d'Activité

<div>

Par défaut le bureau KDE de Debian propose quatre activités:
1.  <div>

    Desktop

    </div>

2.  <div>

    Icônes de Bureau

    </div>

3.  <div>

    Activité Photographique

    </div>

4.  <div>

    Recherché et lancer

    </div>

<p>
Pour Changer d'activité il faut cliquer les 3 petits points
rouge-bleu-vert situés sur la barre des tâches. Vous verrez apparaître
un bandeau avec les différentes activités, il suffira de choisir celle
que vous voulez.
[![](http://localhost/spip/sites/default/IMG/distant/jpg/file-R502af5b9b5.jpg?1468442465){.mediacenter
width="500"
height="60"}](https://debian-facile.org/images/file-R502af57551a4ac9cc92cc302b6a6ca2c.png "/file-R502af57551a4ac9cc92cc302b6a6ca2c.png"){.media}
On pourra désactiver certaines en cliquant sur le carré rouge. On pourra
aussi en créer d'autre à chacun d'avoir de l'imagination.

</div>

Le Gestionnaire de fichiers Dolphin
-----------------------------------

<div>

**Dolphin** est le gestionnaire de fichiers de KDE4. *Un aperçu de
Dolphin*
[![](http://localhost/spip/sites/default/IMG/distant/png/file-Rab95153d52.png?1468442466){.mediacenter
width="500"
height="389"}](https://debian-facile.org/images/file-Rab9515c3c8e5a978d5e3ee2cef766361.png "/file-Rab9515c3c8e5a978d5e3ee2cef766361.png"){.media}
<div>

On peut noter en haut à droite, sous *Informations*, un aperçu du
fichier que l'on survole avec la souris.

</div>

-   <div>

    [Manuel de
    Dolphin](http://docs.kde.org/stable/fr/applications/dolphin/index.html "http://docs.kde.org/stable/fr/applications/dolphin/index.html"){.urlextern}

    </div>

Ce gestionnaire de fichier très complet et puissant peut s'enrichir de
nombreux modules. Par exemple un afficheur de vignette pour les fichiers
vidéos :

     apt-get install ffmpegthumbnailer ffmpegthumbs

Suffira ensuite d'activer dans le menu Configuration &gt; Configurer
Dolphin &gt; Général \[Aperçus\] &gt; Fichiers vidéo (ffmpegthumbs)

</div>

Le panneau de Configuration du système
--------------------------------------

<div>

C'est ici que vous allez pouvoir effectuer tous les réglages de votre
ordinateur et de votre système Debian. Réseau, son, vidéo, apparence des
fenêtres, langue par défaut mais aussi la façon dont vous voulez vous
connecter à votre session et j'en passe, on peut pratiquement tout
régler à partir d'ici. Il y a même des effets de bureaux, façon Compiz,
intégrés à KDE que l'on peut gérer ici.
[![](http://localhost/spip/sites/default/IMG/distant/jpg/file-R132dd26137.jpg?1468442467){.mediacenter
width="500"
height="461"}](https://debian-facile.org/images/file-R132dd28e5fd5a5c6dfa21f0359aaa677.png "/file-R132dd28e5fd5a5c6dfa21f0359aaa677.png"){.media}
<div>

Pour alléger KDE4 vous pouvez décocher l'outil d'indexation Strigi et le
bureau sémantique Nemopuk dans l'onglet *Recherche sur le bureau*. Mais
vous pouvez aussi décocher les effets de bureau (transparence des
fenêtres, par exemple).

</div>

</div>

Les applications KDE
--------------------

<div>

Les applications KDE sont des logiciels qui ont été conçus pour **tirer
pleinement parti de l'environnement de bureau de KDE**. Elles sont
prévues pour **interagir ensemble**. Telle action dans tel programme
ouvrira automatiquement un autre programme. Bien sûre vous n'êtes **pas
obligés d'installer que ces logiciels**. Des logiciels venant de Gnome,
Xfce ou autres pourront parfaitement fonctionner sous KDE. On peut voir
que **Iceweasel ou Icedove fonctionnent très bien**. Pourtant, ils ne
sont **pas spécifiques à KDE**. De même Libre-Office ou OpenOffice ne
sont pas des logiciels spécifique à KDE.
<div>

Pour que vos applications écrites en GTK aient un meilleur rendu et
semblent mieux intégrées dans KDE4, intaller les paquets:
***kde-config-gtk-style*** , ***gtk2-engines-oxygen*** et
***gtk3-engines-oxygen***.

</div>

-   <div>

    [kde-config-gtk-style, module de configuration de KDE pour la
    sélection du style GTK+
    2/3.x](http://packages.debian.org/kde-config-gtk-style "http://packages.debian.org/kde-config-gtk-style"){.urlextern}

    </div>

-   <div>

    [gtk2-engines-oxygen,thème Oxygen pour les applications basées sur
    GTK2+](http://packages.debian.org/gtk2-engines-oxygen "http://packages.debian.org/gtk2-engines-oxygen"){.urlextern}

    </div>

-   <div>

    [gtk3-engines-oxygen,thème Oxygen pour les applications basées sur
    GTK3+
    (Debian Wheezy)](http://packages.debian.org/gtk3-engines-oxygen "http://packages.debian.org/gtk3-engines-oxygen"){.urlextern}

    </div>

</div>

### Les application Multimedia

<div>

-   <div>

    Amarok: *Lecteur de Musique*.
    [Manuel](http://userbase.kde.org/Amarok/fr "http://userbase.kde.org/Amarok/fr"){.urlextern}

    </div>

-   <div>

    K3b: *Graveur de CD/DVD*.
    [Manuel](http://userbase.kde.org/K3b/fr "http://userbase.kde.org/K3b/fr"){.urlextern}

    </div>

-   <div>

    Dragonplayer: *Lecteur multimedia*.
    [Manuel](http://docs.kde.org/stable/fr/kdemultimedia/dragonplayer/index.html "http://docs.kde.org/stable/fr/kdemultimedia/dragonplayer/index.html"){.urlextern}

    </div>

-   <div>

    Kaffeine: *Lecteur multimedia*. [Manuel en
    anglais](http://userbase.kde.org/Kaffeine "http://userbase.kde.org/Kaffeine"){.urlextern}

    </div>

-   <div>

    Kdenlive: *Montage
    video*.[Manuel](http://userbase.kde.org/Kdenlive/fr "http://userbase.kde.org/Kdenlive/fr"){.urlextern}

    </div>

-   <div>

    Autres applications:
    [Multimedia](http://docs.kde.org/stable/fr/kdemultimedia/ "http://docs.kde.org/stable/fr/kdemultimedia/"){.urlextern}

    </div>

</div>

### Les appliquations Graphiques

<div>

-   <div>

    digikam: *Gestionnaire de photos*.
    [Manuel](http://userbase.kde.org/Digikam/fr "http://userbase.kde.org/Digikam/fr"){.urlextern}

    </div>

-   <div>

    Gwenview: *Visualiseur d’images*.
    [Manuel](http://docs.kde.org/stable/fr/kdegraphics/gwenview/index.html "http://docs.kde.org/stable/fr/kdegraphics/gwenview/index.html"){.urlextern}

    </div>

-   <div>

    Krita: *Retouche photo, édition d'images, application de dessin*.
    [Manuel](http://userbase.kde.org/Krita/fr "http://userbase.kde.org/Krita/fr"){.urlextern}

    </div>

-   <div>

    Okular: *Lire des fichiers
    PDF*.[Manuel](http://docs.kde.org/stable/fr/kdegraphics/okular/index.html "http://docs.kde.org/stable/fr/kdegraphics/okular/index.html"){.urlextern}

    </div>

-   <div>

    KSnapshot: *Capture d'écran*.
    [Manuel](http://docs.kde.org/stable/fr/kdegraphics/ksnapshot/index.html "http://docs.kde.org/stable/fr/kdegraphics/ksnapshot/index.html"){.urlextern}

    </div>

-   <div>

    Autres applications:
    [Graphiques](http://docs.kde.org/stable/fr/kdegraphics/ "http://docs.kde.org/stable/fr/kdegraphics/"){.urlextern}

    </div>

</div>

### Internet et communications

<div>

-   <div>

    Konqueror: *Navigateur internet*.
    [Manuel](http://docs.kde.org/stable/fr/kdebase-apps/konqueror/index.html "http://docs.kde.org/stable/fr/kdebase-apps/konqueror/index.html"){.urlextern}

    </div>

-   <div>

    Kmail: *Logiciel de messagerie*.
    [Manuel](http://userbase.kde.org/KMail/fr "http://userbase.kde.org/KMail/fr"){.urlextern}

    </div>

-   <div>

    Kopet: *logiciel de messagerie instantanée*.
    [Manuel](http://docs.kde.org/stable/fr/kdenetwork/kopete/index.html "http://docs.kde.org/stable/fr/kdenetwork/kopete/index.html"){.urlextern}

    </div>

-   <div>

    Ktorrent: *Client pair à pair utilisant le protocole Bitorrent*.

    </div>

-   <div>

    Autres applications:
    [Réseau](http://docs.kde.org/stable/fr/kdenetwork/ "http://docs.kde.org/stable/fr/kdenetwork/"){.urlextern}

    </div>

</div>

### Les applications Bureau

<div>

-   <div>

    Kontact: *Gestionnaire d'informations personnelles, contiend Kmail,
    Korganizer, KAddressBook, KNotes, KNodes et Akregator*.

    </div>

-   <div>

    Kword: *Traitement de texte*. [Manuel en
    anglais](http://userbase.kde.org/Kword "http://userbase.kde.org/Kword"){.urlextern}

    </div>

-   <div>

    Kpresenter: *Créer des présentations*.
    [Manuel](http://docs.kde.org/stable/fr/koffice/kpresenter/index.html "http://docs.kde.org/stable/fr/koffice/kpresenter/index.html"){.urlextern}

    </div>

-   <div>

    Kchart: *Visualiser les données numériques*.
    [Manuel](http://docs.kde.org/stable/fr/koffice/kchart/index.html "http://docs.kde.org/stable/fr/koffice/kchart/index.html"){.urlextern}

    </div>

-   <div>

    Autres applications:
    [Bureau](http://docs.kde.org/stable/fr/kdepim/ "http://docs.kde.org/stable/fr/kdepim/"){.urlextern},
    [Office](http://docs.kde.org/stable/fr/koffice/ "http://docs.kde.org/stable/fr/koffice/"){.urlextern}

    </div>

-   <div>

    </div>

</div>

### Utilitaires

<div>

-   <div>

    [Utilitaires](http://docs.kde.org/stable/fr/kdepim/ "http://docs.kde.org/stable/fr/kdepim/"){.urlextern}

    </div>

</div>

### Les applications Educative

<div>

-   <div>

    KBruch: *Calculs fractionnaire et pourcentages*.
    [Manuel](http://docs.kde.org/stable/fr/kdeedu/kbruch/index.html "http://docs.kde.org/stable/fr/kdeedu/kbruch/index.html"){.urlextern}

    </div>

-   <div>

    Kstars: *Simulation précise du ciel nocturne*.
    [Manuel](http://docs.kde.org/stable/fr/kdeedu/kstars/index.html "http://docs.kde.org/stable/fr/kdeedu/kstars/index.html"){.urlextern}

    </div>

-   <div>

    Marble: *Explorer la planète*.
    [Manuel](http://docs.kde.org/stable/fr/kdeedu/marble/index.html "http://docs.kde.org/stable/fr/kdeedu/marble/index.html"){.urlextern}

    </div>

-   <div>

    Autres applications:
    [kdeedu](http://docs.kde.org/stable/fr/kdeedu/ "http://docs.kde.org/stable/fr/kdeedu/"){.urlextern}

    </div>

</div>

### Les Jeux

<div>

-   <div>

    Voir ici:
    [Jeux](http://docs.kde.org/stable/fr/kdegames/ "http://docs.kde.org/stable/fr/kdegames/"){.urlextern}

    </div>

</div>

### Les applications Système

<div>

-   <div>

    Konsole: *Emulateur de Console*.
    [Manuel](http://userbase.kde.org/Konsole/fr "http://userbase.kde.org/Konsole/fr"){.urlextern}

    </div>

-   <div>

    KInfocenter: *Pour tout savoir sur son matèriel*. [Manuel en
    anglais](http://userbase.kde.org/KInfoCenter "http://userbase.kde.org/KInfoCenter"){.urlextern}

    </div>

-   <div>

    Kate: *l'éditeur texte avancé de KDE*.
    [Manuel](http://userbase.kde.org/Kate/fr "http://userbase.kde.org/Kate/fr"){.urlextern}

    </div>

-   <div>

    Kdevelop: *environnement de développement intégré (EDI) moderne pour
    le C++ (et d'autres languages)*.
    [Manuel](http://userbase.kde.org/Kdevelop4/Manual/Meet_KDevelop/fr "http://userbase.kde.org/Kdevelop4/Manual/Meet_KDevelop/fr"){.urlextern}

    </div>

</div>

Trucs et astuces
----------------

<div>

</div>

### Le menu aide

<div>

Si vous êtes perdu et que vous cherchez une fonction ou un moyen pour
configurer votre bureau mais aussi la manière dont on utilise telle ou
telle application, **Pensez au *menu Aide***.
[![](http://localhost/spip/sites/default/local/cache-vignettes/L418xH535/file-R781efdc776-b2b12.png){.mediacenter
width="418"
height="535"}](https://debian-facile.org/images/file-R781efde4102b7e8e38c218e1b45c2c03.png "/file-R781efde4102b7e8e38c218e1b45c2c03.png"){.media}

</div>

Connecter vos périphériques MTP
-------------------------------

<div>

De plus en plus de matériels nomades sont reconnus comme des
périphériques MTP (Tablettes Android - SmartPhones Android).
Malheureusement, ils ne seront pas vue automatiquement par Debian Wheezy
si vous les connectez à votre ordinateur. Sous KDE, il existe une
solution. Nous allons créer un paquet pour Debian
Wheezy.![8-O](http://localhost/spip/sites/default/local/cache-vignettes/L15xH15/icon_eekgif-adc8-31780.gif){.icon
width="15" height="15"} à partir des sources de SID (version unstable).
Mais non vous allez voir, il faut 5 minutes.
![:-D](http://localhost/spip/sites/default/local/cache-vignettes/L15xH15/icon_biggrin798e-13a59.gif){.icon
width="15" height="15"} Pour ce faire rendez vous ici:
<http://debian-facile.org/viewtopic.php?pid=65515#p65515> La
manipulation complète est présentée ici sur cette page du wiki:
<https://debian-facile.org/doc:mentors:retroportage> Vous suivez pas à
pas ce qui est expliqué en remplacent *Nom\_du\_paquet* par *kio-mtp*.
Voilà 5 minutes chrono , une déconnexion, une reconnexion à KDE et vous
branchez votre Tablette et ça marche, elle est reconnue.
![8-)](http://localhost/spip/sites/default/local/cache-vignettes/L15xH15/icon_coolgifc91c-c0a8c.gif){.icon
width="15" height="15"}
<div>

Depuis la version 8 (Jessie) il suffit d'installer le paquet disponible
dans les dépots:
[kio-mpt](https://packages.debian.org/jessie/kio-mtp "https://packages.debian.org/jessie/kio-mtp"){.urlextern}

</div>

     # apt-get install kio-mtp

</div>

Interagir avec les périphériques Androïd
----------------------------------------

<div>

Pour cela rendez vous sur cette page :
[kdeconnect](https://debian-facile.org/doc:reseau:kdeconnect "doc:reseau:kdeconnect"){.wikilink1}

</div>

Autres liens vers KDE4
----------------------

<div>

-   <div>

    [KDE4 sur Linuxpedia, très complémentaire de cette
    page](http://www.linuxpedia.fr/doku.php/kde/kde4 "http://www.linuxpedia.fr/doku.php/kde/kde4"){.urlextern}

    </div>

-   <div>

    http://www.siteduzero.com/news-62-20134-p1-kde4-le-petit-dernier-du-projet-kde.html -
    **Lien Obsolète**

    </div>

-   <div>

    <http://fr.wikipedia.org/wiki/KDE>

    </div>

-   <div>

    [Introduction à
    KDE](http://userbase.kde.org/An_introduction_to_KDE/fr "http://userbase.kde.org/An_introduction_to_KDE/fr"){.urlextern}

    </div>

-   <div>

    [Applications
    KDE](http://www.commentcamarche.net/faq/4789-kde-les-applications-kde "http://www.commentcamarche.net/faq/4789-kde-les-applications-kde"){.urlextern}

    </div>

-   <div>

    [Documentation
    KDE](http://docs.kde.org/index.php?language=fr&branch=stable "http://docs.kde.org/index.php?language=fr&branch=stable"){.urlextern}

    </div>

-   <div>

    [Liste d'applications
    KDE](http://fr.wikipedia.org/wiki/Liste_de_logiciels_KDE "http://fr.wikipedia.org/wiki/Liste_de_logiciels_KDE"){.urlextern}

    </div>

-   <div>

    [Plasma](http://userbase.kde.org/Plasma/fr "http://userbase.kde.org/Plasma/fr"){.urlextern}

    </div>

</div>
