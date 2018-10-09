---
title: Construire des paquets DEB pour Debian (deuxième partie)
date: 2018-04-21T14:01:41+02:00
layout: post
---

## Le fichier watch et la commande uscan, ou comment faire la plus grosse partie du travail d'un mainteneur ##

Dans le dernier billet, nous avons vu ensemble pour importer des sources d'un paquet sur Ubuntu pour le construire sur et pour une Debian stable, je vous propose donc de continuer sur la  possibilité d'automatiser une grosse partie du processus si une nouvelle version amont sort.

Nous retournons dans nos sources du paquet Ghostwriter que nous venions de faire, et allons voir le fameux fichier watch vu ensemble et dont je disais:

> Le dernier fichier que j’explique ici est assez simple, c’est celui qui va permettre de contrôler si une nouvelle version est disponible, si bien rempli, il va même télécharger via la commande uscan la dernière version, on verra ensemble son utilisation pour la mise en paquet de la nouvelle version de Ghostwriter. (plus d’info: https://www.debian.org/doc/manuals/maint-guide/dother.fr.html#watch)

Il ressemble donc à ceci actuellement:

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ cat watch 
    version=3
    https://github.com/wereturtle/ghostwriter/releases /wereturtle/ghostwriter/archive/v(.+)\.tar\.gz

Normalement mais c'est rarement le cas (je n'en ai vu que très peu le faire), la ligne de l'adresse devrait finir par `debian uupdate` , ce qui permet de faire tout automatiquement en faisant la commande `uscan`: les sources de la nouvelle version seront automatiquement recherchées, téléchargées, et la commande `uupdate` sera exécutée. Si la commande `uscan` télécharge les nouvelles sources mais n'exécute pas la commande `uupdate`, vous devriez corriger le fichier debian/watch pour avoir **debian uupdate** après l'URL. N'étant pas le cas pour Ghostwriter, nous corrigeons comme ceci:

    ~/Paquets/ghostwriter/ghostwriter-1.6.0/debian$ cat watch 
    version=3
    https://github.com/wereturtle/ghostwriter/releases /wereturtle/ghostwriter/archive/v(.+)\.tar\.gz debian uupdate

Et nous lançons `uscan` pour que les outils fassent le boulot à notre place:

    ~/Paquets/ghostwriter/ghostwriter-1.6.0$ uscan
    uscan: Newest version of ghostwriter on remote site is 1.6.2, local version is 1.6.0
    uscan:    => Newer package available from
      https://github.com/wereturtle/ghostwriter/archive/v1.6.2.tar.gz

Normalement tout a été fait si le fichier watch est bien fait:

    ~/Paquets/ghostwriter$ ls
    ghostwriter-1.6.0                           ghostwriter_1.6.0-1~schav1_amd64.deb      ghostwriter-1.6.2                            v1.6.2.tar.gz
    ghostwriter_1.6.0-1~schav1_amd64.build      ghostwriter_1.6.0-1~schav1.debian.tar.xz  ghostwriter-1.6.2.orig
    ghostwriter_1.6.0-1~schav1_amd64.buildinfo  ghostwriter_1.6.0-1~schav1.dsc            ghostwriter_1.6.2.orig.tar.gz
    ghostwriter_1.6.0-1~schav1_amd64.changes    ghostwriter_1.6.0.orig.tar.gz             ghostwriter-dbgsym_1.6.0-1~schav1_amd64.deb

Il y a bien le nouveau *ghostwriter_1.6.2.orig.tar.gz* (nomination Debian des sources non debianisés) qui est un lien symbolique vers *v1.6.2.tar.gz*, le dossier *ghostwriter-1.6.2.orig* (sans modifications donc!) et le dossier *ghostwriter-1.6.2* avec la debianisation, c'est-à-dire le sous-dossier debian. On s’arrête pour parler de ce qui vient de se passer, je sais pas si vous vous rendez compte du taf qui a été fait automatiquement et sans que vous n'ayez à bouger vos petits doigts? Je vais donc le dire, les outils ont **détecté une nouvelle version** en amont sur le site de l'auteur, la 1.6.2, ils ont donc **téléchargé l'archive** de cette version nommé en amont *v1.6.2.tar.gz*, ils ont fait un **lien symbolique** de cette archive en le **nommant à la manière Debian**, c'est-à-dire *ghostwriter_1.6.2.orig.tar.gz* (nommage que Debian emplois pour les sources non encore debianisées donc n'ayant pas subi de changement/ajout du dossier debian). De là, ils ont **décompressé l'archive symbolique** dont le dossier résultant a pour nom *ghostwriter-1.6.2.orig*, ils l'ont **copié** en supprimant le *.orig* du nom et ils lui ont **déposé notre dossier** *debian* de notre build précédent. Mais c'est pas tout, les outils ont **nettoyé ce dossier** (debian) des fichiers résultants de la compilation et ont **complété** le *changelog*:

    ~/Paquets/ghostwriter/ghostwriter-1.6.2/debian$ cat changelog 
    ghostwriter (1.6.2-1) UNRELEASED; urgency=medium
    
    * New upstream release
    
    -- Sebastien CHAVAUX <seb95.scou@gmail.com>  Fri, 20 Apr 2018 23:21:31 +0200

    ghostwriter (1.6.0-1~schav1) unstable; urgency=low
    
    * package for Debian

    [ wereturtle ]
    * New upstream release.

    -- Sebastien CHAVAUX <seb95.scou@gmail.com>  Fri, 20 Apr 2018 19:21:47 +0200

    ghostwriter (1.5.0+ds2-1ppa2~trusty1) trusty; urgency=low

    * Dependency fix for Artful Aardvark.

    -- wereturtle <wereturtledev@gmail.com>  Thu, 31 Aug 2017 23:00:00 -0700

 
Maintenant que cet aparté est fini, il ne reste plus qu'a lancer la compilation avec `debuild`:

    ~/Paquets/ghostwriter/ghostwriter-1.6.2/debian$ debuild
    [....]
    Now running lintian...
    W: ghostwriter source: maintainer-also-in-uploaders
    W: ghostwriter: command-in-menu-file-and-desktop-file ghostwriter usr/share/menu/ghostwriter:7
    Finished running lintian.
    Now signing changes and any dsc files...
    signfile dsc ghostwriter_1.6.2-1.dsc xxxxxxxxxxxxxxxxxxxxxx

    fixup_buildinfo ghostwriter_1.6.2-1.dsc ghostwriter_1.6.2-1_amd64.buildinfo
    signfile buildinfo ghostwriter_1.6.2-1_amd64.buildinfo xxxxxxxxxxxxxxxxxxxxxxx

    fixup_changes dsc ghostwriter_1.6.2-1.dsc ghostwriter_1.6.2-1_amd64.changes
    fixup_changes buildinfo ghostwriter_1.6.2-1_amd64.buildinfo ghostwriter_1.6.2-1_amd64.changes
    signfile changes ghostwriter_1.6.2-1_amd64.changes xxxxxxxxxxxxxxxxxxxxxx

    Successfully signed dsc, buildinfo, changes files
    
J'aurais pu comme pour la version 1.6.0, rajouter le préfixe ~schav1 à l'aide de `dch -r`:

    ~/Paquets/ghostwriter/ghostwriter-1.6.2/debian$ dch -r
    ghostwriter (1.6.2-1~schav1) unstable; urgency=medium
    
    * New upstream release
    
    -- Sebastien CHAVAUX <seb95.scou@gmail.com>  Sat, 21 Apr 2018 00:36:52 +0200
    
    ghostwriter (1.6.0-1~schav1) unstable; urgency=low
    
    * package for Debian
    
    [ wereturtle ]
    * New upstream release.
    
    -- Sebastien CHAVAUX <seb95.scou@gmail.com>  Fri, 20 Apr 2018 19:21:47 +0200
    
Nous auront donc nos paquets et nos fichiers d’après build:

    ~/Paquets/ghostwriter$ ls 
    ghostwriter-1.6.0                           ghostwriter_1.6.2-1_amd64.build             ghostwriter_1.6.2-1~schav1_amd64.deb
    ghostwriter_1.6.0-1~schav1_amd64.build      ghostwriter_1.6.2-1_amd64.buildinfo         ghostwriter_1.6.2-1~schav1.debian.tar.xz
    ghostwriter_1.6.0-1~schav1_amd64.buildinfo  ghostwriter_1.6.2-1_amd64.changes           ghostwriter_1.6.2-1~schav1.dsc
    ghostwriter_1.6.0-1~schav1_amd64.changes    ghostwriter_1.6.2-1_amd64.deb               ghostwriter-1.6.2.orig
    ghostwriter_1.6.0-1~schav1_amd64.deb        ghostwriter_1.6.2-1.debian.tar.xz           ghostwriter_1.6.2.orig.tar.gz
    ghostwriter_1.6.0-1~schav1.debian.tar.xz    ghostwriter_1.6.2-1.dsc                     ghostwriter-dbgsym_1.6.0-1~schav1_amd64.deb
    ghostwriter_1.6.0-1~schav1.dsc              ghostwriter_1.6.2-1~schav1_amd64.build      ghostwriter-dbgsym_1.6.2-1_amd64.deb
    ghostwriter_1.6.0.orig.tar.gz               ghostwriter_1.6.2-1~schav1_amd64.buildinfo  ghostwriter-dbgsym_1.6.2-1~schav1_amd64.deb
    ghostwriter-1.6.2                           ghostwriter_1.6.2-1~schav1_amd64.changes    v1.6.2.tar.gz

    
On peut voir les fichiers en rapport avec la version 1.6.0 *débianisé* par votre serviteur, ceux de Ubuntu (les originaux) ne sont plus là ayant été mit à la corbeille, ceux de la version 1.6.2 avec et sans le préfixe de mes paquets personnels (~schav1).
