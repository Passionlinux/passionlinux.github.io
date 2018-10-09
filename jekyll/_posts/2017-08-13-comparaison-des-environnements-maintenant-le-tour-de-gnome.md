---
title: Comparaison des environnements, maintenant le tour de GNOME.
date: 2017-08-13 18:58
layout: post
---

![](http://download.tuxfamily.org/passionlinux//2017/08/Gnomelogo.svg_-247x300.png){.aligncenter
.wp-image-1473 .size-medium width="247" height="300"} Je ne voulais pas
faire GNOME dans mes petits tests de consommation, en fin de compte, je
profite d'avoir chassé jusqu'au dernier paquet et librairie de mon KDE
pour changer de bureau. Ce qui m'a un peu décidé c'est ce petit
désagréable soucis d’artefacts qui revient régulièrement même si moins
présent depuis [le changement dans les
configurations](http://passiongnulinux.tuxfamily.org/2017/07/27/xfce-ou-kde-plasma-5-2/)
du rendu de la composition. Ce qui m'aide aussi à faire ce passage,
c'est un peu le raz le bol des programmes certes complets mais complexes
avec des configurations dans tous les sens, j'aime au contraire ce côté
propre de l'interface de GNOME, surtout avec une extension
[Topicons](https://extensions.gnome.org/extension/495/topicons/) qui me
permet de parer à cette drôle d'idée de trouver pratique d'avoir les
icônes des applications ouvertes à l'opposé des icônes du réseau et du
son... et déplace les indicateurs (Deluge, Transmission, HexChat, …) du
tiroir de messagerie situé en bas à gauche, vers la barre supérieure.
[![](http://download.tuxfamily.org/passionlinux//2017/08/topicons.png){.aligncenter
.size-full .wp-image-1472 width="217"
height="104"}](http://download.tuxfamily.org/passionlinux//2017/08/topicons.png)  
<!--more-->  
Alors l'installation est faite via un simple:

    apt install task-gnome-desktop

Ce qui m'installe l'ensemble du bureau GNOME, avec des logiciels choisis
comme Firefox ou Libreoffice.

    root@debiacerlinux:/home/sebastien# apt install task-gnome-desktop Lecture des listes de paquets... Fait Construction de l'arbre des dépendances Lecture des informations d'état... Fait Les NOUVEAUX paquets suivants seront installés :  apg argyll argyll-ref baobab brasero brasero-cdrkit brasero-common chrome-gnome-shell dleyna-server eog evolution  evolution-common evolution-data-server evolution-data-server-common evolution-plugins file-roller five-or-more folks-common  four-in-a-row gdm3 gedit gedit-common gedit-plugins gir1.2-accountsservice-1.0 gir1.2-champlain-0.12 gir1.2-clutter-gst-3.0  gir1.2-evince-3.0 gir1.2-gdata-0.0 gir1.2-gdesktopenums-3.0 gir1.2-gdm-1.0 gir1.2-geoclue-2.0 gir1.2-geocodeglib-1.0  gir1.2-gepub-0.4 gir1.2-gfbgraph-0.2 gir1.2-git2-glib-1.0 gir1.2-gmenu-3.0 gir1.2-gnomebluetooth-1.0 gir1.2-gnomedesktop-3.0  gir1.2-gnomekeyring-1.0 gir1.2-goa-1.0 gir1.2-grilo-0.3 gir1.2-gtkchamplain-0.12 gir1.2-gtkclutter-1.0 gir1.2-gtksource-3.0  gir1.2-gucharmap-2.90 gir1.2-gweather-3.0 gir1.2-javascriptcoregtk-4.0 gir1.2-lokdocview-0.1 gir1.2-mediaart-2.0  gir1.2-mutter-3.0 gir1.2-networkmanager-1.0 gir1.2-nmgtk-1.0 gir1.2-peas-1.0 gir1.2-polkit-1.0 gir1.2-rb-3.0 gir1.2-rest-0.7  gir1.2-secret-1 gir1.2-telepathyglib-0.12 gir1.2-telepathylogger-0.2 gir1.2-totem-1.0 gir1.2-totem-plparser-1.0  gir1.2-tracker-1.0 gir1.2-upowerglib-1.0 gir1.2-webkit2-4.0 gir1.2-zpj-0.0 gjs gkbd-capplet gnome gnome-accessibility-themes  gnome-backgrounds gnome-bluetooth gnome-calculator gnome-calendar gnome-characters gnome-chess gnome-clocks gnome-color-manager  gnome-contacts gnome-control-center gnome-control-center-data gnome-core gnome-dictionary gnome-disk-utility gnome-documents  gnome-font-viewer gnome-games gnome-getting-started-docs gnome-keyring gnome-klotski gnome-logs gnome-mahjongg gnome-maps  gnome-menus gnome-mines gnome-music gnome-nibbles gnome-online-accounts gnome-online-miners gnome-robots gnome-screenshot  gnome-session gnome-session-bin gnome-session-common gnome-settings-daemon gnome-shell gnome-shell-common gnome-shell-extensions  gnome-software gnome-software-common gnome-sound-recorder gnome-sudoku gnome-sushi gnome-system-monitor gnome-taquin  gnome-terminal gnome-terminal-data gnome-tetravex gnome-themes-standard gnome-themes-standard-data gnome-tweak-tool  gnome-user-share gnome-weather grilo-plugins-0.3 gvfs-backends hitori hoichess iagno libapache2-mod-dnssd libappstream-glib8  libavahi-gobject0 libavahi-ui-gtk3-0 libbrasero-media3-1 libburn4 libcacard0 libcamel-1.2-59 libchamplain-0.12-0  libchamplain-gtk-0.12-0 libcolord-gtk1 libcryptui0a libdleyna-connector-dbus-1.0-1 libdleyna-core-1.0-3 libdmapsharing-3.0-2  libebackend-1.2-10 libebook-1.2-16 libebook-contacts-1.2-2 libecal-1.2-19 libedata-book-1.2-25 libedata-cal-1.2-28  libedataserver-1.2-22 libedataserverui-1.2-1 libevolution libexempi3 libfolks-eds25 libfolks-telepathy25 libfolks25  libfreerdp-cache1.1 libfreerdp-codec1.1 libfreerdp-common1.1.0 libfreerdp-core1.1 libfreerdp-crypto1.1 libfreerdp-gdi1.1  libfreerdp-locale1.1 libfreerdp-primitives1.1 libfreerdp-utils1.1 libfwupd1 libgail-3-0 libgcab-1.0-0 libgdata-common libgdata22  libgdict-1.0-10 libgdict-common libgdm1 libgeocode-glib0 libgepub0 libgexiv2-2 libgfbgraph-0.2-0 libgit2-glib-1.0-0 libgjs0e  libgmime-2.6-0 libgnome-autoar-0-0 libgnome-autoar-common libgnome-autoar-gtk-0-0 libgnome-bluetooth13 libgnome-games-support-1-2  libgnome-games-support-common libgnome-keyring-common libgnome-keyring0 libgnome-menu-3-0 libgnomekbd-common libgnomekbd8  libgoa-1.0-0b libgoa-1.0-common libgoa-backend-1.0-1 libgom-1.0-0 libgom-1.0-common libgrilo-0.3-0 libgsf-1-114 libgsf-1-common  libgsf-bin libgsound0 libgspell-1-1 libgspell-1-common libgtk-vnc-2.0-0 libgtksourceview-3.0-1 libgtksourceview-3.0-common  libgtkspell3-3-0 libgucharmap-2-90-7 libgupnp-av-1.0-2 libgupnp-dlna-2.0-3 libgvnc-1.0-0 libgweather-3-6 libgweather-common  libiptcdata0 libisofs6 libjte1 liblibreofficekitgtk liblua5.3-0 libmediaart-2.0-0 libmission-control-plugins0 libmozjs-24-0  libmusicbrainz5-2 libmutter0i libnatpmp1 libnm-glib4 libnm-gtk0 libnm-util2 libnma0 libnss-myhostname liboauth0 libosinfo-1.0-0  libpam-gnome-keyring libpeas-1.0-0 libpeas-common libphodav-2.0-0 libphodav-2.0-common libphonenumber7 libpst4 libqqwing2v5  libquvi-0.9-0.9.3 libquvi-scripts-0.9 libreoffice-evolution libreoffice-gnome libreoffice-gtk3 libreofficekit-data  librhythmbox-core10 librygel-core-2.6-2 librygel-db-2.6-2 librygel-renderer-2.6-2 librygel-renderer-gst-2.6-2  librygel-server-2.6-2 libspice-client-glib-2.0-8 libspice-client-gtk-3.0-5 libtelepathy-glib0 libtelepathy-logger3  libtotem-plparser-common libtotem-plparser18 libtotem0 libtracker-control-1.0-0 libtracker-miner-1.0-0 libtracker-sparql-1.0-0  libusbredirhost1 libusbredirparser1 libwinpr-crt0.1 libwinpr-crypto0.1 libwinpr-dsparse0.1 libwinpr-environment0.1  libwinpr-file0.1 libwinpr-handle0.1 libwinpr-heap0.1 libwinpr-input0.1 libwinpr-interlocked0.1 libwinpr-library0.1  libwinpr-path0.1 libwinpr-pool0.1 libwinpr-registry0.1 libwinpr-rpc0.1 libwinpr-sspi0.1 libwinpr-synch0.1 libwinpr-sysinfo0.1  libwinpr-thread0.1 libwinpr-utils0.1 libxcb-res0 libytnef0 libzapojit-0.0-0 lightsoff lua-bitop lua-expat lua-json lua-lpeg  lua-socket mousetweaks mutter mutter-common nautilus nautilus-data nautilus-sendto network-manager-gnome osinfo-db p11-kit  p11-kit-modules polari python-cffi-backend python-cryptography python-enum34 python-gi python-idna python-ipaddress  python-openssl python-pyasn1 python-requests python-urllib3 python3-mako python3-markupsafe quadrapassel realmd rhythmbox  rhythmbox-data rhythmbox-plugin-cdrecorder rhythmbox-plugins rygel rygel-playbin rygel-tracker seahorse seahorse-daemon shotwell  shotwell-common spice-client-glib-usb-acl-helper swell-foop tali task-gnome-desktop telepathy-idle telepathy-logger  telepathy-mission-control-5 totem totem-common totem-plugins tracker tracker-extract tracker-gui tracker-miner-fs  transmission-common transmission-gtk unoconv vinagre vino xdg-user-dirs-gtk xwayland 0 mis à jour, 347 nouvellement installés, 0 à enlever et 1 non mis à jour. Il est nécessaire de prendre 298 Mo dans les archives. Après cette opération, 876 Mo d'espace disque supplémentaires seront utilisés.

Un bon paquet de programmes:), je poursuis avec mon éternel feuille sur
les consommations des applications:

    htop démarrage: 0.728 Go htop avec le gestionnaire de fichiers, 2 consoles (terminal GNOME), Amule, Deluge, Hexchat et Thunderbird de lancé: 1.4 Go gestionnaire système de gnome: 1.0 -> 1.6 Go moniteur système xfce: 0.870 -> 1.4 Go gnome-shell (442+61) 503 Mo gnome-setting-daemon (33+25) 58 Mo gnome-session (9+11) 20 Mo gedit 47 Mo moniteur-systeme 46 Mo nautilus 55 Mo terminal 34 Mo amule 43 Mo deluge 90 Mo hexchat 50 Mo thunderbird 206 Mo

[![](http://download.tuxfamily.org/passionlinux//2017/08/Capture-décran-de-2017-08-12-17-27-00-1024x337.png){.aligncenter
.size-large .wp-image-1475 width="840"
height="276"}](http://download.tuxfamily.org/passionlinux//2017/08/Capture-décran-de-2017-08-12-17-27-00.png)
[![](http://download.tuxfamily.org/passionlinux//2017/08/Capture-décran-de-2017-08-12-17-27-40-1024x337.png){.aligncenter
.size-large .wp-image-1477 width="840"
height="276"}](http://download.tuxfamily.org/passionlinux//2017/08/Capture-décran-de-2017-08-12-17-27-40.png)
[![](http://download.tuxfamily.org/passionlinux//2017/08/Capture-décran-de-2017-08-12-17-39-13-1024x337.png){.aligncenter
.size-large .wp-image-1478 width="840"
height="276"}](http://download.tuxfamily.org/passionlinux//2017/08/Capture-décran-de-2017-08-12-17-39-13.png)
Résultats: GNOME est de mon point de vue le plus lourd des bureaux
testés au même titre que Cinnamon, il est à la limite de faire pire que
KDE mais parait plus vivace dans le lancement des applications, ces
dernières se lancent bien plus rapidement que sous KDE, où j'attends
plusieurs secondes pour la moindre petite application alors que là c'est
instantané! C'est de la sensation mais après tout c'est ce qui compte.
Ça fait un moment que je pense être sur la distribution qui me va comme
un gant, allant même à vouloir en changer pour ne pas tomber dans la
routine ou ne plus savoir utiliser autre chose, sous entendre utiliser
autre chose qu'une distribution à base Debian. Je ne me pose plus la
question, j'ai un autre soucis qui permet de ne plus m'occuper de cette
question, c'est celui du bureau, lequel me correspond le mieux?
Autrement dit, après autant d'années passées sur KDE, est-ce vraiment le
choix qui me correspond vu le passif de ce bureau, c'est-à-dire
changement pour changer et limite casser les habitudes? Manque de
continuité entre les versions, configuration qui casse ou n'est plus
compatible avec la version suivante ou dans une même version avec
changements mineurs... La complexité de KDE ne me convient plus, je suis
dans une optique d'avoir juste un truc bien fini et/ou du moins qui est
pensé pour être simple à l'utilisation, dans ce cas Xfce mais surtout
GNOME correspondent mieux à ce besoin.
