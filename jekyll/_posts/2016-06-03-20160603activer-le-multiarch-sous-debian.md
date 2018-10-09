---
title: Activer le Multiarch sous debian
date: 2016-06-03 12:38
layout: post
---

Qu'est ce que Multi-arch ? {#Qu.27est_ce_que_Multi-arch_.3F}
==========================

<span id="line-8" class="anchor"></span><span id="line-9"
class="anchor"></span>

Multi-arch vous permet d'installer des bibliothèque de paquets venant de
différentes architectures sur un même système. C'est très utile dans
beaucoup de cas, cela permet le plus souvent d'installer à la fois des
logiciels 32 et 64 bits sur la même machine, tout en conservant une
résolution des dépendances automatique correcte. Notez que cela ne
permet pas d'installer simultanément plusieurs versions d'une même
« application » dans de multiples architectures. <span id="line-10"
class="anchor"></span><span id="line-11" class="anchor"></span>

Concepts {#Concepts}
========

<span id="line-12" class="anchor"></span><span id="line-13"
class="anchor"></span>

Il y a une architecture dite architecture courante, et affichée par la
commande `dpkg --print-architecture`. Elle est définie dans le paquet
dpkg actuellement installé. <span id="line-14"
class="anchor"></span><span id="line-15" class="anchor"></span>

(Notez qu'ici « architecture » désigne une Interface Binaire-Programme
(ABI, Application Binary Interface), et non une Architecture de Jeu
d'Instruction (ISA, Instruction Set Architecture). Ainsi, par exemple, «
armel » et « armhf » sont bien des « architectures » différentes car,
bien qu'elles utilisent (presque) le même jeu d'instruction, elles se
reposent sur des ABI différentes pour l'appel de fonctions depuis les
bibliothèques. <span id="line-16" class="anchor"></span><span
id="line-17" class="anchor"></span>

Il est maintenant possible de se référer à un paquet via
« paquet:architecture » à peu près partout où il était possible de le
faire avant avec « paquet » — nous avons donc libc:i386 et libc:amd64 —
malheureusement, les sémantiques comprises par dpkg et apt étant
légèrement différentes, les résultats obtenus via ces deux interfaces
peuvent être légèrement différents. Cependant, préciser l'architecture
d'un paquet devrait toujours être sûr et sans ambigüité, quant au nom
« paquet » sans précision, il se réfère au paquet dans l'architecture
courante d'apt. <span id="line-18" class="anchor"></span><span
id="line-19" class="anchor"></span>

Les autres architectures disponibles sont visibles grâce à la commande
`dpkg --print-foreign-architectures`. Dpkg gèrera les paquets de ces
architectures ainsi que ceux de l'architecture de la machine. <span
id="line-20" class="anchor"></span><span id="line-21"
class="anchor"></span>

Il y a un entête « Multi-Arch » inscrit dans les méta-données pour
chaque paquet multi-architectures concerné. <span id="line-22"
class="anchor"></span><span id="line-23" class="anchor"></span>

Les paquets existants fonctionnent très bien dans un environnement
multi-architectures, mais pour bénéficier d'une co-installation ou d'un
arbre de dépendances multi-architectures, beaucoup de paquets ont besoin
d'être rendus compatibles en multi-architectures. <span id="line-24"
class="anchor"></span><span id="line-25" class="anchor"></span>

-   Pour un paquet inchangé vous pouvez choisir quelle version
    d'architecture du paquet vous souhaitez installer (par exemple, «
    amd64 » ou « i386 »). <span id="line-26" class="anchor"></span><span
    id="line-27" class="anchor"></span>
-   Si un paquet est étiqueté « Multi-Arch: foreign », alors il peut
    satisfaire la dépendance d'un paquet d'une architecture différente
    (par exemple, « make:amd64 » permettra de satisfaire une dépendance
    faite pour un paquet de n'importe quelle architecture). <span
    id="line-28" class="anchor"></span><span id="line-29"
    class="anchor"></span>
-   Pour activer plus d'une version d'architecture d'un paquet en même
    temps (généralement les librairies et les paquets dev-) les fichiers
    ont besoin d'être déplacés pour ne pas avoir de conflit. Ces paquets
    sont eux aussi tagués « Multi-Arch: same ». <span id="line-30"
    class="anchor"></span><span id="line-31" class="anchor"></span>

Des paquets étiquetés « Multi-Arch : allowed » existent aussi. Ils
peuvent être traités à la fois comme « :same » ou comme « :foreign » en
fonction des paquets dont ils dépendent. <span id="line-32"
class="anchor"></span><span id="line-33" class="anchor"></span>

Le plus souvent, les responsables des paquets travaillent sur leur
distribution en commençant par installer les paquets les plus utiles
pour la rendre multi-architectures. Voir [multiarch
spec](https://wiki.ubuntu.com/MultiarchSpec "UbuntuWiki"){.interwiki} et
[howto implementation](https://wiki.debian.org/Multiarch/Implementation)
pour avoir des détails sur le fonctionnement actuel et pour savoir
comment mettre à jour les paquets et tirer avantage de cette
fonctionnalité. <span id="line-34" class="anchor"></span><span
id="line-35" class="anchor"></span>

<!--more-->

Prérequis {#Pr.2BAOk-requis}
---------

<span id="line-36" class="anchor"></span><span id="line-37"
class="anchor"></span>

Vous avez besoin d'un dpkg et d'un apt compatible multi-architectures.
<span id="line-38" class="anchor"></span><span id="line-39"
class="anchor"></span>

Pour dpkg de Debian cela est présent depuis la version 1.16.2. Dans
Ubuntu cela est possible depuis natty (v1.15.8.10ubuntu1). Vérifiez en
regardant si la commande `dpkg --print-foreign-architectures` est
comprise. <span id="line-40" class="anchor"></span><span id="line-41"
class="anchor"></span>

Apt est compatible multi-architectures s'il supporte
`-o APT::Architectures`. Cette prise en charge est disponible depuis la
version 0.8.13 comprise. Cependant, il y a eu de nombreuses
améliorations à la prise en charge de la multi-architecture et de
nombreuses corrections de bugs dans les versions suivantes de apt
(certaines requises par Debian dpkg 1.16.2 pour activer le
multi-architecture), comme la prise en charge de apt-get build-dep -a
cross-dependency. Par conséquent, le plus récent est le plus performant
en général, au moins jusqu'à la version 0.9.4. <span id="line-42"
class="anchor"></span><span id="line-43" class="anchor"></span>

Avant apt 0.9 dans Debian, dpkg peut ne pas fonctionner (mais seulement
si le multi-architecture est activé) pendant les mises à jour lorsqu'on
ne lui indique pas l'architecture du paquet qu'apt doit configurer.
(« dpkg: error: --configure needs a valid package name but
'gcc-4.7-base' is not: ambiguous package name 'gcc-4.7-base' with more
than one installed instance »). `dpkg --configure -a` devrait débloquer
cela. <span id="line-44" class="anchor"></span><span id="line-45"
class="anchor"></span>

Utilisation {#Utilisation}
===========

<span id="line-46" class="anchor"></span><span id="line-47"
class="anchor"></span>

Configurer les architectures {#Configurer_les_architectures}
----------------------------

<span id="line-48" class="anchor"></span><span id="line-49"
class="anchor"></span>

Pour ajouter une architecture supplémentaire (dans Debian depuis dpkg
1.16.2) : <span id="line-50" class="anchor"></span><span id="line-51"
class="anchor"></span><span id="line-52" class="anchor"></span>

    dpkg --add-architecture <arch>

<span id="line-53" class="anchor"></span>Par exemple : <span
id="line-54" class="anchor"></span><span id="line-55"
class="anchor"></span><span id="line-56" class="anchor"></span>

    dpkg --add-architecture armhf

<span id="line-57" class="anchor"></span><span id="line-58"
class="anchor"></span>

Notez que rien ne va réellement changer avant que vous fassiez <span
id="line-59" class="anchor"></span><span id="line-60"
class="anchor"></span><span id="line-61" class="anchor"></span>

    apt-get update

pour mettre à jour la liste des paquets disponibles.<span id="line-62"
class="anchor"></span><span id="line-63" class="anchor"></span>

Pour supprimer une architecture <span id="line-64"
class="anchor"></span><span id="line-65" class="anchor"></span><span
id="line-66" class="anchor"></span>

    dpkg --remove-architecture <arch>

<span id="line-67" class="anchor"></span><span id="line-68"
class="anchor"></span>

Les architectures disponibles pour dpkg sont stockées dans
`/var/lib/dpkg/arch`. <span id="line-69" class="anchor"></span><span
id="line-70" class="anchor"></span>

Notez qu'avant d'effacer une architecture, vous devez en effacer tous
les paquets correspondants : <span id="line-71"
class="anchor"></span><span id="line-72" class="anchor"></span>

    apt-get purge ".*:<arch>"

<span id="line-75" class="anchor"></span><span id="line-76"
class="anchor"></span>

Notez que le dpkg d'Ubuntu dans Natty (1.16.0\~ubuntu7 (reports
1.15.8.10)), Oneiric et Precise (1.16.1.2ubuntu7) utilise une syntaxe
différente : <span id="line-77" class="anchor"></span><span id="line-78"
class="anchor"></span><span id="line-79" class="anchor"></span>

    echo "foreign-architecture armhf" >> /etc/dpkg/dpkg.cfg.d/architectures

<span id="line-80" class="anchor"></span><span id="line-81"
class="anchor"></span>

Configurez les sources apt {#Configurez_les_sources_apt}
--------------------------

<span id="line-82" class="anchor"></span><span id="line-83"
class="anchor"></span>

Par défaut, apt utilise le jeu d'architectures remonté par dpkg, et
toutes architectures non qualifiées présentes dans les lignes du fichier
`/etc/apt/sources.list`, qui représente souvent ce que vous souhaitez.
Cela peut être modifié en utilisant APT::Architecture=&lt;arch&gt; pour
forcer l’architecture par défaut ou avec
APT::Architectures="&lt;arch&gt; &lt;arch&gt;". <span id="line-84"
class="anchor"></span><span id="line-85" class="anchor"></span>

    deb [arch=amd64,i386] http://uk.archive.ubuntu.com/ubuntu/ quantal main universe deb [arch=armel,armhf] http://ports.ubuntu.com/ubuntu-ports quantal main universe

<span id="line-89" class="anchor"></span><span id="line-90"
class="anchor"></span>

Identifier les lignes deb-src avec une architecture n'aurait aucun sens.
<span id="line-91" class="anchor"></span><span id="line-92"
class="anchor"></span>

Notez : Il y a un bug dans la version de apt &gt;=0.9.7 et &lt;0.9.7.2,
ce qui signifie que mettre « arch=armel,armhf » sur une seule ligne ne
fonctionne pas ; vous avez besoin de 2 entrées différentes. <span
id="line-93" class="anchor"></span><span id="line-94"
class="anchor"></span>

N'oubliez pas d'exécuter <span id="line-95" class="anchor"></span><span
id="line-96" class="anchor"></span><span id="line-97"
class="anchor"></span>

    apt-get update

<span id="line-98" class="anchor"></span>

après avoir ajouté une architecture. <span id="line-99"
class="anchor"></span><span id="line-100" class="anchor"></span>

Installer/désinstaller des paquets {#Installer.2Fd.2BAOk-sinstaller_des_paquets}
==================================

<span id="line-101" class="anchor"></span><span id="line-102"
class="anchor"></span>

Pour installer un paquet ne provenant pas de l'architecture par défaut,
spécifiez juste cette architecture dans la ligne de commande : <span
id="line-103" class="anchor"></span><span id="line-104"
class="anchor"></span><span id="line-105" class="anchor"></span>

    apt-get install package:architecture

<span id="line-106" class="anchor"></span><span id="line-107"
class="anchor"></span>

Les dépendances de ce paquet s'installeront automatiquement pour les
bonnes architectures (même architecture pour les bibliothèques,
architecture de la machine pour les autres dépendances) <span
id="line-108" class="anchor"></span>exemple : <span id="line-109"
class="anchor"></span><span id="line-110" class="anchor"></span><span
id="line-111" class="anchor"></span>

    apt-get install links:i386

<span id="line-112" class="anchor"></span>

    dpkg -i package_version_architecture.deb dpkg -r package:architecture

<span id="line-116" class="anchor"></span><span id="line-117"
class="anchor"></span>

Installation de l'arbre des dépendances croisées {#Installation_de_l.27arbre_des_d.2BAOk-pendances_crois.2BAOk-es}
------------------------------------------------

<span id="line-118" class="anchor"></span><span id="line-119"
class="anchor"></span>

Pour installer les dépendances à la construction d'un paquet avant une
compilation croisée <span id="line-120" class="anchor"></span><span
id="line-121" class="anchor"></span><span id="line-122"
class="anchor"></span>

    apt-get build-dep -a <arch> <package>

<span id="line-123" class="anchor"></span><span id="line-124"
class="anchor"></span>

Cela fonctionne lorsque tous les « outils » dont le paquet dépend sont
étiquetés `Multi-Arch: foreign`, que toutes les dépendances qui sont
nécessaires sur la machine de compilation, et que les paquets de
développement qui sont nécessaires à la fois sur l'architecture CIBLE et
sur l'architecture de COMPILATION sont coinstallable (« Multi-Arch: same
»), et que toutes les exceptions aux règles par défaut sont étiquetées
`package:any` ou `package:native` dans le paquet source. Ce processus
est indirect. <span id="line-125" class="anchor"></span><span
id="line-126" class="anchor"></span>

Lorsque cela ne fonctionne pas, vous pouvez souvent obtenir les
dépendances avec une commande manuelle de apt-get : <span id="line-127"
class="anchor"></span>Par exemple, à la place de <span id="line-128"
class="anchor"></span><span id="line-129" class="anchor"></span>

    apt-get build-dep -a armhf acl

, faites<span id="line-130" class="anchor"></span><span id="line-131"
class="anchor"></span><span id="line-132" class="anchor"></span>

    apt-get install autoconf automake debhelper gettext libtool libattr1-dev:armhf

<span id="line-133" class="anchor"></span><span id="line-134"
class="anchor"></span>

Les détails de la résolution des dépendances sont sur
[MultiarchCross](https://wiki.ubuntu.com/MultiarchCross "UbuntuWiki"){.interwiki}.
<span id="line-135" class="anchor"></span><span id="line-136"
class="anchor"></span>

Installer les bibliothèques de compatibilité Android SDK {#Installer_les_biblioth.2BAOg-ques_de_compatibilit.2BAOk_Android_SDK}
--------------------------------------------------------

<span id="line-137" class="anchor"></span><span id="line-138"
class="anchor"></span>

Certains utilisateurs utilisant le SDK Android pourraient rencontrer des
problèmes en essayant de lancer build-tools ou platform-tools sur une
plateforme amd64. Comme substitut pour `ia32-libs`, les utilisateurs
devraient s'en sortir en installant simplement les bibliothèques
suivantes : <span id="line-139" class="anchor"></span><span
id="line-140" class="anchor"></span>

    dpkg --add-architecture i386 apt-get update apt-get install libstdc++6:i386 libgcc1:i386 zlib1g:i386 libncurses5:i386

    Voir en ligne : Multiarch
