---
title: Développer pour Frugalware 2, création de paquets, entraînons nous avec un exemple simple
date: 2014-06-10 22:56
layout: post
---

*Pourquoi utiliser un environnement chroot pour compiler ses paquets ?*
Tout simplement parce que le chroot permet de trouver les véritables
dépendances pour votre paquet sans pour autant “sacrifier” votre
système. Le chroot, c'est une sorte de matrice qui joue le rôle de votre
système dans votre système. Pour créer le chroot, il vous suffira juste
d'installer les paquets nécessaires en tapant la commande suivante.
[Makepkg](https://wiki.frugalware.org/index.php/Makepkg_%28Fran%C3%A7ais%29 "Makepkg (Français)")
s'occupera de télécharger et d'installer ce qu'il faudra lorsque vous
ferez votre premier FrugalBuild. Par défaut, le chroot se situe dans le
répertoire /var/chroot. Vous pouvez changer son emplacement en modifiant
le fichier /etc/makepkg.conf Essayez [cette exemple simple et
détaillé](https://wiki.frugalware.org/index.php/FrugalBuild_%28exemple_d%C3%A9taill%C3%A9%29 "FrugalBuild (exemple détaillé)"):  

Exemple détaillé d'un FrugalBuild
=================================

Notre exemple
-------------

      # Compiling Time: 0.06 SBU # Maintainer: VMiklos <vmiklos@frugalware.org> pkgname=cabextract pkgver=1.2 pkgrel=1 pkgdesc="a program to extract Microsoft Cabinet files"  url="http://www.kyz.uklinux.net/cabextract.php"depends=('glibc') groups=('apps')  archs=('i686' 'x86_64') up2date="lynx -dump http://www.kyz.uklinux.net/cabextract.php |grep 'cabextract source code'|tr -s ' '|cut -d ' ' -f 6"  source=(http://www.kyz.uklinux.net/downloads/$pkgname-$pkgver.tar.gz)  sha1sums=('871b3db4bc2629eb5726659c147aecea1af6a6d0')  # optimization OK

Détaillons chaque élément…
--------------------------

### \# Compiling Time: SBU

      # Compiling Time:  SBU

Cette ligne signifie le temps de compilation, elle se rajoute
automatiquement lors de la compilation ou par vérification via la
commande fblint.  

### Maintainer et Contributor

      # Maintainer: VMiklos <vmiklos@frugalware.org>

Cette ligne indique le nom de mainteneur de paquet, si vous n'allez pas
maintenir indiquez ceci:

      # Contributor: votrepseudo <votreemail@blabla.com>

### pkgname

      pkgname=cabextract

Cette ligne indique le nom de paquet. Ce sera le nom utilisé dans vos
commandes pacman une fois le paquet au dépôt.  

### pkgver

      pkgver=1.2

Cette ligne indique la version du programme cabextract, faîtes bien
attention certains programmes ont des manières différentes de nommer ces
numéros de version.  

### pkgrel

      pkgrel=1

Cette ligne indique la version du paquet. Si vous avez recompilé le
paquet afin de corriger des choses…etc vous devez alors changer le 1 par
2 (et ainsi de suite).  

### pkgdesc

      pkgdesc="a program to extract Microsoft Cabinet files"

Cette ligne indique une courte description du programme en question.  

### url

      url="http://www.kyz.uklinux.net/cabextract.php"

Cette ligne indique la page web du programme.  

### depends (dépendances)

      depends=('glibc')

Cette ligne est très importante, elle indique les dépendances
nécessaires au paquet. Dans cet exemple, glibc est nécessaire au
fonctionnement de cabextract. Si votre paquet nécessite plusieurs
dépendances il vous faudra toutes les indiquer entre guillemets et
espacées par un espace. Pour trouver les dépendances d'un paquet
utilisez la commande makepkg -a.  

### Le Groupe

      groups=('apps')

Cette ligne indique le groupe auquel appartient le paquet. Ne placez pas
votre paquet dans les groupes apps, base, devel, lib, multimedia ou
network, vous devez utiliser un groupe adéquat avec le suffixe -extra.
Par exemple si vous faîtes un paquet d'un programme pour Gnome, prenez
le groupe gnome-extra.  

### Architectures

      archs=('i686' 'x86_64')

Cette ligne indique l'architecture pour laquelle se destine votre
paquet. Dans cet exemple les architectures sont i686 et x86\_64.  

### L'up2date

      up2date="lynx -dump http://www.kyz.uklinux.net/cabextract.php |grep 'cabextract        source code'|tr -s ' '|cut -d ' ' -f 6"

Cette ligne est destinée au serveur de frugalware.org pour signaler aux
mainteneurs la présence d'une nouvelle version du fichier source. Elle
n'est pas toujours facile à faire, voici quelque exemples: Pour une page
comportant le lien vers le tarball en tar.gz, l'up2date devrait
ressembler à ceci:

      up2date="lynx -dump http://adressedelapage/page.php |grep tar.gz | Flasttar"

Note: S'il y a plusieurs liens pour des tar.gz, pour que l'up2date
sélectionne le premier lien, mettez grep -m1 tar.gz. S'il n'y a pas de
page mais juste un espace avec des tarball en tar.bz2,

      up2date="lynx -dump http://adressedelapage/ | Flasttarbz2"

Si vraiment vous n'y arrivez pas, vous pouvez bloquer l'up2date et
indiquez aux développeurs de Frugalware qu'ils devront corriger la
ligne, voilà ce qu'il faut mettre:

      up2date=$pkgver #need to be fixed

### Source

      source=(http://www.kyz.uklinux.net/downloads/$pkgname-$pkgver.tar.gz)

Cette ligne indique l'URL de la source du programme. Ce fichier tar.gz
sera téléchargé pour la compilation du paquet.  

### SHA1SUMS

      sha1sums=('094e3afb2fe8dfe82f63731cdcd3b999f4856cff')

Cette ligne indique le SHA1SUM du fichier source de la précédente ligne.
Avec la commande makepkg -g vous aurez le SHA1SUM du fichier source.
Ensuite arrive la partie build, dans l'exemple il n'y en a pas. Allez
voir la section plus bas pour les détails.  

### \# optimization OK

      # optimization OK

Cette ligne est rajouté automatiquement lors de la compilation ou par la
commande fblint. Elle indique que la compilation a été faite par votre
\$CFLAGS ou \$CXXFLAGS.  

build
-----

Dans l'exemple plus haut il n'y avait pas de partie build, tout
simplement car par défaut si vous ne mettez rien, le build correspond à
ceci:

      build() {          Fpatchall          Fmake "$@"            Fmakeinstall          if echo ${source[@]}|grep -q README.Frugalware; then          Fdoc README.Frugalware          fi  }

Les commandes sont indiquées entre { }. Si votre paquet se compile avec
les banales:

      ./configure  make  make install

alors, là aussi, il n'est pas nécessaire de mettre un build, que c'est
pratique… :-D Nous avons vu sur cette page les fonctions classiques que
comporte un FrugalBuild mais il en existe d'autres suivant les cas
particuliers:

-   [Autres fonctions possibles dans un
    FrugalBuild](https://wiki.frugalware.org/index.php/FrugalBuild_%28autre_fonctions%29 "FrugalBuild (autre fonctions)")

puis placez-vous dans le répertoire où se trouve le FrugalBuild. Et
lancez la commande:

<div style="text-align: left;">

<div style="float: left;">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ sudo makepkg -H

</div>

</div>

Ce n'est pas conseillé car vous risquez de passer à coté de certaines
dépendances. Il est recommandé de consulter toutes les commandes
possibles avec
[Makepkg](https://wiki.frugalware.org/index.php/Makepkg_%28Fran%C3%A7ais%29 "Makepkg (Français)").  

Allez plus loin
---------------

### FrugalBuild

Un [exemple
vierge](https://wiki.frugalware.org/index.php/FrugalBuild_%28exemple_vierge%29 "FrugalBuild (exemple vierge)")
est disponible. Si vous avez des difficultés avec votre FrugalBuild,
n'hésitez pas à demander de l'aide sur ircou sur le forum. Pour plus
d'informations sur les FrugalBuild, n'oubliez pas le manuel en tapant :

<div style="text-align: left;">

<div style="float: left;">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ man FrugalBuild

</div>

</div>

### Composition d'un FrugalBuild

Avant d'aller plus loin, il vous faut déjà connaitre l'outil de base de
la création de paquet. C'est-à-dire, le FrugalBuild. C'est grâce à lui
que vous donnerez les “instructions” à makepkg pour qu'il puisse
accomplir sa tâche. Voici un FrugalBuild vierge :

-   Exemple de [FrugalBuild
    vierge](https://wiki.frugalware.org/index.php/FrugalBuild_%28exemple_vierge%29 "FrugalBuild (exemple vierge)")

Les explications

-   [La documentation générale sur le
    FrugalBuild](https://wiki.frugalware.org/index.php/FrugalBuild_%28documentation_g%C3%A9n%C3%A9rale%29 "FrugalBuild (documentation générale)")

Les fonctions

-   [Autres fonctions possibles dans un
    FrugalBuild](https://wiki.frugalware.org/index.php/FrugalBuild_%28autre_fonctions%29 "FrugalBuild (autre fonctions)")

Prêt à contribuer ?
-------------------

Ne gardez pas vos paquets fpm que pour vous, vous pouvez les partager en
les proposant aux développeurs. Il suffit pour çà de vous inscrire sur
la mailing list anglophone frugalware-devel:

-   <http://frugalware.org/mailman/listinfo/frugalware-devel>

Même si l'anglais vous rebutte, n'ayez crainte. Une fois souscris à la
liste envoyez votre mail à

-   **frugalware-devel AT frugalware POINT org**

Avec votre FrugalBuild (et patches si besoin) attaché au mail en demande
une "review". L'équipe de développement se fera un plaisir de vous
répondre et vous aider si votre FrugalBuild comporte des erreurs. Par la
suite, il est préférable de [cloner le dépôt
git](https://wiki.frugalware.org/index.php/Cloner_le_d%C3%A9p%C3%B4t_git "Cloner le dépôt git")
pour des raisons pratiques. Une fois le FrugalBuild sans fautes, on vous
demandera de [faire un patch
git](http://passiongnulinux.tuxfamily.org/?p=33)
