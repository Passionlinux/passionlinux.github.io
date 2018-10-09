---
title: Comparaison des environnements Xfce, Cinnamon, Mate et KDE 2, Le cas KDE
date: 2017-08-13 10:20
layout: post
---

Dans les commentaires du [billet
précédent](http://passiongnulinux.tuxfamily.org/2017/08/05/comparaison-des-environnements-xfce-cinnamon-mate-et-kde/),
celui qui porte le même titre à quelques mots près, j'ai eu des avis
intéressants et surtout des questions sur pourquoi KDE-full
[ICI](http://passiongnulinux.tuxfamily.org/2017/08/05/comparaison-des-environnements-xfce-cinnamon-mate-et-kde/#comment-1330)
et
[LÀ, ](http://passiongnulinux.tuxfamily.org/2017/08/05/comparaison-des-environnements-xfce-cinnamon-mate-et-kde/#comment-1336)sont
notamment intéressant car m'ont dévoilé un souci que je répétais depuis
des lustres, à savoir installer KDE avec le méta-paquet
[kde-full](https://packages.debian.org/stretch/kde-full), paquet ultra
complet qui installe l'intégralité ou presque de ce bureau! Je tente
donc de donner la raison de cette manière de faire, mauvaise du coup
pour l'utilisation que j'en fais et aussi les résultats d'un KDE
installé avec seulement le "[taskel](https://wiki.debian.org/tasksel)".  
<!--more-->  
Pour commencer, il faut virer kde-full avec un:

    apt remove kde-full

Ce qui aura pour conséquence de supprimer au prochain "apt-autoremove"
les paquets suivants:

    Les paquets suivants ont été installés automatiquement et ne sont plus nécessaires :  advancecomp akonadiconsole analitza-common artikulate astrometry.net avogadro-data blinken blogilo bomber bovo cantor  cantor-backend-qalculate cervisia cvs cvsservice edict filelight fonts-dustin freerdp-x11 gnugo granatier indi-bin kajongg kalarm  kalgebra kalgebra-common kalzium kalzium-data kanagram kanjidic kapman kapptemplate katomic kblackbox kblocks kbounce kbreakout  kbruch kcachegrind kcharselect kcolorchooser kde-config-cron kde-games-core-declarative kdeadmin kdeartwork kdeartwork-wallpapers  kdeedu kdeedu-data kdeedu-kvtml-data kdegames kdegames-card-data kdegames-card-data-kf5 kdegames-mahjongg-data  kdegames-mahjongg-data-kf5 kdegraphics kdegraphics-mobipocket kdegraphics-thumbnailers kdemultimedia kdenetwork  kdenetwork-filesharing kdepim kdepimlibs-kio-plugins kdesdk kdesdk-kio-plugins kdesdk-misc kdesdk-scripts kdesdk-thumbnailers  kdetoys kdeutils kdewebdev kdf kdiamond kfilereplace kfourinline kgeography kgeography-data kget kgoldrunner kgpg khangman  khelpcenter4 kig kigo killbots kimagemapeditor kiriki kiten kjumpingcube klettres klettres-data klickety klines klinkstatus  kmahjongg kmines kmplot kmtrace knavalbattle knetwalk kolf kollision kolourpaint4 kommander kompare konquest konsolekalendar  kontact kpart5-kompare kpartloader kpat kppp krdc kremotecontrol kreversi krfb kruler ksaneplugin kscd kshisen ksirk ksnakeduel  kspaceduel ksquares kstars kstars-data ksudoku ksystemlog kteatime ktimer ktouch ktouch-data ktuberling kturtle kubrick kuiviewer  kuser kwordquiz libakonadi-contact4 libakonadi-kde4 libakonadi-kmime4 libakonadiprotocolinternals1 libanalitza7 libanalitzagui7  libanalitzaplot7 libanalitzawidgets7 libastrometry0 libavogadro1 libc6-dbg libcfitsio-bin libcfitsio5 libdiscid0 libdmtx0a  liberfa1 libfreerdp-cache1.1 libfreerdp-client1.1 libfreerdp-codec1.1 libfreerdp-common1.1.0 libfreerdp-core1.1  libfreerdp-crypto1.1 libfreerdp-gdi1.1 libfreerdp-locale1.1 libfreerdp-plugins-standard libfreerdp-primitives1.1  libfreerdp-rail1.1 libfreerdp-utils1.1 libgettextpo0 libindi-data libindi-plugins libindi1 libindialignmentdriver1 libindidriver1  libjs-jquery-datatables libjs-mootools libkasten3controllers3 libkasten3core3 libkasten3gui3 libkasten3okteta1controllers1  libkasten3okteta1core1 libkasten3okteta1gui1 libkcalcore4 libkdegames6abi1 libkdegamesprivate1abi1 libkeduvocdocument5  libkf5blog5 libkf5composereditorng5 libkf5gapiblogger5 libkf5kdegames7 libkf5kdegamesprivate1 libkf5kexiv2-15.0.0  libkf5kmahjongglib5 libkf5plotting5 libkidletime4 libkimap4 libkiten5 libkomparediff2-5 libkompareinterface5 libkrossui4  libksane0 libkunitconversion4 libmailtransport4 libnova-0.16-0 libokteta2core2 libokteta2gui2 libopenbabel4v5 libprison0  libqhull7 libqrencode3 libserf-1-1 libsvn1 libwcs5 libwinpr-crt0.1 libwinpr-crypto0.1 libwinpr-dsparse0.1 libwinpr-environment0.1  libwinpr-file0.1 libwinpr-handle0.1 libwinpr-heap0.1 libwinpr-input0.1 libwinpr-interlocked0.1 libwinpr-library0.1  libwinpr-path0.1 libwinpr-pool0.1 libwinpr-registry0.1 libwinpr-rpc0.1 libwinpr-sspi0.1 libwinpr-synch0.1 libwinpr-sysinfo0.1  libwinpr-thread0.1 libwinpr-utils0.1 libxfreerdp-client1.1 lokalize lskat marble okteta optipng palapeli palapeli-data parley  parley-data picmi pkg-kde-tools poxml print-manager python-astrometry python-astropy python-attr python-avogadro python-babel  python-babel-localedata python-cffi-backend python-click python-colorama python-constantly python-cryptography python-dbus  python-diff-match-patch python-enchant python-enum34 python-gi python-idna python-incremental python-iniparse python-ipaddress  python-kde4 python-l20n python-levenshtein python-openssl python-pam python-py python-pyasn1 python-pyasn1-modules python-pytest  python-qt4-sql python-serial python-service-identity python-simplejson python-translate python-twisted-bin python-twisted-core  python-utidylib python-vobject python-xapian python-yaml python-zope.interface qhull-bin qml-module-org-kde-analitza  qml-module-org-kde-games-core qtdeclarative4-kqtquickcharts-1 rocs sextractor step subversion svgpart translate-toolkit  translate-toolkit-doc ttf-sjfonts umbrello valgrind valgrind-dbg xplanet xplanet-images

C'est sur que cela fait du monde. Je redémarre la bête, c'est à dire le
PC et non uniquement le bureau et effectivement c'est le jour et la
nuit, je vous montre les captures de mes écrans:
[![](http://download.tuxfamily.org/passionlinux//2017/08/Screenshot_20170810_163745-1024x337.png){.aligncenter
.wp-image-1462 .size-large width="840"
height="276"}](http://download.tuxfamily.org/passionlinux//2017/08/Screenshot_20170810_163745.png)
[![](http://download.tuxfamily.org/passionlinux//2017/08/Screenshot_20170810_163915-1024x576.png){.aligncenter
.wp-image-1463 .size-large width="840"
height="473"}](http://download.tuxfamily.org/passionlinux//2017/08/Screenshot_20170810_163915.png)
[![](http://download.tuxfamily.org/passionlinux//2017/08/Screenshot_20170810_174131-1024x337.png){.aligncenter
.wp-image-1464 .size-large width="840"
height="276"}](http://download.tuxfamily.org/passionlinux//2017/08/Screenshot_20170810_174131.png)Oui
vous voyez bien, je gagne  facilement la moitié précédemment consommée,
avec 421 Mo au démarrage puis une fois que j'ai lancé ma liste de
programmes, je passais à 761 Mo après une heure d'amusement. Donc oui,
il est préférable de n'installer le minimum, dans mon cas le
kde-standard et d'installer et de rajouter les programmes qu'on aime
avoir. J'ai aussi pensé à cocher la case pour démarrer une session
vierge. Pour les processeurs, je note une diminution, moins d’activités
et surtout moins de pointes. Les seules pointes que je note c'est
Firefox et Thunderbird qui me bouffent de plus en plus de RAM, je suis
actuellement à 360 Mo pour le navigateur de Mozilla (avec un seul onglet
d'ouvert) et 213 Mo pour le courrielleur. Il va falloir que je regarde
pourquoi ces deux produits pompent autant.
