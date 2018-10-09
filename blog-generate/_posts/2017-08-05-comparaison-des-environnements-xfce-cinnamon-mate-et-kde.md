---
title: Comparaison des environnements Xfce, Cinnamon, Mate et KDE
date: 2017-08-05 18:17
layout: post
---

Je ne savais pas quoi faire de mon petit temps libre alors j'ai pris ma
Debian et j'ai installé les différents bureaux, entre autre Cinnamon,
KDE, Mate et Xfce, pour voir le nombre de paquets installé par défaut
avec leurs méta-paquets sur une Debian. J'ai lâché les bureaux GNOME et
les autres petits pour la simple raison qu'ils ne m’intéressaient pas de
les comparer soit parce que je les connais ou que je ne compte pas les
utiliser. Alors le test n'est pas fait proprement, c’était juste pour me
donner une idée du nombre de paquets installé et savoir à peu prés
l'utilisation des bureaux dont je ne suis pas ou peu habitué à utiliser,
savoir aussi la consommation de ressources approximatives des différents
bureaux. Pour ce faire, je n'ai pas eu le courage de désinstaller le KDE
qui de base accompagne ma Debian donc je ne pourrais pas dire combien de
paquets et de places utilisés à l'installation de cet environnement.
Pour les autres, pas de soucis, ça a été fait notamment j'ai désinstallé
totalement Xfce pour son test, j'ai fait des aperçus de chacun avec
toutes mes applications habituelles sauf de kde qui est pris lors d'une
compilation(rétro-portage ou rebuild venant de Sid pour Stable) de
paquet Deb. Les différents tests sont effectués sur ma machine
personnelle et non dans une VM, ainsi je n'ai pas utilisé que les
différents moniteurs systèmes des environnements mais Htop en plus pour
être sur des chiffres donnés, c'est comme ça que j'ai vu que celui de
Xfce était celui qui collait le plus à ce que donnait Htop. Dernière
chose, pour tous les environnements, il reste des applications KDE comme
Kalarm ou Kaccessible qui restaient ouverte, c'est normal c’était
recherché, aussi pour ne pas trop fausser, je redémarre à chaque test le
PC, pour éviter de garder des services en tache de fond d'autres
bureaux. J'ai donc copié dans un fichier la sortie d'Apt et ensuite fait
un rapport des différentes applications layout de chaque environnement et
de deux ou trois applications que j'ai l'habitude d'utiliser. Alors
pourquoi ce test, c'est simple, pour mon utilisation je suis avec KDE et
Xfce, je ne pense pas en changer surtout à la vue des résultats que j'ai
eu, ensuite je voulais voir si d'autres bureaux ne pouvaient pas mieux
convenir à ceux dont j'installe Debian notamment si Mate était si léger
que ce qu'on pouvait entendre par rapport à Xfce.  
<!--more-->  
Je pense avoir rien oublié donc on peut commencer ;). On va le faire par
ordre alphabétique, commençons donc par Cinnamon:  

> root@debiacerlinux:/home/sebastien\# **apt install
> cinnamon-desktop-environment cinnamon-l10n** Lecture des listes de
> paquets... Fait Construction de l'arbre des dépendances Lecture des
> informations d'état... Fait The following additional packages will be
> installed: .... **Les NOUVEAUX paquets suivants seront installés :**
> apg blueman brasero brasero-cdrkit brasero-common cinnamon
> cinnamon-common cinnamon-control-center cinnamon-control-center-data
> cinnamon-core cinnamon-desktop-data cinnamon-desktop-environment
> cinnamon-l10n cinnamon-screensaver cinnamon-screensaver-x-plugin
> cinnamon-session cinnamon-session-common cinnamon-settings-daemon cjs
> dleyna-server dmz-cursor-theme eog file-roller five-or-more
> four-in-a-row gdebi gdebi-core gedit gedit-common gedit-plugins
> gir1.2-accountsservice-1.0 gir1.2-cinnamondesktop-3.0
> gir1.2-clutter-gst-3.0 gir1.2-cmenu-3.0 gir1.2-cvc-1.0
> gir1.2-evince-3.0 gir1.2-gdesktopenums-3.0 gir1.2-git2-glib-1.0
> gir1.2-gkbd-3.0 gir1.2-gnomebluetooth-1.0 gir1.2-gnomedesktop-3.0
> gir1.2-gnomekeyring-1.0 gir1.2-gtkclutter-1.0 gir1.2-gucharmap-2.90
> gir1.2-javascriptcoregtk-3.0 gir1.2-meta-muffin-0.0
> gir1.2-networkmanager-1.0 gir1.2-nmgtk-1.0 gir1.2-peas-1.0
> gir1.2-polkit-1.0 gir1.2-rb-3.0 gir1.2-secret-1 gir1.2-upowerglib-1.0
> gir1.2-xapp-1.0 gir1.2-xkl-1.0 gist gkbd-capplet gksu
> gnome-accessibility-themes gnome-backgrounds gnome-bluetooth
> gnome-calculator gnome-chess gnome-control-center
> gnome-control-center-data gnome-font-viewer gnome-games gnome-keyring
> gnome-klotski gnome-mahjongg gnome-mines gnome-nibbles
> gnome-online-accounts gnome-robots gnome-screenshot
> gnome-settings-daemon gnome-sudoku gnome-sushi gnome-system-monitor
> gnome-taquin gnome-terminal gnome-terminal-data gnome-tetravex
> gnome-themes-standard gnome-themes-standard-data gnome-user-share
> gnote gvfs-backends hamster-applet hddtemp hitori hoichess iagno inxi
> iso-flags-png-320x240 libapache2-mod-dnssd libavahi-gobject0
> libavahi-ui-gtk3-0 libbonobo2-0 libbonobo2-common libbonoboui2-0
> libbonoboui2-common libbrasero-media3-1 libburn4 libcacard0
> libcinnamon-control-center1 libcinnamon-desktop4 libcinnamon-menu-3-0
> libcjs0 libcolord-gtk1 libcscreensaver0 libcvc0
> libdleyna-connector-dbus-1.0-1 libdleyna-core-1.0-3
> libdmapsharing-3.0-2 libexempi3 libfarstream-0.2-5 libgail-3-0
> libgdata-common libgdata22 libgeocode-glib0 libgexiv2-2
> libgit2-glib-1.0-0 libgjs0e libgksu2-0 libgmime-2.6-0 libgnome-2-0
> libgnome-autoar-0-0 libgnome-autoar-common libgnome-bluetooth13
> libgnome-games-support-1-2 libgnome-games-support-common
> libgnome-keyring-common libgnome-keyring0 libgnome2-common
> libgnomecanvas2-0 libgnomecanvas2-common libgnomekbd-common
> libgnomekbd8 libgnomeui-0 libgnomeui-common libgoa-1.0-0b
> libgoa-1.0-common libgoa-backend-1.0-1 libgrilo-0.3-0 libgspell-1-1
> libgspell-1-common libgtk-vnc-2.0-0 libgtkspell3-3-0
> libgucharmap-2-90-7 libgupnp-av-1.0-2 libgupnp-dlna-2.0-3
> libgvnc-1.0-0 libgweather-3-6 libgweather-common libiptcdata0
> libisofs6 libjavascriptcoregtk-3.0-0 libjte1 libmediaart-2.0-0
> libmozjs-24-0 libmuffin0 libmusicbrainz5-2 libnemo-extension1
> libnm-glib-vpn1 libnm-glib4 libnm-gtk0 libnm-util2 libnma0
> libnss-myhostname liboauth0 liborbit-2-0 liborbit2
> libpam-gnome-keyring libpango1.0-0 libpeas-1.0-0 libpeas-common
> libphodav-2.0-0 libphodav-2.0-common libpurple-bin libpurple0
> libqqwing2v5 libquvi-0.9-0.9.3 libquvi-scripts-0.9 librhythmbox-core10
> librygel-core-2.6-2 librygel-db-2.6-2 librygel-renderer-2.6-2
> librygel-server-2.6-2 libspice-client-glib-2.0-8
> libspice-client-gtk-3.0-5 libtelepathy-glib0 libtotem-plparser-common
> libtotem-plparser18 libtracker-sparql-1.0-0 libusbredirhost1
> libusbredirparser1 libwnck-common libwnck22 libxapp1 libzephyr4
> lightsoff lua-bitop lua-expat lua-json lua-lpeg lua-socket
> mate-icon-theme mate-themes mousetweaks muffin muffin-common nautilus
> nautilus-data nemo nemo-data nemo-fileroller net-tools
> network-manager-gnome p11-kit p11-kit-modules pidgin pidgin-data
> python-gconf python-gnome2 python-pexpect python-ptyprocess
> python-pyorbit python-wnck python3-mako python3-markupsafe
> python3-setproctitle python3-xlib quadrapassel realmd rhythmbox
> rhythmbox-data rhythmbox-plugin-cdrecorder rhythmbox-plugins ruby-json
> rygel shotwell shotwell-common sound-juicer
> spice-client-glib-usb-acl-helper swell-foop tali vinagre vino
> xapps-common xdg-user-dirs-gtk xscreensaver-data
> xscreensaver-data-extra xscreensaver-gl xscreensaver-gl-extra **0 mis
> à jour, 255 nouvellement installés, 0 à enlever et 0 non mis à jour.**
> **Il est nécessaire de prendre 170 Mo dans les archives.** **Après
> cette opération, 607 Mo d'espace disque supplémentaires seront
> utilisés.** Souhaitez-vous continuer ? \[O/n\]
> </p>

Alors comment se passe le test, simplement j'installe l'environnement,
puis redémarre le PC et je choisis le bureau voulu. Htop étant déjà
installé, je le lance dans un terminal (celui qui va avec le bureau)
puis je lance le moniteur système (ou gestionnaire système), enfin je
lance mes applications habituelles pour les différents bureaux, c'est à
dire pour KDE, je lance Ktorrent, Konversation et Thunderbird (je lance
aussi par la suite Amule, Deluge et Hexchat), pour les bureaux à base de
Gtk, je lance uniquement Amule, Deluge et Hexchat. Pour chaque bureau,
je lance 2 consoles, le gestionnaire de fichiers ouvert sur
téléchargements, Amule, Deluge (remplacé dans un premier temps par
Ktorrent dans KDE) et Hexchat (remplacé dans un premier temps par
Konversation dans KDE). Une fois que j'ai testé le bureau, je lance les
différents moniteurs/gestionnaires système pour voir celui qui
s'approche le plus de Htop. Je mesure aussi pour chaque bureau, la
vitesse de lancement de celui-ci et le temps que prennent les
applications à leurs démarrages. Je compare dans un dernier temps, les
différentes applications attitrées à leurs environnements pour savoir un
peu la lourdeur du bureau et des applications qui vont avec. Voila la
petite capture d'écran avec toutes mes applications lancées.
[![](http://download.tuxfamily.org/passionlinux//2017/08/Capture-du-2017-08-03-01-21-16-1024x337.png){.aligncenter
.wp-image-1441 .size-large width="840"
height="276"}](http://download.tuxfamily.org/passionlinux//2017/08/Capture-du-2017-08-03-01-21-16.png)
Ce que j'ai noté pour ce bureau,  

> Cinnamon: htop donne 0.841Go et 0 Mo swap au démarrage puis 0.938Go
> une fois le gestionnaire de fichiers (Nemo), 2 consoles (terminal
> GNOME), Amule, Deluge et Hexchat de lancé. ksygard 0.793 (démarrage)
> -&gt; 0.877 Go (une fois amule, deluge, hexchat et thunderbird lancé)
> gestionnaire système de gnome 1.1 -&gt; 1.2 Go " moniteur système xfce
> 0.887 -&gt; 0.973 Go " gestionnaire système de mate 1.1 -&gt; 1.2 Go "
> cinnamon--replace 203 Mo cinnamon-killer-daemon 32 Mo
> cinnamon-launcher 29 Mo cinnamon-screensaver 46 Mo cinnamon-session 43
> Mo cinnamon-setting-daemon 52 Mo gedit 48 Mo moniteur systeme 46 Mo
> nemo 52 Mo terminal 38 Mo amule 59 Mo deluge 94 Mo hexchat 59 Mo
> thunderbird 235 Mo
> </p>

Pour Mate:  

> root@debiacerlinux:/home/sebastien\# **apt install
> mate-desktop-environment-extra** Lecture des listes de paquets... Fait
> Construction de l'arbre des dépendances Lecture des informations
> d'état... Fait The following additional packages will be installed:
> ... **Les NOUVEAUX paquets suivants seront installés :** atril
> atril-common blueman caja caja-common caja-extensions-common caja-gksu
> caja-image-converter caja-open-terminal caja-sendto caja-share
> caja-wallpaper cpufrequtils dconf-editor debian-mate-default-settings
> dmz-cursor-theme engrampa engrampa-common eom eom-common fonts-mathjax
> galculator gir1.2-mate-panel gksu gnome-keyring gvfs-backends hddtemp
> libapache2-mod-dnssd libatrildocument3 libatrilview3
> libcaja-extension1 libcpufreq0 libexempi3 libgail-3-0 libgdata-common
> libgdata22 libgksu2-0 libgnome-keyring-common libgnome-keyring0
> libgoa-1.0-0b libgoa-1.0-common libiw30 libjs-mathjax
> libmarco-private1 libmate-desktop-2-17 libmate-menu2
> libmate-panel-applet-4-1 libmate-sensors-applet-plugin0 libmate-slab0
> libmate-window-settings1 libmatedict6 libmatekbd-common libmatekbd4
> libmatemixer-common libmatemixer0 libmateweather-common
> libmateweather1 liboauth0 libopenobex2 libpam-gnome-keyring
> libpango1.0-0 libunique-3.0-0 marco marco-common mate-applets
> mate-applets-common mate-backgrounds mate-control-center
> mate-control-center-common mate-desktop mate-desktop-common
> mate-desktop-environment mate-desktop-environment-core
> mate-desktop-environment-extra mate-desktop-environment-extras
> mate-icon-theme mate-icon-theme-faenza mate-media mate-media-common
> mate-menus mate-notification-daemon mate-notification-daemon-common
> mate-panel mate-panel-common mate-polkit mate-polkit-common
> mate-power-manager mate-power-manager-common mate-screensaver
> mate-screensaver-common mate-sensors-applet mate-sensors-applet-common
> mate-session-manager mate-settings-daemon mate-settings-daemon-common
> mate-system-monitor mate-system-monitor-common mate-terminal
> mate-terminal-common mate-themes mate-user-guide mate-user-share
> mate-user-share-common mate-utils mate-utils-common menu-xdg mozo
> obex-data-server p11-kit p11-kit-modules pluma pluma-common
> python-crypto python-gobject python-ldb python-mate-menu
> python-requests python-samba python-tdb python-urllib3 samba-common
> samba-common-bin **0 mis à jour, 122 nouvellement installés, 0 à
> enlever et 0 non mis à jour.** **Il est nécessaire de prendre 136 Mo
> dans les archives.** **Après cette opération, 466 Mo d'espace disque
> supplémentaires seront utilisés.** Souhaitez-vous continuer ? \[O/n\]
> </p>

La petite capture qui va bien:
[![](http://download.tuxfamily.org/passionlinux//2017/08/Capture-du-2017-08-03-02-13-38-1024x337.png){.aligncenter
.wp-image-1445 .size-large width="840"
height="276"}](http://download.tuxfamily.org/passionlinux//2017/08/Capture-du-2017-08-03-02-13-38.png)  

> mate htop 0.670Go et 0 Mo swap 1.1 go (une fois tout lancé avec mes
> applications en plus) ksygard 0.656 -&gt; 0.937 Go gest de gnome 0.949
> -&gt; 1.2 Go gest de xfce 0.754 -&gt; 1.0 Go gest de mate 0.949 -&gt;
> 1.2 Go caja 62 Mo marco 38 Mo mate-panel 57 Mo mate-session 44 Mo
> mate-terminal 39 Mo mate-setting demon 34 Mo mate-volume 31 Mo
> mate-systeme moniteur 47 Mo mate-power 24 Mo mate-scrennsaver 19 Mo
> pluma 50 Mo amule 79 Mo deluge 93 Mo hexchat 59 Mo thunderbird 231 Mo
> </p>

Maintenant passons à Plasma, on n’oublie pas que je n'ai pas désinstallé
KDE de mon PC donc pas de liste exacte ni de place prise sur le disque
mais en gros l'installation du méta-paquet kde-full entraîne
l'installation des méta-paquets suivant:

-   

    <span class="nonvisual">dep:</span> [kde-plasma-desktop](https://packages.debian.org/stretch/kde-plasma-desktop) (&gt;= 5:92)
    :   bureau Plasma de KDE avec un ensemble minimal d'applications

-   

    <span class="nonvisual">dep:</span> [kde-standard](https://packages.debian.org/stretch/kde-standard) (&gt;= 5:92)
    :   bureau Plasma de KDE et applications standard

-   

    <span class="nonvisual">dep:</span> [kdeadmin](https://packages.debian.org/stretch/kdeadmin) (&gt;= 4:16.04.0)
    :   Outils d'administration système de la version officielle de KDE

-   

    <span class="nonvisual">dep:</span> [kdeartwork](https://packages.debian.org/stretch/kdeartwork) (&gt;= 4:15.08.0)
    :   thèmes, styles et graphismes de la version officielle de KDE

-   

    <span class="nonvisual">dep:</span> [kdeedu](https://packages.debian.org/stretch/kdeedu) (&gt;= 4:16.04.0)
    :   applications éducatives de la version officielle de KDE

-   

    <span class="nonvisual">dep:</span> [kdegames](https://packages.debian.org/stretch/kdegames) (&gt;= 4:16.04.0)
    :   Jeux issus de la version officielle de KDE

-   

    <span class="nonvisual">dep:</span> [kdegraphics](https://packages.debian.org/stretch/kdegraphics) (&gt;= 4:16.04.0)
    :   applications pour le graphisme de la version officielle de KDE

-   

    <span class="nonvisual">dep:</span> [kdemultimedia](https://packages.debian.org/stretch/kdemultimedia) (&gt;= 4:16.04.0)
    :   applications multimedia de la version officielle de KDE

-   

    <span class="nonvisual">dep:</span> [kdenetwork](https://packages.debian.org/stretch/kdenetwork) (&gt;= 4:16.04.0)
    :   applications réseau de la distribution officielle de KDE

-   

    <span class="nonvisual">dep:</span> [kdepim](https://packages.debian.org/stretch/kdepim) (&gt;= 4:16.04.0)
    :   applications de gestion d'informations personnelles (PIM) de la
        version officielle de KDE

-   

    <span class="nonvisual">dep:</span> [kdeutils](https://packages.debian.org/stretch/kdeutils) (&gt;= 4:16.04.0)
    :   utilitaires polyvalents fournis par la publication officielle de
        KDE

<!-- -->

-   

    <span class="nonvisual">rec:</span> [kdeaccessibility](https://packages.debian.org/stretch/kdeaccessibility) (&gt;= 4:16.04.0)
    :   paquets d'accessibilité officiels de KDE

-   

    <span class="nonvisual">rec:</span> [kdesdk](https://packages.debian.org/stretch/kdesdk) (&gt;= 4:16.04.0)
    :   ensemble d'outils de développement logiciel de la version
        officielle de KDE

-   

    <span class="nonvisual">rec:</span> [kdetoys](https://packages.debian.org/stretch/kdetoys) (&gt;= 4:16.04.0)
    :   jouets de bureau fournis par la publication officielle de KDE

-   

    <span class="nonvisual">rec:</span> [kdewebdev](https://packages.debian.org/stretch/kdewebdev) (&gt;= 4:16.04.0)
    :   applications de développement web de la version officielle KDE

<!-- -->

-   

    <span class="nonvisual">sug:</span> [calligra](https://packages.debian.org/stretch/calligra) (&gt;= 1:2.9.11)
    :   suite de productivité et création

-   

    <span class="nonvisual">sug:</span> [kde-l10n](https://packages.debian.org/stretch/kde-l10n) (&gt;= 4:16.04.0)
    :   paquet virtuel fourni par <span id="js_kde-l10n"
        class="p_js_elem">[\[montrer 55 paquets fournissant\]]()</span>

-   

    <span class="nonvisual">sug:</span> [xorg](https://packages.debian.org/stretch/xorg)
    :   Système X Window de X.Org

[![](http://download.tuxfamily.org/passionlinux//2017/08/Screenshot_20170726_223507-1024x337.png){.aligncenter
.wp-image-1446 .size-large width="840"
height="276"}](http://download.tuxfamily.org/passionlinux//2017/08/Screenshot_20170726_223507.png)
Par contre j'ai bien ma petite liste d'applications ouvertes avec leurs
consommations:  

> plasma5 htop 0.651 et 0 Mo swap 1.1 Go (une fois tout lancé avec mes
> applications en plus) ksygard 0.755 -&gt; 1.0 Go gest de gnome 1.0
> -&gt; 1.3 Go gest de xfce 0.866 -&gt; 1.1 Go gest de mate 1.0 -&gt;
> 1.3 Go dolphin 93 Mo kwin 107 Mo plasma 206 Mo konsole 86 Mo kwrite
> 113 Mo kate 119 Mo ktorrent 98 Mo konversation 88 Mo ksysguard 80 Mo
> amule 57 Mo deluge 94 Mo hexchat 62 Mo thunderbird 237 Mo
> </p>

Enfin, on termine avec Xfce:  

> root@debiacerlinux:/home/sebastien\# **apt install xfce4
> xfce4-goodies** Lecture des listes de paquets... Fait Construction de
> l'arbre des dépendances Lecture des informations d'état... Fait The
> following additional packages will be installed: .... **Les NOUVEAUX
> paquets suivants seront installés :** exo-utils gtk2-engines-xfce
> hddtemp libburn4 libexo-1-0 libexo-common libexo-helpers libgarcon-1-0
> libgarcon-common libisofs6 libjte1 libnotify-bin libthunarx-2-0
> libtumbler-1-0 libwnck-common libwnck22 libxfce4panel-2.0-4
> libxfce4ui-1-0 libxfce4ui-2-0 libxfce4ui-common libxfce4ui-utils
> libxfce4util-bin libxfce4util-common libxfce4util7 libxfconf-0-2
> light-locker lightdm mousepad orage ristretto thunar
> thunar-archive-plugin thunar-data thunar-media-tags-plugin
> thunar-volman tumbler tumbler-common xfburn xfce4 xfce4-appfinder
> xfce4-battery-plugin xfce4-clipman xfce4-clipman-plugin
> xfce4-cpufreq-plugin xfce4-cpugraph-plugin xfce4-datetime-plugin
> xfce4-dict xfce4-diskperf-plugin xfce4-fsguard-plugin
> xfce4-genmon-plugin xfce4-goodies xfce4-mailwatch-plugin
> xfce4-mount-plugin xfce4-netload-plugin xfce4-notes xfce4-notes-plugin
> xfce4-notifyd xfce4-panel xfce4-places-plugin xfce4-power-manager
> xfce4-power-manager-data xfce4-power-manager-plugins
> xfce4-pulseaudio-plugin xfce4-screenshooter xfce4-sensors-plugin
> xfce4-session xfce4-settings xfce4-smartbookmark-plugin
> xfce4-systemload-plugin xfce4-taskmanager xfce4-terminal
> xfce4-timer-plugin xfce4-verve-plugin xfce4-wavelan-plugin
> xfce4-weather-plugin xfce4-whiskermenu-plugin xfce4-xkb-plugin xfconf
> xfdesktop4 xfdesktop4-data xfwm4 **0 mis à jour, 81 nouvellement
> installés, 0 à enlever et 0 non mis à jour.** **Il est nécessaire de
> prendre 19,3 Mo dans les archives.** **Après cette opération, 75,4 Mo
> d'espace disque supplémentaires seront utilisés.**
> </p>

[![](http://download.tuxfamily.org/passionlinux//2017/08/Capture-décran_2017-08-05_15-27-00-1024x337.png){.aligncenter
.wp-image-1449 .size-large width="840"
height="276"}](http://download.tuxfamily.org/passionlinux//2017/08/Capture-décran_2017-08-05_15-27-00.png)
Et la liste d'applications:  

> xfce htop 0.421 Go et 0 Mo Swap puis 0.760 Go. ksygard 0.452 -&gt;
> 0.708 Go gest de gnome 0.722 -&gt; 1.1 Go gest de xfce 0.519 -&gt;
> 0.824 Go gest de mate 0.722 -&gt; 1.1 Go Gestionnaire xfce 30 Mo
> mousepad 32 Mo thunar 43 Mo tumbler 38 Mo terminal 39 Mo xfce clipman
> 30 Mo xfce panel 43 Mo xfce power 15 Mo xfce session 19 Mo xconfd 5 Mo
> xfdesktop 79 Mo xfsetting 19 Mo xfwm 31 Mo amule 57 Mo deluge 94 Mo
> hexchat 63 Mo thunderbird 236 Mo
> </p>

Alors mon ressenti, comment dire ça sans faire croire qu'il y a parti
pris ou que ça soit totalement neutre de ma part, forcément il y a
toujours parti pris et on ne peut être totalement neutre sur un sujet,
on le voit avec les journalistes pour les présidentielles! Je vais être
pragmatique et me baser pour cela sur les chiffres. Pour commencer,
parlons des moniteurs système, celui de Kde (Ksysguard) est celui qui
est le plus loin de tous, même au niveau des ressources des
applications, il est ailleurs, il n'a pas totalement tout faux par
exemple mémoire partagée donne bien ce que Htop montre en SHR mais pour
le reste... Le gestionnaire de Cinnamon qui est celui de GNOME donne
exactement le même résultat que celui de mate qui s'approche du résultat
de Htop sans être aussi proche que ce que donne celui de Xfce. Question
environnements, Xfce est le plus rapide à se lancer, c'est aussi celui
qui consomme le moins et celui qui demande le moins de paquets. Il offre
le meilleur choix de personnalisations, je me demande même si il n'a pas
surpassé Kde sur ce plan, par contre coté intégration c'est celui qui
souffre le plus du manque d'applications bien qu'il est rejoint par Mate
pour ce soucis, obligeant ainsi à aller chercher dans des applications
indépendants ou dans les autres environnements des applications pouvant
nous servir. Le plus lourd à lancer et à l'utilisation est Cinnamon qui
côtoie en lourdeur Kde, alors je n'ai pas touché la partie composition,
peut etre qu'il y avait un truc à toucher comme sous Kde (mon histoire
de pixels), mais je suis resté sur le plus proche de l'offre par défaut.
Dans les sensations, je note des lourdeurs avec Cinnamon, beaucoup plus
qu'avec Kde, par contre le gestionnaire de fichiers qui s'ouvre le moins
rapidement est bel et bien Dolphin (kde). Thunar offre un bon compromis
entre fonctions et rapidité avec toutefois des manques qui peuvent être
comblé par les actions personnalisés facilement configurable. Mate ne
m'a toujours pas convaincu pour plusieurs raisons, je vais commencer par
le fait de ne pas avoir la possibilité de renommer en masse directement
dans Caja contrairement à Thunar. Je poursuis sur le manque de
personnalisation comme juste pour donner un exemple, ne pas pouvoir
mettre des fonds d'écrans différents si on a plusieurs écrans par défaut
sans aucunes applications ajoutées. Caja est pour moi un sacré retour en
arrière, il n'a rien de ce que je me sers ou de ce que mes "habitués"
demandent, par contre il a des choses qui manquent à Thunar mais dont je
ne me sers pas notamment le fait de pouvoir scinder la vue. Je ne parle
pas de Cinnamon qui n'a jamais su me convaincre entre sa trop grande
dépendance envers GNOME pour ses applications, le manque d'un renommer
en masse présent depuis la 3.22 dans GNOME (à moins que ça soit depuis
la 3.20?),  j'ai eu des lenteurs, mon PC s'est emballé à plusieurs
reprises alors qu'il y avait rien qui nécessitait cette débauche
d'efforts, non rien de convaincant... De plus il collectionne les
défauts présent dans les Gnome avant 3.20, pas de fonds d’écran
différent pour chaque écran (si plusieurs qui est mon cas), en fait je
m'aperçois que le seul bureau à base de GTK possédant cette fonction est
le petit Xfce. Bon je dois dire ce qui m'a plu tout de même, alors dans
ce qui m'a plu de ce bureau c'est d'avoir un truc plus moderne et plus
classe que Mate qui pour moi vieillit très mal, ne me sortez pas Mate
est en GTK3 et Xfce est encore en mixte GTK2 et 3 car je m'en fou
totalement, en fin de compte dans mon utilisation je ne vois pas ce que
m'apporte GTK3 et c'est bien mon utilisation qui compte pour moi. Je
reviens vite fait sur Mate, il y a des choses qui me plaisent, comme ce
retour sur un bureau qui au début de ma vie linuxienne ne m'avait pas
conquis et qui avec le temps a réussi, le temps y est pour quelque chose
mais surtout le travail de Canonical sur Ubuntu 10.04 avait fait le
reste! Sinon les deux panels par défaut sont bien dans l'esprit Gnome2
et ça fait du bien, mais il n'est pas ergonomique, c'est encore une fois
mon avis, je fais trop de va-et-vient vers le haut et le bas de mon
écran dans cette configuration. Et comment ne pas se perdre dans ce
panel, on ne sait jamais où est telle application surtout si c'est de la
configuration mais là je chipote, car il doit bel et bien y avoir des
menus plus moderne un peu comme ce que proposait openSUSE pour son
GNOME-panel (GNOME2). Pour ce qui est de Kde, c'est presque du tout bon,
mais si je dis ça comme ça vous aurez droit de me dire que je suis pas
impartial... Il me manque toujours la possibilité de choisir la qualité
d'impression dans une application Kde, comme Gwenview. Je pense aussi à
cette lenteur de faire apparaître le bureau lors du boot, on n'en finit
plus d'attendre à en croire même à un plantage. C'est aussi le bureau
qui est le plus lent à lancer les applications, par exemple Dolphin met
bien 3 secondes par moment pour s'afficher là ou GNOME-Shell, Mate,
Cinnamon et surtout Xfce met à peine une seconde pour lancer leurs
gestionnaires voire instantané,  un autre exemple c'est quand on clique
dans Dolphin sur une image, ce qui lance Gwenview mais là encore c'est
pas instantané, ce qui donne une sensation de lourdeur ou du moins de
lenteur alors que chez les autres bureaux c'est du instantané... Alors
c'est pas trop comparable vu les possibilités et les fonctions des
applications Kde par rapport à ses concurrents mais tout de même.
Surtout que j'ai toujours entendu que si Kde était plus lent au
démarrage (prenait plus de temps), c'était dû au fait qu'il chargeait en
amont toutes les librairies qui seront partagés par la suite dans ses
applications, les fameux [KIO.](https://fr.wikipedia.org/wiki/KIO) Autre
point et pas des moindres, c'est ce côté usine à gaz, il y a toujours au
moins 2 programmes qui font la même chose, exemple tout bête, Dolphin
capable de ripper dans le format que l'on souhaite les pistes de son CD
audio, chose que K3B (graveur), SoundKonverter (ripper de CD) ou pour ne
citer que ceux là, Amarok sont aussi capables de faire grâce entre autre
aux Kparts. Autre chose et ce sera mon dernier, c'est ce truc qui fait
que ça part dans tous les sens et puis ça s'arrête là, exemple,
Konqueror plus ou moins abandonné comme gestionnaire de fichiers suite à
l'apparition de Dolphin(Kde4) et comme navigateur web pour à la place
Rekonq, résultat c'est que ce dernier est abandonné alors il y a
maintenant
[QupZilla.](https://doc.ubuntu-fr.org/qupzilla "qupzilla"){.wikilink1}
Et comment oublier que si on regarde les ressources des applications
utilisées, on s'aperçoit que les applications KDE sont bien plus
gourmande, on passe de 2 fois à 3 fois plus de ressources que pour des
application Mate, Cinnamon/GNOME ou Xfce, exemple, Konsole qui prends 86
Mo alors que Terminal Xfce et celui de Mate n'utilise que 39 Mo ou par
celui de Cinnamon... Autre exemple, Kwrite prends 113 Mo alors que Gedit
en est à 48 Mo, Pluma est à 50 Mo et Mousepad 32 Mo... Je pensais, à
tord peut être, que les applications KDE partageaient entre elles leurs
ressources. Ce qui si on regarde, commence à faire beaucoup de mauvais
points, d’où la tendance de GNOME à me plaire pour sa simplicité, une
application vaut une fonction et c'est tout, ainsi la simplification des
menus et sous-menus des applications, bref c'est du gagnant. J'ai fini
avec ce long billet qui en fin de compte n'apporte rien, je suis dans
une réflexion d'abandonner KDE pour de bon, d’être sur du Xfce pure avec
quelques applications externes sans liens avec KDE. On verra ça plus
tard.
