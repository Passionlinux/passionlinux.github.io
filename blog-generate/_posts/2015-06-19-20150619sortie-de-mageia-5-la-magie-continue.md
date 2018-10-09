---
title: Sortie de Mageia 5, la magie continue !
date: 2015-06-19 19:25
layout: post
---

Mageia est un système d’exploitation libre basé sur GNU/Linux, et porté
en tant que projet communautaire par l’association loi 1901
[Mageia.Org](https://www.mageia.org/fr/about/constitution/), cette
dernière étant constituée de contributeurs élus. Le cinquième tour de
Mageia est sortie le **vendredi 19 juin 2015**, proposant les dernières
évolutions techniques, de nouvelles versions des bureaux et logiciels,
tout en préservant la stabilité d’usage, et en conservant ses outils
spécifiques de contrôle du système. Chaque version de Mageia est
supportée 18 mois. Les mises à niveau entre versions sont supportées et
aisées. Mageia a démarré en septembre 2010 comme un [fork de Mandriva
Linux](https://linuxfr.org/news/mandriva-linux-et-apr%C3%A8s-mageia).
Elle a réuni des centaines de passionnés et plusieurs sociétés à travers
le monde, qui coproduisent l’infrastructure, la distribution Mageia
elle-même, sa documentation, sa diffusion et son assistance, à l’aide de
logiciels libres. Depuis son lancement, elle a publié quatre versions
majeures stables en [juin
2011](https://linuxfr.org/news/sortie-de-mageia-1), [mai
2012](https://linuxfr.org/news/la-magie-est-de-nouveau-la-mageia-2-est-disponible),
[mai 2013](https://linuxfr.org/news/sortie-de-mageia-3) et [février
2014](https://linuxfr.org/news/sortie-de-la-mageia-4). Mageia est et
reste référencée parmi les dix distributions les plus consultées sur
[Distrowatch](http://distrowatch.com/). ![logo
mageia](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569612e6f72672f672f6d656469612f6c6f676f2f6d61676569612d323031332e706e67/mageia-2013.png)  

Quoi de neuf ?
--------------

### Base du système

#### Architectures

Le code non utilisé gérant les architectures Alpha/IA64/PPC/SPARC a été
retiré. Mageia se concentre sur l’architecture Intel, en 64 bits, et
continue de fournir des compilations pour la version 32bits.  

#### BIOS & EFI, amorçage {#bios--efi-amorçage}

L’intégration de la gestion des BIOS EFI est opérationnelle via les
*media* Live64 ou DVD64. L’intégration a été semée d’embûches, retardant
la sortie de cette version. Grub2 (qui est optionnel) fonctionne mieux
maintenant, et détecte les autres systèmes d’exploitation afin de les
ajouter.  

#### Noyau Linux

Mageia 5 embarque le noyau Linux 3.19 qui dispose dans cette version du
support du DMA-BUF et de la gestion "fences" (nécessaire pour une bonne
prise en charge
d’[Optimus](http://fr.wikipedia.org/wiki/Optimus_%28NVIDIA%29) &
powerplay). Tout le matériel géré par ce noyau est fonctionnel et
utilisable, notamment côté portables Toshiba. De gros progrès ont été
reportés, ainsi que pour les écrans tactiles utilisant *atmel\_mxt\_ts*.
Les tablettes Wacom et les pavés tactiles Synaptics fonctionnent
maintenant mieux au cours de l’installation ([bogue
11524](https://bugs.mageia.org/show_bug.cgi?id=11524)).  

#### Nouveaux pilotes NVIDIA

NVIDIA a abandonné la prise en charge pour son pilote le plus récent de
la gamme suivante de puces : GeForce 8xxx, 9xxx et 100 à 415. En
conséquence, un nouveau paquet NVIDIA a été créé pour ces cartes,
maintenant appelé nvidia340. L’intégration pour ces cartes a été ajoutée
à drakx11/XFdrake permettant une détection automatique du pilote
approprié à votre matériel. De plus, si vous réalisez une mise à niveau,
la configuration X.Org sera automatiquement ajustée par le service
harddrake au premier démarrage.  

#### Partitions & systèmes de fichiers {#partitions--systèmes-de-fichiers}

Le partitionnement GPT est maintenant utilisé par défaut, au lieu du
disque complet LVM pour les disques supérieurs à 4 To. Btrfs est
désormais pris en charge comme système de fichiers (mais ext4 reste
celui par défaut). En le sélectionnant pour la partition `/boot` (ou `/`
sans partition boot séparée), Grub2 sera automatiquement sélectionné et
configuré.  

#### Système d’initialisation

Systemd est fourni dans sa version
[217](http://lists.freedesktop.org/archives/systemd-devel/2014-October/024662.html)
qui signe l’abandon des derniers outils sysvinit historiques.  

### RPM, URPM & Gestion de paquets {#rpm-urpm--gestion-de-paquets}

RPM a été mis à niveau en version
[4.12.0.1](http://rpm.org/wiki/Releases/4.12.0).  

#### Nouvelle gestion des suggestions

RPM apporte maintenant une prise en charge officielle des paquets
suggérés, qui diffère de la mise en œuvre précédente. Les paquets
utilisent dorénavant la nouvelle balise *Recommends* au lieu de
l’ancienne balise *Suggests*. Enfin, le format des fichiers de synthèse
dans les *media* a été légèrement modifié.  

#### Nouveau générateur de dépendances

Pendant quelques années, RPM a pris en charge deux façons de générer les
dépendances lors de la construction de paquets :

-   l’ancienne, dite générateurs *externes*
-   la nouvelle, dite générateurs *internes*

La plupart des distributions ont basculé sur les nouveaux générateurs
*internes*, mais Mageia utilisait toujours les anciens générateurs
*externes*. La version 5 se met à la page avec de nombreux avantages à
la clé comme :

-   La construction des paquets est plus rapide
-   La compatibilité des fichiers .spec avec les technologies Fedora
    (& Suse) s'en trouve améliorée
-   Les dépendances d’OCaml et d’autres technologies sont automatiques

Pour de plus amples explications, vous pouvez lire :

-   [RPM Dependency
    Generator](http://www.rpm.org/wiki/PackagerDocs/DependencyGenerator) ;
-   [A Tale of Three Dependency
    Generators](http://laiskiainen.org/blog/?p=35);
-   [RPM 4.9.0 Release Notes](http://rpm.org/wiki/Releases/4.9.0) .

Le nouveau comportement a aussi demandé une [modification du mécanisme
d’exclusion de
dépendances](http://fedoraproject.org/wiki/Packaging:AutoProvidesAndRequiresFiltering).  

#### Urpm

Une limite codée en dur, empêchant la mise à jour de mga4 vers mga5 en
raison de certains paquets ayant une liste longue de plus de 64 000
caractères, a été corrigée. Gurpmi va maintenant exécuter drakbug
lorsqu’il se bloque ou rencontre des erreurs de segmentation, afin
d’obtenir des rapports de bogue plus explicites. Les options urpmi
inhérentes aux dépendances ont été renommées (`--no-suggests` devient
`--no-recommends`) Les utilisateurs ont donc toujours à leur convenance
cette possibilité de n’installer que le strict minimum, la distribution
s’efforçant de réduire les dépendances nécessaires.  

### Traduction & Documentations {#traduction--documentations}

#### Localisation (l10n) / Internationalisation (i18n) {#localisation-l10n--internationalisation-i18n}

Firefox et Thunderbird ont été modifiés pour installer automatiquement
les bons paquets de langue `-l10n-xx` selon le paquet de langue installé
`locales-xx`. Si plusieurs paquets de langues `locales-xx` sont
installés, le bon paquet devrait être sélectionné suivant le langage
principal configuré pour le système. Le paquet `man-pages-de` pour
l’allemand a été corrigé : il contient maintenant plus de 530 pages de
manuel au lieu de 0 comme précédemment (Merci à Mario Blaettermann pour
le rapport et la correction de bogue).  

#### Documentation officielle

Tous les paquets `mageia-doc-installer-*` et `mageia-doc-mcc-*`
localisés ont été fignolés pour utiliser la capture d’écran
correspondante à la langue du système. Les textes d’aide en ligne pour
le programme d’installation traditionnel (non-Live) sont maintenant
disponibles dans plus de 20 langues. Les textes d’aide pour les boutons
d’aide dans le Centre de Contrôle Mageia `mageia-doc-mcc*` sont
maintenant disponibles en plus de 15 langues.  

### Bureaux & Environnements graphiques {#bureaux--environnements-graphiques}

L’assistant *MageiaWelcome* démarre automatiquement dans la langue de
l'utilisateur au lancement d’un bureau pour aider à configurer et à
utiliser Mageia permettant d’installer les dernières mises à jour, les
codecs audios/vidéos et plein d’autres bonnes choses…
![MageiaWelcome](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f6d616765696177656c636f6d65312e706e67/mageiawelcome1.png "Source : http://www.mageialinux-online.org/upload/mageiawelcome1.png")
![MageiaWelcome2](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f6d616765696177656c636f6d65322e706e67/mageiawelcome2.png "Source : http://www.mageialinux-online.org/upload/mageiawelcome2.png")
![MageiaWelcome3](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f6d616765696177656c636f6d65332e706e67/mageiawelcome3.png "Source : http://www.mageialinux-online.org/upload/mageiawelcome3.png")
![MageiaWelcome4](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f6d616765696177656c636f6d65342e706e67/mageiawelcome4.png "Source : http://www.mageialinux-online.org/upload/mageiawelcome4.png")
![MageiaWelcome5](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f6d616765696177656c636f6d65352e706e67/mageiawelcome5.png "Source : http://www.mageialinux-online.org/upload/mageiawelcome5.png")  

#### X Window System (X11)

Mageia 5 embarque X.Org 1.16.4  

#### KDE SC

KDE SC 4.14 est fourni.
![KDE](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f6b64655f64353866362e706e67/kde_d58f6.png "Source : http://www.mageialinux-online.org/upload/kde_d58f6.png")
KDE 4.14 est dédié à la mémoire de Volker Lanz. Il fournit une
apparence, un ressenti et des fonctionnalités familières avec la
stabilité solide comme le roc des dernières versions à support long
terme de l'environnement de bureau Plasma (4.11.12) et des applications
du dernier KDE SC (4.14). La couche KDE Telepathy offre des
fonctionnalités comme le chiffrement Off-the-Record (OTR) pour la
messagerie instantanée, la prise en charge de nombreux protocoles et un
jeu d'éléments graphiques pour l’environnement Plasma. Les applications
utilisant la couche multimédia sont maintenant basées sur la version 1.0
de GStreamer, permettant une réduction notable des dépendances. Mageia
accorde un soin particulier à ce bureau.  

#### KF5

Plasma 5.1 & KDE [Frameworks 5
(en)](https://www.kde.org/info/kde-frameworks-5.0.0.php) en version 5.5.
est également de la partie. Il est installable uniquement avec les
medias en ligne.  

#### GNOME

GNOME 3.14 est fourni. Voir [GNOME 3.14 rebat les
cartes](https://linuxfr.org/news/gnome-3-14-rebat-les-cartes) ![Mageia 5
GNOME
3.14](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f6d6761355f36346269745f676e6f6d652e706e67/mga5_64bit_gnome.png "Source : http://www.mageialinux-online.org/upload/mga5_64bit_gnome.png")
Nous utilisons maintenant le thème standard Adwaita au lieu de
Oxygen-gtk.  

#### LXDE

![lxde](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f6c7864652e706e67/lxde.png "Source : http://www.mageialinux-online.org/upload/lxde.png")
LXDE est disponible en version 0.99. Cet environnement peut être
installé à partir du DVD (installateur classique).  

#### XFCE

![xfce](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f786663652e706e67/xfce.png "Source : http://www.mageialinux-online.org/upload/xfce.png")
Cet environnement peut être installé dans sa dernière version 4.12.1 à
partir du DVD (installateur classique) ou du DVD double architecture.
[Xfce 4.12 est là !](https://linuxfr.org/news/xfce-4-12-est-la)  

#### LXQt (remplaçant RazorQt)

![lxqt](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f6c7871742e706e67/lxqt.png "Source : http://www.mageialinux-online.org/upload/lxqt.png")
LXQt en version 0.9.0 est le successeur de RazorQt. Il le remplace
pendant la mise à niveau depuis Mageia 4. Pour plus d’information,
vérifiez également
l’[Errata](https://wiki.mageia.org/en/Mageia_5_Errata#LXQt_.26_RazorQt).
Il est installable uniquement avec les *media* en ligne.  

#### Mate

![mate](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f6d6174652e706e67/mate.png "Source : http://www.mageialinux-online.org/upload/mate.png")
Cet environnement peut être installé en version 1.8 à partir du DVD
(installateur classique).  

#### Cinnamon

![cinnamon](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f63696e6e616d6f6e2e706e67/cinnamon.png "Source : http://www.mageialinux-online.org/upload/cinnamon.png")Cet
environnement peut être installé en version 2.4.5 à partir du DVD
(installateur classique).  

#### Enlightenment

![Enlightenment](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f656e6c69676874656e6d656e742e706e67/enlightenment.png "Source : http://www.mageialinux-online.org/upload/enlightenment.png")
Cet environnement est livré dans sa version E18 basée sur les
bibliothèques Enlightenment Foundation.  

#### Gestionnaires légers de fenêtres

Mageia 5 fournit aussi une multitude de gestionnaires de fenêtres petits
et efficaces comme : afterstep, awesome, dwm, fluxbox, fvwm2,
fvwm-crystal, i3, icewm, jwm, lightdm, matchbox, openbox, pekwm, sugar,
swm, ou windowmaker.  

#### Applications bureautiques

-   LibreOffice a été mis à jour en [version
    4.4](https://wiki.documentfoundation.org/ReleaseNotes/4.4/fr)
-   Calligra en 2.8.7
-   Abiword en 3.0.0
-   Gnumeric en 1.12.20

#### Navigateur internet & apps web {#navigateur-internet--apps-web}

Firefox et Thunderbird sont dans leurs dernières versions ESR. ![Firefox
31.6
ESR](https://img.linuxfr.org/img/687474703a2f2f7777772e6d61676569616c696e75782d6f6e6c696e652e6f72672f75706c6f61642f636170747572655f64755f323031355f30365f32315f30315f35375f30302e706e67/capture_du_2015_06_21_01_57_00.png "Source : http://www.mageialinux-online.org/upload/capture_du_2015_06_21_01_57_00.png")
Dans les dépôts on trouve facilement chaussure à son pied :
[Transmission](http://fr.wikipedia.org/wiki/Transmission_%28logiciel%29),
[Deluge](http://fr.wikipedia.org/wiki/Deluge_%28logiciel%29),
[qBittorrent](http://fr.wikipedia.org/wiki/QBittorrent),
[KTorrent](http://fr.wikipedia.org/wiki/KTorrent)…

-   Les identifiants d’utilisateurs sont maintenant créés avec un UID à
    partir de 1000 au lieu de 500 auparavant, puisque c’est le choix de
    la majorité des nouvelles distributions ;
-   [Handbrake](https://handbrake.fr/features.php), un convertisseur
    vidéo libre, a finalement été ajouté à nouveau dans Mageia. C’est
    maintenant possible car il n’inclut plus les encodeurs faac
    et fdk-aac. Il prend en charge l’encodage x265 ;
-   Le convertisseur vidéo [Transmageddon](http://www.linuxrising.org/)
    prend en charge l’[accélération matérielle
    VAAPI](http://fr.wikipedia.org%C2%A0;/wiki/Video_Acceleration_API).
-   [Phototonic](http://oferkv.github.io/phototonic/) un lecteur et
    organiseur d’images, rapide, léger et à l'aspect Qt/C++ a
    été ajouté.
-   freshplayerplugin a été ajouté - c’est une surcouche qui permet à
    Firefox d’utiliser la dernière extension du lecteur flash
    pepperflash, à télécharger manuellement car elle vient seulement
    avec Google Chrome et Mageia ne peut pas l’embarquer par défaut.
    Pour plus de détails voir [ce sujet de
    forum](https://forums.mageia.org/en/viewtopic.php?f=41&t=8568) (en
    anglais), qui offre un script qui télécharge automatiquement la
    dernière version de l’extension pepperflash (c’est nécessaire
    seulement si vous utilisez Firefox sans installer Google Chrome) ;
-   Le paquet mailcap a été complétement mis à jour et synchronisé avec
    Fedora ;
-   Radio amateur - Les ajouts à la sélection de logiciels radio dans
    cette version sont :
    [xdx](http://sourceforge.net/projects/xdxclusterclient/),
    [freedv](http://freedv.org/tiki-index.php),
    [chirp](http://chirp.danplanet.com/projects/chirp/wiki/Home) et
    [splat](http://www.qsl.net/kd2bd/splat.html) ;
-   SDR [gqrx](http://gqrx.dk/) a été ajouté pour compléter [Gnu
    Radio](http://fr.wikipedia.org/wiki/GNU_Radio) et offre un accès
    facile au monde des logiciels Radio. Prise en charge incluse d’une
    vaste gamme de matériels SDR ;
-   Grâce à Juan Luis Baptiste, les images officielles de docker pour
    Mageia 3 et 4 sont maintenant disponibles sur le site officiel
    de docker. Pour plus de détails voir [ce
    poste](https://ml.mageia.org/wwsympa-wrapper.fcgi/arc/dev/2014-10/msg00196.html)
    sur la liste de diffusion des développeurs Mageia. Docker et Docker
    Registry sont aussi empaquetés pour Mageia 5, ce qui vous permet
    d’utiliser et de gérer vos conteneurs.

### Paquets obsolètes

-   postgresql9.0, postgresql9.1 et postgresql9.2 ont été abandonnés ;
    Mageia 5 fournit postgresql9.3 et postgresql9.4. Si vous utilisez
    l’un des anciens paquets sur Mageia 4, assurez-vous de sauvegarder
    vos bases de données avant la mise à niveau, de sorte que vous
    puissiez les restaurer une fois votre système à jour ;
-   Les paquets gwibber et couchdb ont été abandonnés, ils n’étaient pas
    maintenus et inutilisables. le [service
    GNOME](https://blogs.gnome.org/kenvandine/) peut être un bon
    remplacement pour gwibber ;
-   Openstack a été abandonné car il n’était pas maintenu et contenait
    de nombreux problèmes de sécurité non résolus ;
-   ruby-rails a été abandonné car il n’était pas maintenu ;
-   wings3d a été abandonné car il ne fonctionne pas sous Mageia 5 et
    les paquets Erlang nécessaires sont manquants ;
-   zarafa a été abandonné par manque de retour sur les problèmes de
    sécurité ([Voir bug
    14993](https://bugs.mageia.org/show_bug.cgi?id=14993)) ;
-   Les bibliothèques C standard inutilisées ont été abandonnées : musl,
    klibc, uClibc (uniquement glibc & dietlibc sont
    maintenant fournies).

### Problèmes connus et rapports de bogues

Vous pouvez utiliser [notre bugzilla](https://bugs.mageia.org/), mais
s’il vous plaît, consultez les
[Errata](https://wiki.mageia.org/en/Mageia_5_Errata) avant de signaler
un bug. Si vous n’avez pas encore de compte Mageia, vous pouvez en créer
un à l'adresse <https://identity.mageia.org/>. Si vous ne savez pas
comment rapporter un bogue, [consultez le guide
(en)](https://wiki.mageia.org/en/Bugzilla#How-to_report_a_bug%7C).  

Valeurs sûres & Stabilité {#valeurs-sûres--stabilité}
-------------------------

### Dépôts en ligne de Mageia

Les paquets de Mageia sont répartis dans trois dépôts/*media* suivant la
licence. Le dépôt **Core** (cœur) est constitué des paquets essentiels
ou spécifique à la distribution et de tous les logiciels entièrement
libres qu’elle propose. L’ensemble des *media* *Core* est **actif** par
défaut. Le dépôt **NonFree** (non-libre) comprend des paquets qui sont
gratuits et redistribuables, mais à sources fermées (pilotes
propriétaires des cartes graphiques NVIDIA et AMD/ATI, des
micrologiciels pour certaines cartes wi-fi, etc). L’ensemble des *media*
*nonfree* (*nonfree release* et *nonfree updates*) est configuré mais
**désactivé** par défaut. Le dépôt **Tainted** (contaminé, entaché)
comprend les paquets sous différentes licences, libres et non libres. Le
principal critère est une infraction possible aux brevets et droits
d’auteur (copyright) dans certains pays (par exemple les codecs
multimédia nécessaires pour lire des fichiers audio/vidéo de différents
layouts, les paquets nécessaires pour lire les DVD vidéo du commerce…)  ;
l’ensemble des *media* *tainted* est configuré, mais **désactivé** par
défaut, c’est-à-dire qu’il est à consentement préalable, donc vérifiez
vos lois locales avant de redistribuer les paquets provenant de
*tainted* (mais tout utilisateur peut les installer). Ce dépôt est à
Mageia, ce que le dépôt RPM Fusion est à Fedora. *Sur un système 64bits,
le dépôt 32bits est aussi ajouté. Si les dépôts nonfree et/ou tainted
64bits sont activés, les dépôts 32bits correspondants seront activés
automatiquement (ils peuvent être nécessaires pour des paquets comme
Skype©, par exemple)*  

### Centre de Contrôle Mageia

Le Centre de Contrôle Mageia (MCC ou drakconf) facilite la gestion et la
configuration du matériel, du système et des services. Ce centre de
contrôle est disponible au travers d’une interface centrale regroupant
tout les modules, mais aussi sous formes de modules indépendants, et
enfin en interface pour terminal. ![Le Centre de Contrôle en mode
semi-graphique
(console).](https://img.linuxfr.org/img/687474703a2f2f617263686976652e6f70656e6d616e64726976612e6f72672f77696b692f66722f696d616765732f632f63352f43656e7472655f64655f636f6e74722543332542346c655f4d616e64726976615f74657874652e706e67/Centre_de_contr%C3%B4le_Mandriva_texte.png "Source : http://archive.openmandriva.org/wiki/fr/images/c/c5/Centre_de_contr%C3%B4le_Mandriva_texte.png")  

#### Utilisation

Il permet de configurer une grande partie de son système Mageia, de
manière simple et conviviale. Il est composé de plusieurs modules
organisés en onglets. Tous les modules peuvent aussi être lancés de
manière autonome, sans nécessairement passer par le centre de contrôle
Mageia, pourvu que l’entrée de menu existe pour ce module, ou que l’on
connaisse la commande à taper dans une console. Le Centre de Contrôle
agit sur le cœur du système et les changements peuvent avoir un effet
pour tous les utilisateurs de la machine. C’est pourquoi il nécessite
les droits administrateurs (ou droits root) et demande donc le mot de
passe de l’utilisateur root si nécessaire (c’est-à-dire si l’on est pas
root).  

#### Gestion des logiciels

Drakrpm (ou rpmdrake) est l’interface graphique de gestion des paquets
logiciels, permettant la gestion des canaux, l’installation, la mise à
jour, la désinstallation, la consultation des descriptions et la
recherche. Pour en savoir plus, voir la documentation de
[rpmdrake](https://doc.mageia.org/mcc/3/fr/content/rpmdrake.html).  

#### Utilisation de Drakrpm

Ce gestionnaire de logiciel est un des principaux outils de Mageia. Il
vous permet d’installer les logiciels sous forme de paquets, de les
mettre à jour, et de les désinstaller à votre gré. Tous les paquets sont
rangés par catégorie dans la barre latérale à gauche. À chaque
démarrage, le gestionnaire met à jour la liste des paquets disponibles
(appelés *media*) à partir des serveurs de Mageia. Un système de filtres
vous permet de n’afficher que certains paquets : soit vous n’affichez
que les applications (par défaut), soit vous n’affichez que des mises à
jour disponibles. Vous pouvez également afficher uniquement les paquets
installés ou qui ne le sont pas, y compris pendant une recherche. Vous
pouvez également rechercher soit par nom de paquet, soit dans les
résumés de descriptions, soit dans les descriptions complètes des
paquets, soit dans les noms de fichiers inclus dans les paquets.
![rpmdrake1](https://img.linuxfr.org/img/68747470733a2f2f646f632e6d61676569612e6f72672f6d63632f332f66722f636f6e74656e742f696d616765732f72706d6472616b65312e706e67/rpmdrake1.png "Source : https://doc.mageia.org/mcc/3/fr/content/images/rpmdrake1.png")
Cet outil se trouve dans le Centre de Contrôle de Mageia, onglet
« Gestion des logiciels », icône « Installer et désinstaller des
logiciels ».

1.  Filtre de layout de paquet : Il vous permet de n’afficher que certains
    layouts de paquets. Au premier démarrage il n’affiche que
    les applications. Vous pouvez afficher soit tous les paquets avec
    les dépendances et les librairies, soit uniquement des groupes de
    paquets, soit les applications seulement, soit les mises à jour
    seulement, soit des paquets rétro-portés de versions supérieures de
    Mageia Linux ;
2.  Filtre d’état de paquet : Ce filtre vous permet soit de n’afficher
    que les paquets installés, soit les paquets qui ne sont pas
    installés seulement, soit tous les paquets qu’ils soient installés
    ou non ;
3.  Mode de recherche : Cliquez sur la loupe pour rechercher parmi : les
    noms des paquets, leurs résumés, leurs descriptions complètes ou les
    fichiers inclus dans tous les paquets ;
4.  Champ de recherche : Entrez dans ce champ un ou plusieurs mots clés.
    Si vous souhaitez utiliser plus d’un mot clé, utilisez un '|' entre
    les mots clés. Par exemple, si vous recherchez mplayer et xine en
    même temps, tapez mplayer | xine ;
5.  Effacer : Ce bouton vous permet d’effacer d’un clic tout mot clé
    rentré dans le champ de recherche ;
6.  Liste des catégories : Ce panneau latéral regroupe toutes les
    catégories et sous catégories des logiciels disponibles ;
7.  Panneau de description : Ce panneau affiche le nom du paquet, son
    résumé et sa description complète. Il fourni de nombreuses
    informations sur l’élément sélectionné. Il permet également
    d’afficher des détails précis sur le paquet, les fichiers contenus
    dans le paquet, ainsi qu’un historique des derniers changement
    effectués par le mainteneur du paquet.

Une fois les filtres correctement paramétrés, le paquet peut être trouvé
par catégorie (dans la zone 6 ci-dessus) ou par nom/résumé/description
(dans la zone 4). Une liste de paquets répondant à la requête et, ne
l’oubliez pas, aux media choisis est affichée avec les indicateurs de
statut précisant si le paquet est installé/pas installé/une mise à jour…
Pour changer ce statut, cocher ou décocher la case devant le nom du
paquet et cliquer sur `Appliquer`.  

#### Maintenir à jour

Pour mettre à jour, on utilise le module **drakrpm-update**. Il peut se
lancer depuis le Centre de Contrôle ou en console en tapant
drakrpm-update ou
[MageiaUpdate](https://doc.mageia.org/mcc/3/fr/content/MageiaUpdate.html).
Il permet de mettre à jour l’ensemble des applications et paquets
installés, et installe donc les paquets les plus récents disponibles
parmi les *media* configurés.
![MageiaUpdate](https://img.linuxfr.org/img/68747470733a2f2f646f632e6d61676569612e6f72672f6d63632f332f66722f636f6e74656e742f696d616765732f4d61676569615570646174652e706e67/MageiaUpdate.png "Source : https://doc.mageia.org/mcc/3/fr/content/images/MageiaUpdate.png")
**Matériel**
![mcc-hardware](https://img.linuxfr.org/img/68747470733a2f2f646f632e6d61676569612e6f72672f6d63632f332f66722f636f6e74656e742f696d616765732f6d63632d68617264776172652e706e67/mcc-hardware.png "Source : https://doc.mageia.org/mcc/3/fr/content/images/mcc-hardware.png")
**Réseau et Internet**
![mcc-network](https://img.linuxfr.org/img/68747470733a2f2f646f632e6d61676569612e6f72672f6d63632f332f66722f636f6e74656e742f696d616765732f6d63632d6e6574776f726b2e706e67/mcc-network.png "Source : https://doc.mageia.org/mcc/3/fr/content/images/mcc-network.png")
**Système**
![mcc-system](https://img.linuxfr.org/img/68747470733a2f2f646f632e6d61676569612e6f72672f6d63632f332f66722f636f6e74656e742f696d616765732f6d63632d73797374656d2e706e67/mcc-system.png "Source : https://doc.mageia.org/mcc/3/fr/content/images/mcc-system.png")
**Partages réseau**
![mcc-network-sharing](https://img.linuxfr.org/img/68747470733a2f2f646f632e6d61676569612e6f72672f6d63632f332f66722f636f6e74656e742f696d616765732f6d63632d6e6574776f726b2d73686172696e672e706e67/mcc-network-sharing.png "Source : https://doc.mageia.org/mcc/3/fr/content/images/mcc-network-sharing.png")
**Disques locaux**
![mcc-localdisks](https://img.linuxfr.org/img/68747470733a2f2f646f632e6d61676569612e6f72672f6d63632f332f66722f636f6e74656e742f696d616765732f6d63632d6c6f63616c6469736b732e706e67/mcc-localdisks.png "Source : https://doc.mageia.org/mcc/3/fr/content/images/mcc-localdisks.png")
**Sécurité**
![mcc-security](https://img.linuxfr.org/img/68747470733a2f2f646f632e6d61676569612e6f72672f6d63632f332f66722f636f6e74656e742f696d616765732f6d63632d73656375726974792e706e67/mcc-security.png "Source : https://doc.mageia.org/mcc/3/fr/content/images/mcc-security.png")
**Démarrage**
![mcc-boot](https://img.linuxfr.org/img/68747470733a2f2f646f632e6d61676569612e6f72672f6d63632f332f66722f636f6e74656e742f696d616765732f6d63632d626f6f742e706e67/mcc-boot.png "Source : https://doc.mageia.org/mcc/3/fr/content/images/mcc-boot.png")  

Installation
------------

### *Media* d’installation

Trois layouts de *media* sont disponibles : DVD 32 bits, DVD 64 bits, DVD
DualArch. Ce dernier contient un choix précis et restreint de paquets,
proposant ses bibliothèques en 32 & 64 bits, et ayant comme bureau Xfce.
Ces *media* sont gravables sur support optique ou copiables sur un
disque USB. Ils proposent le lancement du système d’installation complet
et classique, en interface graphique ou en interface ncurses. Cet
installateur prend aussi en charge les recettes
[Autoinstall](http://members.shaw.ca/mandrake/drakx/HTML/index.html),
permet une installation en mode *oem* personnalisé, est capable de
réaliser une installation en mode braille, ou encore d’utiliser une
ligne série.  

### *Media* Live

Les *media* *Live* sont déclinés en huit variantes suivant la taille (CD
et DVD), l’architecture matérielle (32 et 64 bits) et l’environnement de
bureau (KDE et Gnome). Ils permettent tous l’installation simplifiée.  

### Installation par le réseau filaire

Quatre mini *media* (entre 30 & 80 Mo, 32 ou 64 bits, avec ou sans
firmwares non libres) sont préparés pour ceux qui préfèrent une
installation réseau (filaire). Ils permettent donc l’installation par
internet ou depuis votre réseau, ce dernier pouvant comprendre
simplement un fichier iso monté et partagé ou votre propre serveur
d’installation. Ils supportent également les recettes *AutoInstall*.  

Mise à niveau depuis Mageia 4
-----------------------------

La mise à niveau d’une Mageia version 4 vers une version 5 est supportée
de plusieurs manières. Avant de mettre à niveau :

-   S'assurer vous que Mageia 4 soit parfaitement à jour ;
-   Prendre connaissance de la page des [problèmes
    connus](https://wiki.mageia.org/fr/Mageia_5_Errata#Probl.C3.A8mes_de_Mise_.C3.A0_Niveau%7C)
    et sauvegarder les données importantes peut être utile. Si des
    dépôts tiers, tels que ceux de Google, ont été ajoutés lors de
    l’utilisation de Mageia 4, inclure `/etc/urpmi/urpmi.cfg` dans les
    « données importantes ». Le contenu de ce fichier peut ensuite être
    utilisé pour ajouter à nouveau les dépôts tiers, après la mise
    à niveau.

*La mise à niveau de Mageia 4 vers Mageia 5 n’est pas possible depuis
les media live, ces derniers copiant simplement leur contenu sur le
disque*.  

### Avec les *media* CD & DVD {#avec-les-media-cd--dvd}

Vous pouvez utiliser le DVD de Mageia 5 pour faire une installation mais
aussi pour faire une mise à niveau de la version précédente. Pour mettre
à niveau :

-   Téléchargez l’image ISO depuis la [page de
    téléchargement](http://mageia.org/fr/downloads/) de Mageia et
    gravez-la sur un DVD, ou installez-la sur une clé USB ; pour plus de
    détails sur ce point, jetez un œil à [*media* d’installation
    disponibles](https://wiki.mageia.org/en/Installation_Media) ;
-   Démarrez sur le DVD et sélectionnez « Installer Mageia 5 » depuis le
    chargeur de démarrage dans le menu ;
-   Sélectionnez l’option de [Mise à
    jour](http://doc.mageia.org/installer/5/fr/content/selectInstallClass.html)
    dans l’installeur (programme d'installation).

### Avec Internet

### En graphique

L’applet de notification des mises à jour vous notifiera qu’une nouvelle
version de Mageia est disponible et vous demandera si vous souhaitez
faire la mise à niveau. Si vous acceptez, la mise à niveau se déroulera
sans autre intervention. Si vous avez désactivé l’applet, ou si elle ne
tourne plus de manière automatique pour une raison quelconque, vous
pouvez lancer la mise à niveau soit par l’interface graphique
(**mgaonline**), soit en ligne de commande (via `urpmi`). Les deux
méthodes sont détaillées ci-après.  

### En ligne de commande

Vous pouvez aussi faire la mise à niveau en utilisant urpmi à partir de
votre émulateur de terminal.

-   Supprimer toutes les sources existantes des *media* sur votre
    système en exécutant cette commande en tant qu’utilisateur root dans
    un terminal : ` su urpmi.removemedia -a `
-   Ajouter les sources en ligne de Mageia 5, soit ;
-   En utilisant la méthode de LA LISTE DES MIROIRS (qui sélectionnera
    automatiquement un miroir en fonction de votre situation
    géographique) :
    ` su urpmi.addmedia --distrib --mirrorlist 'http://mirrors.mageia.org/api/mageia.5.$ARCH.list' `

(la variable \$ARCH est soit i586 ou x86\_64)

-   Ou utiliser un miroir de *media* spécifique : su urpmi.addmedia
    --distrib Vous pouvez récupérer la variable `mirror_url` en
    utilisant [l’application web des miroirs
    Mageia](http://mirrors.mageia.org/distrib)
-   Pour finir, commencer la mise à niveau :
    ` su urpmi --replacefiles --auto-update --auto `
-   Il est préférable d’exécuter la commande ci-dessus une seconde fois,
    afin de s'assurer que tout les paquets ont bien été mis à jour.

Pour plus d’informations, consultez le [manuel
d'installation](https://doc.mageia.org/installer/4/fr/content/index.html).  

Mageia c’est vous !!
--------------------

Mageia est régie par un [code de
conduite](https://www.mageia.org/fr/about/code-of-conduct/) permettant
de coopérer efficacement dans une atmosphère positive. Elle est
organisée en équipes (traducteurs, développeurs, packageurs, testeurs
\[QA\], communicants, etc.) qu’il est facile de rejoindre grâce à un
système d’accompagnement des nouveaux contributeurs. Mais même en dehors
de toute équipe, utiliser Mageia, en parler autour de soi, remonter les
problèmes éventuels ou encore donner à l’association sont autant de
manières de contribuer. Quelles que soient vos compétences, rendez-vous
sur le site de la distribution pour [contribuer à
Mageia](http://www.mageia.org/fr/contribute/) et intégrer la
communauté !
