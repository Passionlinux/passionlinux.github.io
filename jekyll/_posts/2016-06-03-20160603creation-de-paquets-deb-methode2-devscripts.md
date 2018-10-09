---
title: Création de paquets DEB (méthode2 devscripts)
date: 2016-06-03 12:19
layout: post
---

    Cette fois ci, on va se simplifier la vie:

1/ Pour commencer, nous faisons un dossier avec le nom du paquet, par
exemple pour playonlinux:  
`$ mkdir /home/sebastien/packaging/playonlinux  $ cd /home/sebastien/packaging/playonlinux`

2/ On télécharge les sources debian du paquet:  
`$ apt-get source playonlinux`

<small>`Lecture des listes de paquets... Fait  Construction de l'arbre des dépendances         Lecture des informations d'état... Fait  Note : la maintenance du paquet de « playonlinux » est réalisée dans le système de suivi de versions « Svn » à l'adresse :  svn://anonscm.debian.org/pkg-games/packages/trunk/playonlinux/  Nécessité de prendre 3 211 ko dans les sources.  Réception de : 1 http://ftp.fr.debian.org/debian/ testing/contrib playonlinux 4.2.6-1 (dsc) [1 978 B]  Réception de : 2 http://ftp.fr.debian.org/debian/ testing/contrib playonlinux 4.2.6-1 (tar) [3 203 kB]  Réception de : 3 http://ftp.fr.debian.org/debian/ testing/contrib playonlinux 4.2.6-1 (diff) [6 684 B]  3 211 ko réceptionnés en 4s (780 ko/s)    dpkg-source: info: extraction de playonlinux dans playonlinux-4.2.6  dpkg-source: info: extraction de playonlinux_4.2.6.orig.tar.gz  dpkg-source: info: extraction de playonlinux_4.2.6-1.debian.tar.xz  dpkg-source: info: mise en place de set_debian_env.diff  dpkg-source: info: mise en place de remove_binary_plugin.diff`</small>

3/ On télécharge en ROOT, les paquets nécessaire pour construire ce
paquet:  
`# apt-get build-dep playonlinux`

4/ On se remet en simple utilisateur, puis on rentre dans le dossier des
sources debian:  
`$ cd '/home/sebastien/packaging/playonlinux/playonlinux-4.2.6'`

5/ On va dans voir le fichier /debian/watch qui permet, si bien fait, de
faire tout automatiquement avec la commande uscan. Les sources mises à
jour seront automatiquement recherchées, téléchargées, et la commande
uupdate sera exécutée.  
`$ uscan`

<small>`playonlinux: Newer version (4.2.8) available on remote site:    https://www.playonlinux.com/script_files/PlayOnLinux/4.2.8/PlayOnLinux_4.2.8.tar.gz    (local version is 4.2.6)  Successfully downloaded updated package PlayOnLinux_4.2.8.tar.gz  Successfully symlinked ../PlayOnLinux_4.2.8.tar.gz to ../playonlinux_4.2.8.orig.tar.gz.  New Release will be 4.2.8-1.  -- Untarring the new sourcecode archive ../playonlinux_4.2.8.orig.tar.gz  Unpacking the debian/ directory from version 4.2.6-1 worked fine.  Remember: Your current directory is the OLD sourcearchive!  Do a "cd ../playonlinux-4.2.8" to see the new package`</small>

Si la commande uscan télécharge les sources mises à jour mais n'exécute
pas la commande uupdate, vous devriez corriger le fichier debian/watch
pour avoir debian uupdate après l'URL.

6/ Normalement tout a été fait si le fichier watch est bien fait, du
coup reste plus qu'a fabriquer le deb:  
`$ cd '/home/sebastien/packaging/playonlinux/playonlinux-4.2.8'  $ debuild`

<small>`dpkg-buildpackage -rfakeroot -D -us -uc  dpkg-buildpackage: paquet source playonlinux  dpkg-buildpackage: version source 4.2.8-1  dpkg-buildpackage: distribution source UNRELEASED  dpkg-buildpackage: source changé par Sebastien CHAVAUX <sebastien@debianlinux.schavfr>   dpkg-source --before-build playonlinux-4.2.8  dpkg-buildpackage: architecture hôte amd64  dpkg-source: info: mise en place de set_debian_env.diff  dpkg-source: info: mise en place de remove_binary_plugin.diff   fakeroot debian/rules clean  dh clean --with python2     dh_testdir     dh_auto_clean     dh_clean   dpkg-source -b playonlinux-4.2.8  dpkg-source: info: utilisation du format source « 3.0 (quilt) »  dpkg-source: info: construction de playonlinux en utilisant le ./playonlinux_4.2.8.orig.tar.gz existant  dpkg-source: info: construction de playonlinux dans playonlinux_4.2.8-1.debian.tar.xz  dpkg-source: info: construction de playonlinux dans playonlinux_4.2.8-1.dsc   debian/rules build  dh build --with python2     dh_testdir     dh_auto_configure     debian/rules override_dh_auto_build-indep  make[1]: Entering directory '/home/sebastien/packaging/playonlinux/playonlinux-4.2.8'  convert -monitor -resize 32x32 /home/sebastien/packaging/playonlinux/playonlinux-4.2.8/etc/playonlinux.png /home/sebastien/packaging/playonlinux/playonlinux-4.2.8/playonlinux.xpm  Load/Image//home/sebastien/packaging/playonlinux/playonlinux-4.2.8/etc[playonlinux.png]: 0 of 128, 00% cLoad/Image//home/sebastien/packaging/playonlinux/playonlinux-4.2.8/etc[playonlinux.png]: 1 of 128, 00% cLoad/Image//home/sebastien/packaging/playonlinux/playonlinux-4.2.8/etc[playonlinux.png]: 2 of 128, 01% cLoad/Image//home/sebastien/packaging/playonlinux/playonlinux-4.2.8/etc[playonlinux.png]: 3 of 128, 02% cLoad/Image//home/sebastien/packaging/playonlinux/playonlinux-4.2.8/etc[playonlinux.png]: 4 of 128, 03% c......  Save/Image//home/sebastien/packaging/playonlinux/playonlinux-4.2.8[playonlinux.xpm]: 30 of 32, 96% complSave/Image//home/sebastien/packaging/playonlinux/playonlinux-4.2.8[playonlinux.xpm]: 31 of 32, 100% complete  make[1]: Leaving directory '/home/sebastien/packaging/playonlinux/playonlinux-4.2.8'     dh_auto_test   fakeroot debian/rules binary  dh binary --with python2     dh_testroot     dh_prep     dh_auto_install     debian/rules override_dh_install  make[1]: Entering directory '/home/sebastien/packaging/playonlinux/playonlinux-4.2.8'  dh_install  chmod +x debian/playonlinux/usr/share/playonlinux/bash/startup_after_server  chmod +x debian/playonlinux/usr/share/playonlinux/bash/read_pc_cd  chmod +x debian/playonlinux/usr/share/playonlinux/bash/find_python  make[1]: Leaving directory '/home/sebastien/packaging/playonlinux/playonlinux-4.2.8'     dh_installdocs     dh_installchangelogs     dh_installman     dh_python2  W: dh_python2:479: Please add dh-python package to Build-Depends     dh_installmenu     dh_perl     dh_link     dh_compress     dh_fixperms     dh_installdeb     dh_gencontrol  dpkg-gencontrol: avertissement: champ Depends du paquet playonlinux : variable de substitution inconnue ${shlibs:Depends}     dh_md5sums     dh_builddeb  dpkg-deb : construction du paquet « playonlinux » dans « ../playonlinux_4.2.8-1_all.deb ».   dpkg-genchanges  >../playonlinux_4.2.8-1_amd64.changes  dpkg-genchanges: inclusion du code source original dans l'envoi (« upload »)   dpkg-source --after-build playonlinux-4.2.8  dpkg-source: info: retrait de remove_binary_plugin.diff  dpkg-source: info: retrait de set_debian_env.diff  dpkg-buildpackage: envoi complet (inclusion du code source d'origine)  Now running lintian...  W: playonlinux source: changelog-should-mention-nmu  W: playonlinux source: source-nmu-has-incorrect-version-number 4.2.8-1  Finished running lintian.  Now signing changes and any dsc files...   signfile playonlinux_4.2.8-1.dsc 0x100F502F`</small>

<small>`You need a passphrase to unlock the secret key for  user: "Sebastien XXXX (seb95) <xxxxx@xxx.xx>"  2048-bit RSA key, ID 100F502F, created 2015-05-19`</small>

<small>`                     signfile playonlinux_4.2.8-1_amd64.changes 0x100F502F`</small>

<small>`You need a passphrase to unlock the secret key for  user: "Sebastien XXXXXX (seb95) <xxxx.xxx@xx.xx>"  2048-bit RSA key, ID 100F502F, created 2015-05-19`</small>

<small>`                    Successfully signed dsc and changes files`</small>

On aura de jolies paquets deb, et pour finir un coup de `debuild clean`.
