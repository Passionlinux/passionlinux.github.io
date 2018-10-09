---
title: Construire des paquets DEB pour Debian (première partie)
date: 2018-04-20T21:02:56+02:00
layout: post
---

*(Édition: je décide de couper en plusieurs billets).*

Cela fait un moment que ça me trotte, l'envie de refaire les billets sur la fabrication de paquets DEB et RPM, et c'est en voyant le billet de Microlinux sur comment [Construire des paquets RPM pour CentOS](https://blog.microlinux.fr/rpm-build/) que le courage m'est revenue.

Je ne parlerais pas de construction depuis zéro mais depuis des paquets venant de Debian SID (qu'on appel rétro-portage) et d'Ubuntu sur un système Debian stable. Toutes les étapes citées ici seront reproductibles sur toutes distributions issues de la famille Debian, aussi bien sur Ubuntu que sur Mint, c'est la grande force de ce format de paquet. L’inconvénient est qu'il est moins facile de partir de zero que le format RPM pour faire son propre paquet, sous DEB nous avons un dossier contenant une multitude de fichier alors que le RPM n'a qu'un seul fichier obligatoire, par contre sous Debian, la création du dossier et des fichiers sont grandement facilité par des automatismes (`dh_make`).

![debvsrpm](https://download.tuxfamily.org/passionlinux/distributions_linux/debvsrpm.png)

Un mot tout d'abord, pourquoi j'aime les DEB à ce point, c'est simple: contrairement aux RPM, peu importe l'origine du paquet -j'entends par origine, la distribution DEB que ce soit un paquet venant de Mint, d'Ubuntu, de Debian, ect...- il sera toujours possible de le rétro-porter ou de le porter sur sa distribution, sans changer quoique ce soit. Par exemple il m'arrive souvent de prendre une version d'Ubuntu d'un paquet pour le rebuilder sur ma Debian, et un exemple qui me vient en tête est simplement Ubuntu qui utilise l'intégrale de l'archive Debian rebuilder pour elle. Là où les distributions RPM sont souvent peu ou pas compatible et où il faut retoucher les fichiers.spec pour arriver à ses fins. Par exemple, un spec venant de Fedora sera souvent retouché pour fabriquer un paquet sous openSUSE, on pourra s'en inspirer mais pas le copier à l'identique, faudra déjà mettre les bons noms des dépendances de build, mais aussi souvent changer la partie %build ou %install du spec. Il y a bien sur l'exception qui confirme la règle, des spec qui sont compatibles quelque soit la distribution et encore si les noms de dépendances correspondent. Bien sur la famille RedHat est totalement un contre exemple puisque Fedora est 100 compatible avec les autres distributions du groupe, comme l'est Tumbleweed vis à vis de Leap ou de SLE coté de la famille SUSE, mais un spec Rosa sera peu ou pas compatible avec une SUSE, une RedHat, voir même une Mageia...

Maintenant que j'ai dis ça, allons voir de quoi il en retourne. Il n'y a pas de paquets sources proprement parlé sous Debian, comme on peut s'attendre à trouver à la manière de RPM, non, un paquet source Debian n'est pas un truc appelé *"mon-programme.deb.source"* mais plutôt un ensemble de 2 archives compressées et d'un fichier:

- une archive nommée *"nom-du-programme_numéro.de.version.orig.tar.gz"* qui contient les sources originales du logiciel et non modifiés/altérés par l'opération d'empaquetage Debian (c'est comme pour RPM et l'archive des sources compressés),
- une archive compressée nommé *"nom-du-programme_numéro.de.version-release.debian.tar.xz"* qui contient l'arbre des sources Debian, la façon de transformer les sources en paquet Debian comme le ferait un fichier spec,
- un fichier *"nom-du-programme_numéro.de.version-release.dsc"* (DSC: Debian Source Control) qui décrit le paquet source aux outils de gestion de paquets, donne également le contenu du paquet source. Ce fichier est normalement signé en clair par la clé du mainteneur (Debian, Ubuntu,..).

Je partirais sur un paquet n'existant pas chez Debian mais qui est sur Ubuntu, je prendrais une version qui ne sera pas la dernière pour vous montrer la puissance des outils Debian pour mettre à jour les sources et rebuilder en directe et enfin un autre programme qui sera accessible depuis SID dans une version plus récente que sous Stable. Toutes les actions citées qui suivent seront fait avec les outils de Debian utilisés par les Devs mais sont possible d’être fait avec des outils universaux comme wget, ect... Je reprends un peu l'architecture du billet de Microlinux pour mon billet, comme pour donner une idée des étapes à suivre et comparer avec les RPM.

## Mettre en place l’environnement de construction ##

Plusieurs outils et méthodes sont possibles, je n'aborderais que la plus simple et pourtant la plus puissante, celle des développeurs Debian: les outils **devscripts**. On commence donc par les installer:

    # apt install devscripts
    
Il nous faudra pour la suite, avoir configuré sa clé pour signer ses paquets, je ne parlerais pas de ça ici, mais on peut se documenter et suivre l'excellent tuto de Debian-facile sur la question:

https://debian-facile.org/doc:mentors:signer-un-paquet

Sinon il reste la possibilité de ne pas signer les paquets au moment de lancer debuild avec l'option `-uc`.

On va se faire un endroit propre dans notre /home pour la construction:

    $ mkdir /home/nom-de-l'utilisateur/paquets && cd /home/nom-de-l'utilisateur/paquets
    
On peut nommer le dossier comme il nous chante, remplacer *paquet* ci-dessus par ce que vous voulez, pareil pour l'emplacement.

## Téléchargement des sources depuis une distribution autres que Debian (Ubuntu) et construction d’un paquet DEB pour sa Debian stable##

Comme dit au début du billet, je commence par un paquet venant d'Ubuntu que je compilerais pour la stable de Debian. Je prends volontairement un paquet non encore inclus dans les archives Debian, en l'occurrence [Ghostwriter](https://wereturtle.github.io/ghostwriter/) **mais non dans sa dernière version** car je compte ensuite vous montrer la simplicité de mettre un paquet dans sa dernière version via ses sources de façon presque automatique, c'est ça aussi Debian, un système qui vous simplifie la vie. Les sources Ubuntu sont disponibles depuis [Launchpad](https://launchpad.net/%7Ewereturtle/+archive/ubuntu/ppa), on n'aura besoin de télécharger qu'un seul fichier pour commencer et non des trois fichiers cités plus haut, le fichier *DSC*, on le télécharge via la commande `dget`:

    ~/Paquets/$ mkdir /ghostwriter
    
    ~/Paquets/ghostwriter$ dget https://launchpad.net/~wereturtle/+archive/ubuntu/ppa/+files/ghostwriter_1.6.0-0ppa1~trusty1.dsc
    
    dget: retrieving https://launchpad.net/~wereturtle/+archive/ubuntu/ppa/+files/ghostwriter_1.6.0-0ppa1~trusty1.dsc
    % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
    0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
    100  1942  100  1942    0     0   1793      0  0:00:01  0:00:01 --:--:--  1793
    dget: retrieving https://launchpad.net/~wereturtle/+archive/ubuntu/ppa/+files/ghostwriter_1.6.0.orig.tar.gz
    % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
    0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
    100  771k  100  771k    0     0   297k      0  0:00:02  0:00:02 --:--:--  733k
    dget: retrieving https://launchpad.net/~wereturtle/+archive/ubuntu/ppa/+files/ghostwriter_1.6.0-0ppa1~trusty1.debian.tar.xz
    % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
    0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
    100  2184  100  2184    0     0   2752      0 --:--:-- --:--:-- --:--:--  5762
    ghostwriter_1.6.0-0ppa1~trusty1.dsc:
    dscverify: ghostwriter_1.6.0-0ppa1~trusty1.dsc failed signature check:
    gpg: WARNING: no command supplied.  Trying to guess what you mean ...
    gpg: Signature made sam. 07 avril 2018 23:47:46 CEST
    gpg:                using RSA key 395C56156A3F539F
    gpg: Can't check signature: Pas de clef publique
    Validation FAILED!!

Un peu d'explication, pour recompiler un paquet Debian, il faut commencer par rapatrier son code source. Le moyen le plus simple est d'employer la commande `apt-get source nom-paquet-source`, qui nécessite la présence d'une ligne de type **deb-src** dans le fichier **/etc/apt/sources.list** et l'exécution préalable de la commande `apt-get update`. Ceci dit, il faut comprendre que pour cette commande, les sources doivent déjà être disponible dans l'archive Debian, or ce n'est pas le cas pour Ghostwriter. Il nous faut donc télécharger manuellement les sources depuis une archive **DEB** ou depuis le site web du programme: récupérer deux ou trois fichiers (d'extensions **.dsc**,  **.tar.comp** et parfois **.diff.gz** ou **.debian.tar.comp** — *comp* pouvant prendre les valeurs *gz*, *bz2* ou *xz* selon l'outil de compression employé), puis exécuter la commande `dpkg-source -x fichier.dsc`. Puisque ici le fichier **.dsc** est disponible à une URL donnée, on peut même se simplifier la vie en utilisant `dget URL` : cette commande (qui fait partie du paquet **devscripts** ) récupère le **.dsc** à l'adresse indiquée, en analyse le contenu et récupère automatiquement le ou les fichiers qu'il référence. Le paquet source est même extrait localement (à moins que l'option -d ou --download-only soit spécifiée). (https://debian-handbook.info/browse/fr-FR/stable/debian-packaging.html)

On a pu voir un "gpg: Can't check signature: Pas de clef publique Validation FAILED!!" , rien de grave, je n'ai pas ajouté la clé du launchpad et donc les outils me préviennent que *gpg* ne peut donc pas vérifier l'authenticité et il nous décompactera pas les sources pour nous. Nos sources sont bien maintenant dans notre dossier */home/nom-de-l'utilisateur/paquets/ghostwriter*, voyons ensemble dedans ce que nous avons:

    ~/Paquets/ghostwriter$ ls -1
    ghostwriter_1.6.0-0ppa1~trusty1.debian.tar.xz
    ghostwriter_1.6.0-0ppa1~trusty1.dsc
    ghostwriter_1.6.0.orig.tar.gz
    
Nous avons donc nos 3 fichiers essentiels, l'archive des sources amonts, l'archive de la transformation pour en faire un paquet binaire Debian, et notre fichier DSC, nous allons donc commencer par regarder ce que contient le DSC:

    ~/Paquets/ghostwriter$ nano ghostwriter_1.6.0-0ppa1~trusty1.dsc

    -----BEGIN PGP SIGNED MESSAGE-----
    Hash: SHA1
    Format: 3.0 (quilt)
    Source: ghostwriter
    Binary: ghostwriter
    Architecture: any
    Version: 1.6.0-0ppa1~trusty1
    Maintainer: Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com>
    Uploaders: wereturtle <wereturtledev@gmail.com>
    Homepage: http://wereturtle.github.io/ghostwriter/
    Standards-Version: 3.9.7
    Build-Depends: debhelper (>= 9), qtbase5-dev, libqt5svg5-dev, qtmultimedia5-dev, libqt5webkit5-dev, libhunspell-dev, pkg-config
    Package-List:
    ghostwriter deb editors optional arch=any
    Checksums-Sha1:
    ab272acee4319667c69f39bab246aa78a95e8cb6 789564 ghostwriter_1.6.0.orig.tar.gz
    8e261ef35b6e9b5527a7d73d922b64d944bb56b5 2184 ghostwriter_1.6.0-0ppa1~trusty1.debian.tar.xz
    Checksums-Sha256:
    0bcb0bf8d0eb2b57470da01161c015ed53ad09208a954f7424451b5c59251e71 789564 ghostwriter_1.6.0.orig.tar.gz
    9e4597e5c599425a88900fe2746fa5b2f3ebc1c9b83a47812fc23c0b74de8d56 2184 ghostwriter_1.6.0-0ppa1~trusty1.debian.tar.xz
    Files:
    740a5c0762bd2f14d5410af932b65776 789564 ghostwriter_1.6.0.orig.tar.gz
    6010c66e0ec415e860d9a95014750fff 2184 ghostwriter_1.6.0-0ppa1~trusty1.debian.tar.xz

    -----BEGIN PGP SIGNATURE-----
    Version: GnuPG v1

    iQIcBAEBAgAGBQJayTyCAAoJEDlcVhVqP1OfAzkP/1gFoezCY9How8FQU2CKGNFn
    SWxz/KULuwopQJzpvG/tBMA56+Owak9sNWXd6WZU+d06Xtb6r+LAT0NDvhgl2PoU
    GsbHHFDrMA7GP71bIz2Ng9AFgwnYDBJSvkG4o7VARSey/33iA0Xc8AsdvSv5dli8
    9NzY/2rA5xdgczbjGMdAzw2lCBO5jFCPHXFrLxRtp1mQOkGYc9r9diOHcmEdjIw3
    gzx0ZwUjgwV52dsSwIj61b8x4OVz9oFk4bEijGhmRVsQgsKz4xaIJAe/p0Dsc4yK
    +LqkshJjJxxATjoyJZWAAgvQMz8momMhg0Ht5yOCA0N/s9TxHo8tj4AKQAebD2AN
    YfjjE4uOGZMSBlUF1efEHukMAEgD8chIt00dYDD+7j1xaEYJeGCj5A8wgDb5jcUv
    hLt9TuDiG8J3ZxvxMahCly9N0tfRANWPcONnmQyRomGIGrY6l3OC94i65H3yg05/
    M0c3ApsVpccLF6rFXsATYoXn7XoF7JT453qTgcRf6Fhaq79K/RZFMhFpWKEDkXve
    w0rUz5AVXAfbYit+95/eQwHeQ0QjtYKzTmwPFoO+yE9O0fhuMUhiMXJsvyo7IowU
    lYuoKoCMLVXjj4nOIan7rg7YRnXgGEgK63HKzPbLlkDdeBskcmIzO0YjHM20MUUb
    tmryLkhYkZY57W8/S54V
    =lVh1
    -----END PGP SIGNATURE-----

Je ne pense pas avoir à revenir dessus, ce sont les informations classiques qu'on peut retrouver dans un SPEC. En faite ce fichier va être refait au moment de notre build, il reprend des données qui viennent de l'archive ghostwriter_1.6.0-0ppa1~trusty1.debian.tar.xz et qui auront changer d'ici à ce que l'on y touche. On peut s'assurer que les archives présentes ici ont bien les mêmes signatures.

Décompressons les archives, nous pouvons bien sur le faire graphiquement, nous avons donc nos deux dossiers nouvellement décompressés, un dossier **debian** et un dossier **ghostwriter-1.6.0**, nous allons maintenant déplacer le dossier debian dans celui du ghostwriter-1.6.0 et nous irons dedans:

    ~/Paquets/ghostwriter$ cd ghostwriter-1.6.0/debian/

Regardons ce qu'il contient:

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ ls
    changelog  compat  control  copyright  dirs  menu  rules  source  watch

Le fichier **changelog** est un fichier essentiel dans les sources debian et sera utilisé tout au long de la vie du paquet, c'est ce fichier qui déterminera la version du paquet, sa syntaxe est stricte et on devra faire appel à `dch` pour faire un changement dedans. Regardons ce que donne ce fichier:

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ cat changelog 
    
    ghostwriter (1.6.0-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sat, 7 Apr 2018 14:30:00 -0700

    ghostwriter (1.5.0+ds2-1ppa2~trusty1) trusty; urgency=low

    * Dependency fix for Artful Aardvark.

    -- wereturtle <wereturtledev@gmail.com>  Thu, 31 Aug 2017 23:00:00 -0700
 
    ghostwriter (1.5.0+ds1-1ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sat, 17 May 2017 13:00:00 -0700
 
    ghostwriter (1.5.0-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sat, 17 May 2017 11:15:00 -0700

    ghostwriter (1.4.2-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sun, 23 Aug 2016 09:06:00 -0700

    ghostwriter (1.4.1-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sun, 14 Aug 2016 15:02:00 -0700

    ghostwriter (1.4.0-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sun, 23 Jul 2016 11:40:00 -0700

    ghostwriter (1.3.1-1ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sun, 28 Feb 2016 15:40:00 -0700

    ghostwriter (1.3.1-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sat, 27 Feb 2016 15:18:00 -0700

    ghostwriter (1.3.0-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sat, 27 Feb 2016 12:51:00 -0700

    ghostwriter (1.2.5-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sun, 13 Dec 2015 12:51:00 -0700

    ghostwriter (1.2.4-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sat, 28 Nov 2015 11:14:00 -0700

    ghostwriter (1.2.3-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sat, 31 Oct 2015 11:47:00 -0700

    ghostwriter (1.2.2-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sat, 10 Oct 2015 16:52:00 -0700

    ghostwriter (1.2.1-0ppa1~trusty1) trusty; urgency=low

    * New upstream release.

    -- wereturtle <wereturtledev@gmail.com>  Sat, 03 Oct 2015 00:04:00 -0700

    ghostwriter (1.2.0-0ppa1~trusty1) trusty; urgency=low

    * Initial release for Ubuntu.

    -- wereturtle <wereturtledev@gmail.com>  Sun, 27 Sep 2015 00:44:56 -0700

Les entrés sont dans l'ordre de chronologie inverse, les changements récents sont en haut. Je décide donc de changer la version et de faire référence à Debian pour marquer la "debianisation", on le fait avec `dch -r`.

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ dch -r
    
Puis je change de cette façon:

    ghostwriter (1.6.0-1~schav1) unstable; urgency=low

    * package for Debian

    [ wereturtle ]
    * New upstream release.

    -- Sebastien CHAVAUX <seb95.scou@gmail.com>  Fri, 20 Apr 2018 19:21:47 +0200

C'est pré-rempli, je n'ai donc que peu de chose à faire:)

Le fichier **compat** contient juste un nombre identifiant la version des outils **debhelper**, Stretch en est à la **version 9**.

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ cat compat 
    9

Je continue à vous expliquer les autres fichiers car ils sont important et normalement ils sont le strict minimum pour faire un paquet propre, j'explique en survolant car ils sont tout de même explicites et en parler plus prendrait beaucoup de temps. Le fichier **control** est le plus important, c'est lui qui fournit toutes les informations sur les paquets sources et binaires du logiciel en cours, que ce soit le nom du paquet source, la section dans l'archive Debian (editeur, jeux, kde, ...), les dépendances de build, les noms des paquets binaires,  l'architecture, les dépendances, la description, bref c'est lui qui va entre autre remplir le fichier **DSC**  une fois notre paquet contruis.

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ cat control 

    Source: ghostwriter
    Section: editors
    Priority: optional
    Maintainer: Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com>
    Uploaders: wereturtle <wereturtledev@gmail.com>
    Build-Depends: debhelper (>= 9),
                    qtbase5-dev,
                    libqt5svg5-dev,
                    qtmultimedia5-dev,
                    libqt5webkit5-dev,
                    libhunspell-dev,
                    pkg-config
    Standards-Version: 3.9.7
    Homepage: http://wereturtle.github.io/ghostwriter/
    #Vcs-Git: git://git.debian.org/collab-maint/ghostwriter.git
    #Vcs-Browser: http://git.debian.org/?p=collab-maint/ghostwriter.git;a=summary

    Package: ghostwriter
    Architecture: any
    Depends: libqt5concurrent5,
            libqt5printsupport5,
            libqt5svg5,
            ${misc:Depends},
            ${shlibs:Depends},
    Suggests: hunspell-dictionary, myspell-dictionary
    Description: Distraction-free, themeable Markdown editor
    ghostwriter is a Markdown editor that provides a themable,
    distraction-free writing environment, along with a live HTML
    preview as you type, easy document navigation with an outline HUD,
    and export to popular document formats with Sundown, Pandoc,
    MultiMarkdown, Discount, cmark, or cmark-gfm processors.  It also
    features a live word count and auto-save. Eliminate distractions in
    fullscreen mode, or concentrate on the current text you are writing
    in focus mode.  It even remembers your last opened file and position
    within the file, so you can pick up where you last left off.

Nous pouvons ici, changer le mainteneur par nous et nous rajouter dans l'Uploaders:

    Maintainer: Sebastien CHAVAUX <seb95.scou@gmail.com>
    Uploaders: Sebastien CHAVAUX <seb95.scou@gmail.com>, wereturtle <wereturtledev@gmail.com>

Le **copyright** est un fichier requis par la [charte Debian](https://www.debian.org/doc/devel-manuals.fr.html), spécifie les informations nécessaires pour connaître l'auteur amont et sa licence.

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ cat copyright 
    Format: http://www.debian.org/doc/packaging-manuals/copyright-format/1.0/
    Upstream-Name: ghostwriter
    Upstream-Contact: wereturtle <wereturtledev@gmail.com>
    Source: http://wereturtle.github.io/ghostwriter/
            git://github.com/wereturtle/ghostwriter.git

    Files: *
    Copyright: 2014-2018 wereturtle <wereturtledev@gmail.com>
    License: GPL-3.0+

    Files: debian/*
    Copyright: 2015-2018 wereturtle <wereturtledev@gmail.com>
    License: GPL-3.0+

    License: GPL-3.0+
    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.
    .
    This package is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.
    .
    You should have received a copy of the GNU General Public License
    along with this program. If not, see <http://www.gnu.org/licenses/>.
    .
    On Debian systems, the complete text of the GNU General
    Public License version 3 can be found in "/usr/share/common-licenses/GPL-3".

Je n'y touche pas ! Pas plus que les fichiers **dirs** et **menu**.

Il peut être intéressant de regarder le fichier **rules** qui est celui qui contrôle la fabrication du ou des paquets, définit les étapes de construction, c'est un fichier exécutable. Par exemple, on touchera à ce fichier pour ajouter une option ou une fonction au programme.

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ cat rules 
    #!/usr/bin/make -f

    export QT_SELECT=qt5

    %:
        dh $@ --parallel
        
Le dernier fichier que j'explique ici est assez simple, c'est celui qui va permettre de contrôler si une nouvelle version est disponible, si bien rempli, il va même télécharger via la commande `uscan` la dernière version, on verra ensemble son utilisation pour la mise en paquet de la nouvelle version de Ghostwriter. (plus d'info: https://www.debian.org/doc/manuals/maint-guide/dother.fr.html#watch)

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ cat watch 
    version=3
    https://github.com/wereturtle/ghostwriter/releases /wereturtle/ghostwriter/archive/v(.+)\.tar\.gz

Donc je récapitule un peu, car j'ai quand meme noyé les étapes avec les différents fichiers et leurs contenus. Nous avons changer la version dans le **changelog** via `dch -r` et mit la raison du build, nous avons ensuite changer le mainteneur (à ne pas faire normalement mais le ubuntu donne un *warning* voir ma demande https://mentors.debian.net/package/ghostwriter) et nous nous sommes ajouté dans l'uploader. 

Nous pouvons lancer le build via `debuild` mais avant il faut installer les dépendances de build:

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ su
    Mot de passe : (vide, normale ;p)

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian# apt-get build-dep ~/Paquets/ghostwriter/ghostwriter_1.6.0-0ppa1~trusty1.dsc
    Note, using file '/home/sebastien/Paquets/ghostwriter/ghostwriter_1.6.0-0ppa1~trusty1.dsc' to get the build dependencies
    Lecture des listes de paquets... Fait
    Construction de l'arbre des dépendances       
    Lecture des informations d'état... Fait
    Les NOUVEAUX paquets suivants seront installés :
    libhunspell-dev libqt5quickparticles5 libqt5quicktest5 libqt5svg5-dev libqt5webkit5-dev qt5-qmake
    qt5-qmltooling-plugins qtbase5-dev qtbase5-dev-tools qtdeclarative5-dev qtmultimedia5-dev
    0 mis à jour, 11 nouvellement installés, 0 à enlever et 1 non mis à jour.
    Il est nécessaire de prendre 4 081 ko dans les archives.
    Après cette opération, 27,9 Mo d'espace disque supplémentaires seront utilisés.
    Souhaitez-vous continuer ? [O/n]
    [....]

et enfin la fabrication:

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ debuild 
    dpkg-buildpackage -rfakeroot -us -uc
    dpkg-buildpackage: info: paquet source ghostwriter
    dpkg-buildpackage: info: version source 1.6.0-1~schav1
    dpkg-buildpackage: info: distribution source unstable
    dpkg-buildpackage: info: source changé par Sebastien CHAVAUX <seb95.scou@gmail.com>
    dpkg-source --before-build ghostwriter-1.6.0
    dpkg-buildpackage: info: architecture hôte amd64
    fakeroot debian/rules clean
    dh clean --parallel
    dh_testdir -O--parallel
    dh_auto_clean -O--parallel
            make -j4 distclean
    make[1] : on entre dans le répertoire « /home/sebastien/Paquets/ghostwriter/ghostwriter-1.6.0 »
    rm -f build/release/qrc_resources.cpp
    rm -f build/release/moc_MainWindow.cpp build/release/moc_MarkdownEditor.cpp build/release/moc_HtmlPreview.cpp build/release/moc_TextBlockData.cpp build/release/moc_HudWindow.cpp build/release/moc_ThemeSelectionDialog.cpp build/release/moc_ThemeEditorDialog.cpp build/release/moc_AppSettings.cpp build/release/moc_DocumentManager.cpp build/release/moc_TextDocument.cpp build/release/moc_ExportDialog.cpp build/release/moc_Outline.cpp build/release/moc_MarkdownHighlighter.cpp build/release/moc_StyleSheetManagerDialog.cpp build/release/moc_SimpleFontDialog.cpp build/release/moc_TimeLabel.cpp build/release/moc_LocaleDialog.cpp build/release/moc_AbstractStatisticsWidget.cpp build/release/moc_DocumentStatistics.cpp build/release/moc_DocumentStatisticsWidget.cpp build/release/moc_SessionStatistics.cpp build/release/moc_SessionStatisticsWidget.cpp build/release/moc_PreferencesDialog.cpp build/release/moc_PreviewOptionsDialog.cpp build/release/moc_find_dialog.cpp build/release/moc_image_button.cpp build/release/moc_color_button.cpp build/release/moc_dictionary_manager.cpp buil
    [....]
    dpkg-shlibdeps: avertissement: la dépendance pourrait être évitée si « debian/ghostwriter/usr/bin/ghostwriter » n'y était pas lié avec libpthread.so.0 sans nécessité (il n'utilise aucun des symboles de la bibliothèque)
    dpkg-shlibdeps: avertissement: la dépendance pourrait être évitée si « debian/ghostwriter/usr/bin/ghostwriter » n'y était pas lié avec libGL.so.1 sans nécessité (il n'utilise aucun des symboles de la bibliothèque)
    dpkg-shlibdeps: avertissement: la dépendance pourrait être évitée si « debian/ghostwriter/usr/bin/ghostwriter » n'y était pas lié avec libQt5Network.so.5 sans nécessité (il n'utilise aucun des symboles de la bibliothèque)
    dpkg-shlibdeps: avertissement: la dépendance pourrait être évitée si « debian/ghostwriter/usr/bin/ghostwriter » n'y était pas lié avec libQt5Concurrent.so.5 sans nécessité (il n'utilise aucun des symboles de la bibliothèque)
    dh_installdeb -O--parallel
    dh_gencontrol -O--parallel
    dh_md5sums -O--parallel
    dh_builddeb -O--parallel
    dpkg-deb: building package 'ghostwriter-dbgsym' in '../ghostwriter-dbgsym_1.6.0-1~schav1_amd64.deb'.
    dpkg-deb: building package 'ghostwriter' in '../ghostwriter_1.6.0-1~schav1_amd64.deb'.
    dpkg-genbuildinfo
    dpkg-genchanges  >../ghostwriter_1.6.0-1~schav1_amd64.changes
    dpkg-genchanges: info: inclusion du code source original dans l'envoi (« upload »)
    dpkg-source --after-build ghostwriter-1.6.0
    dpkg-buildpackage: info: envoi complet (inclusion du code source d'origine)
    Now running lintian...
    W: ghostwriter source: maintainer-also-in-uploaders
    W: ghostwriter source: out-of-date-standards-version 3.9.7 (current is 3.9.8)
    W: ghostwriter: command-in-menu-file-and-desktop-file ghostwriter usr/share/menu/ghostwriter:7
    Finished running lintian.
    Now signing changes and any dsc files...
    signfile dsc ghostwriter_1.6.0-1~schav1.dsc XXXXXXXXXXXXXXXXXXXXXXXXXXX

    fixup_buildinfo ghostwriter_1.6.0-1~schav1.dsc ghostwriter_1.6.0-1~schav1_amd64.buildinfo
    signfile buildinfo ghostwriter_1.6.0-1~schav1_amd64.buildinfo XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

    fixup_changes dsc ghostwriter_1.6.0-1~schav1.dsc ghostwriter_1.6.0-1~schav1_amd64.changes
    fixup_changes buildinfo ghostwriter_1.6.0-1~schav1_amd64.buildinfo ghostwriter_1.6.0-1~schav1_amd64.changes
    signfile changes ghostwriter_1.6.0-1~schav1_amd64.changes XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

    Successfully signed dsc, buildinfo, changes files

Nos paquets sont construit.

On remarque que certaines dépendances pourraient être évités: 

    dpkg-shlibdeps: avertissement: la dépendance pourrait être évitée si « debian/ghostwriter/usr/bin/ghostwriter » n'y était pas lié avec libpthread.so.0 sans nécessité (il n'utilise aucun des symboles de la bibliothèque)
    dpkg-shlibdeps: avertissement: la dépendance pourrait être évitée si « debian/ghostwriter/usr/bin/ghostwriter » n'y était pas lié avec libGL.so.1 sans nécessité (il n'utilise aucun des symboles de la bibliothèque)
    dpkg-shlibdeps: avertissement: la dépendance pourrait être évitée si « debian/ghostwriter/usr/bin/ghostwriter » n'y était pas lié avec libQt5Network.so.5 sans nécessité (il n'utilise aucun des symboles de la bibliothèque)
    dpkg-shlibdeps: avertissement: la dépendance pourrait être évitée si « debian/ghostwriter/usr/bin/ghostwriter » n'y était pas lié avec libQt5Concurrent.so.5 sans nécessité (il n'utilise aucun des symboles de la bibliothèque)

On remarque aussi différents *warning* :

    Now running lintian...
    W: ghostwriter source: maintainer-also-in-uploaders
    W: ghostwriter source: out-of-date-standards-version 3.9.7 (current is 3.9.8)
    W: ghostwriter: command-in-menu-file-and-desktop-file ghostwriter usr/share/menu/ghostwriter:7
    Finished running lintian.

Pour le premier *warning*, le mainteneur ne devrait pas être répété dans Uploaders, ce que je décide d'ignorer puisque par défaut *Ubuntu Developers <ubuntu-devel-discuss@lists.ubuntu.com>* fait aussi un warning, si je veux corriger c'est dans le fichier **control** que ça se trouve. Le second est encore plus simple et c'est dû à une inattention de ma part, j'aurais dû remarquer la version de la charte technique, c'est celle que le mainteneur se conforme de respecter en créant son paquet. Sous Stretch, nous en somme à la 3.9.8 et je modifie donc pour la prochaine fois... Pour le troisième, je suppose que c'est le :7 qui est en trop dans le fichier **menu** mais là je sèche :)

Maintenant qu'on a expliqué en large et en long, je récapitule les commandes:

1/ Téléchargement du **DSC** (penser à se mettre dans le dossier de notre future paquet):

    ~/Paquets/ghostwriter$ dget https://launchpad.net/~wereturtle/+archive/ubuntu/ppa/+files/ghostwriter_1.6.0-0ppa1~trusty1.dsc

2/ Installation des dépendances (en **root**):

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian# apt-get build-dep ~/Paquets/ghostwriter/ghostwriter_1.6.0-0ppa1~trusty1.dsc

3/ Modification de la version du programme, de la version de la distribution (Ubuntu vers Debian unstable), enfin ne pas oublier d'y mettre la raison du build (penser à se mettre dans le dossier /debian du logiciel voulu):

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ dch -r

4/ Lancement de la construction:

    debuild

Nous avons nos paquets, nos fichiers de log pour le build, le nouveau DSC changé, l'archive compressé du dossier debian avec nos modifications. Nous pourront regarder le fichier *ghostwriter_1.6.0-1~schav1_amd64.changes* pour voir. 

    ~/Paquets/ghostwriter$ ls 
    ghostwriter-1.6.0                              ghostwriter_1.6.0-1~schav1_amd64.buildinfo  ghostwriter_1.6.0-1~schav1.dsc
    ghostwriter_1.6.0-0ppa1~trusty1.debian.tar.xz  ghostwriter_1.6.0-1~schav1_amd64.changes    ghostwriter_1.6.0.orig.tar.gz
    ghostwriter_1.6.0-0ppa1~trusty1.dsc            ghostwriter_1.6.0-1~schav1_amd64.deb        ghostwriter-dbgsym_1.6.0-1~schav1_amd64.deb
    ghostwriter_1.6.0-1~schav1_amd64.build         ghostwriter_1.6.0-1~schav1.debian.tar.xz

Regardons le fichier *ghostwriter_1.6.0-1~schav1_amd64.changes* pour voir les changements de ce builds:
    
    ~/Paquets/ghostwriter$ cat ghostwriter_1.6.0-1~schav1_amd64.changes 
    -----BEGIN PGP SIGNED MESSAGE-----
    Hash: SHA256
    
    Format: 1.8
    date: Fri, 20 Apr 2018 19:21:47 +0200
    Source: ghostwriter
    Binary: ghostwriter
    Architecture: source amd64
    Version: 1.6.0-1~schav1
    Distribution: unstable
    Urgency: low
    Maintainer: Sebastien CHAVAUX <seb95.scou@gmail.com>
    Changed-By: Sebastien CHAVAUX <seb95.scou@gmail.com>
    Description:
    ghostwriter - Distraction-free, themeable Markdown editor
    Changes:
    ghostwriter (1.6.0-1~schav1) unstable; urgency=low
    .
    * package for Debian
    .
    [ wereturtle ]
    * New upstream release.
    Checksums-Sha1:
    4bd9fdbd88d6133b4a5bbf2a0d286a590dc34253 1618 ghostwriter_1.6.0-1~schav1.dsc
    ab272acee4319667c69f39bab246aa78a95e8cb6 789564 ghostwriter_1.6.0.orig.tar.gz
    5e1ee5be9288567c128229ddb93dff65c7de562c 2224 ghostwriter_1.6.0-1~schav1.debian.tar.xz
    feb8290a7d05a36f8cbb526c16d29c2987bdcac9 8062606 ghostwriter-dbgsym_1.6.0-1~schav1_amd64.deb
    25a815d3aec1d1423166bd9fa16b935f1c7a4009 11340 ghostwriter_1.6.0-1~schav1_amd64.buildinfo
    57bf08fed54c25a626ef0995f20fddb679646b2f 384182 ghostwriter_1.6.0-1~schav1_amd64.deb
    Checksums-Sha256:
    c158e0659286cf1ad3b3a4acd86b770f41e4418861d77dea9bf070e62dd062d0 1618 ghostwriter_1.6.0-1~schav1.dsc
    0bcb0bf8d0eb2b57470da01161c015ed53ad09208a954f7424451b5c59251e71 789564 ghostwriter_1.6.0.orig.tar.gz
    efe51ac6aa2f1e6a117130f7be880922cde8d1875889aa5f0818e76c448118c0 2224 ghostwriter_1.6.0-1~schav1.debian.tar.xz
    6457444fcdf3426e1c930b043fbc698fd3f6be1655332811dfe033bdf30cbf85 8062606 ghostwriter-dbgsym_1.6.0-1~schav1_amd64.deb
    f793275fcd72bd85f18793396a61cddec62ee5166c715f5c8565956088650249 11340 ghostwriter_1.6.0-1~schav1_amd64.buildinfo
    4dc45011023b16caccff74ebb33d48750baff66eef53a75597838efd35c54536 384182 ghostwriter_1.6.0-1~schav1_amd64.deb
    Files:
    30bb8c33bfd1aeccbb2356e874645830 1618 editors optional ghostwriter_1.6.0-1~schav1.dsc
    740a5c0762bd2f14d5410af932b65776 789564 editors optional ghostwriter_1.6.0.orig.tar.gz
    252af53442e50d40f1d4a85a3f678b1f 2224 editors optional ghostwriter_1.6.0-1~schav1.debian.tar.xz
    632a601524de3f5c9e5dd97c73c6d988 8062606 debug extra ghostwriter-dbgsym_1.6.0-1~schav1_amd64.deb
    e9e3cb40b70fde62e23543e40017034d 11340 editors optional ghostwriter_1.6.0-1~schav1_amd64.buildinfo
    76268cb27aa50c80b17ba124dfba74c3 384182 editors optional ghostwriter_1.6.0-1~schav1_amd64.deb

    -----BEGIN PGP SIGNATURE-----

    iQEzBAEBCAAdFiEEXOsrOHvyxJM5+4X7Qk4R/tAPf9wFAlraMowACgkQQk4R/tAP
    f9zoOAf/fA1jN8kGUKQs0JXuWc2H3bJIHzzeiNf8MGnmHfZZwu3DW0cOgiMqyx7h
    Lcr00OXz8yJWnDkuoz88NZZ1TbwPVTIfYyeplJnE9osyKHPd3x4195S8X5GtOWWe
    0YcW7qf0p6LZ7teN8J9Qdu1NowqoM9Q4VvaZZhOQ2Ef3WmBbvUuLPWbPGtZulx9+
    l42rROLlThltJ1k55VobtTx4pP6qvdslQuNEmtrj3cHSa2mdRoFafZckRLAUfpnK
    bB2i3HuAzph9xbcWLopy2BQhinMpViyNziv1+CxEuygDrgwn06Pu1/ve7SNMBYpV
    0MpC94SvvG5GMueOnO8j09L4+/uwRA==
    =woOB
    -----END PGP SIGNATURE-----

Source:

- https://debian-handbook.info/browse/fr-FR/stable/debian-packaging.html, 
- https://blog.microlinux.fr/rpm-build/,
- https://debian-facile.org/doc:mentors:signer-un-paquet.
- Livre Debian Administration et configuration avancées (EYROLLES 2006 et toujours valable 12 ans après!!!) - https://www.eyrolles.com/Informatique/Livre/debian-9782212119046
- https://www.debian.org/doc/manuals/maint-guide/index.fr.html
