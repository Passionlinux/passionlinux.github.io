---
title: Les tests des distributions de FRlinux 1, Mandriva 2006
date: 2007-06-10 01:32
layout: post
---

Quand je commençais à toucher a mon premier linux, il y avait un site
qui proposait des tests de distributions, depuis ce site est arrêté mais
il est toujours en ligne a cette adresse: <http://frlinux.net/index.php>
Je reprend ici les nombreux tests qui m'ont donné envie de me poser sur
telle ou telle distribution.  
<!--more-->

<div>

Voila ce qu'on pouvait lire sur ma première distribution:

</div>

<div>

**[Mandriva 2006.0](/index.php?tag/Mandriva%202006.0)**

*Dernière mise à jour : 30/12/2005* Le premier test de la Mandriva
2006.0 a été effectué le 04 novembre 2005. Depuis, une version Club de
décembre est disponible, lisez en
plus [ici](http://frlinux.net/index.php?section=distributions#club).

 Mandriva 2006.0 représente la première sortie de Mandriva avec l'équipe
de [Conectiva](/index.php?tag/Conectiva). Il est d'ailleurs possible aux
possesseurs de cette dernière de passer à Mandriva 2006.0 en suivant
les [Release
Notes](http://qa.mandriva.com/twiki/bin/view/Main/MandrivaLinux2006ReleaseNotes_Fr).
Cette nouvelle version intègre plein de bonnes choses comme :
[noyau](/index.php?tag/noyau) 2.6.12.6, [KDE](/index.php?tag/KDE) 3.4.2,
[Gnome](/index.php?tag/Gnome)
2.10,[OpenOffice](/index.php?tag/OpenOffice).org 2.0 beta2,
[Firefox](/index.php?tag/Firefox) 1.0.6, [Glibc](/index.php?tag/Glibc)
2.3.5 et encore plein de bonnes choses. J'ai procédé à l'installation de
cette distribution en installant une Mandriva 2005 minimale puis en
mettant à jour en utilisant les fichiers de configuration générés
par [EasyUrpmi](http://easyurpmi.zarb.org/). J'ai procédé à
l'installation sur mon AMD64 3000+ avec 1GO de RAM et une seconde
machine en mode 32 bits (Athlon 2600+ avec 1GO de RAM). J'ai aussi tenté
une installation sur mon T42 mais il a pas aimé la table de partition
façon IBM, j'ai donc abandonné. L'installation réseau ne m'a pas posée
de problème, je tournais sur une ligne ADSL 2MO. Ce qui a pris environ
une heure et demi. J'ai également installé cette
[distribution](/index.php?tag/distribution) depuis une 2006
[beta](/index.php?tag/beta)1 vers la finale. Cela n'a pas non plus posé
de problème, à condition de ne pas oublier de mettre à jour le noyau
manuellement :) J'ai installé Gnome et KDE, ce qui prends à peu près 2GO
sur mon disque. Mandriva vient avec KDE 3.4.2 par défaut. La press
release parle d'une rapidité accrue, je n'ai pas remarqué de gain
notable sur le lancement des applications (par contre sur le démarrage,
clairement oui) depuis la 2005 (testé autant sur l'AMD64 que l'Athlon 32
bits). Ceci étant dit, c'est une distribution qui a de bonnes
performances. J'ai fait le test avec une installation sous ext3 et une
autre en reiserfs 3 (à quand le 4 ?). Le centre de configuration semble
par contre lui un peu plus rapide. Pour préciser, du fait de
l'installation réseau, j'ai utilisé la Mandriva 2006.0 Free, mais j'ai
par contre ajouté les sources Club par la suite pour bénéficier
notamment des paquets Nvidia.

[![](http://frlinux.net/pictures/linux/mandriva2006_01s.png)](http://frlinux.net/pictures/linux/mandriva2006_01.png)

    Côté Gnome, le 2.10 est fourni. Je l'ai donc installé par une suite
de paquets. Firefox fait partie de la suite avec la 1.0.6. Mandriva a
d'ailleurs changé la page de défaut qui vous envoie vers un portail de
sites disponibles. Notez également les smart bookmarks rajoutés sur le
navigateur. Mandriva semble vouloir également changer d'urpmi en
proposant un nouvel outil de gestion de paquets : **smart**. Ce
gestionnaire vient d'un des développeurs de Conectiva. Il implémente (je
cite) un algorithme avancé de résolution des dépendances. Son statut est
néanmoins considéré comme bêta pour le moment mais vous êtes encouragés
à l'utiliser :)

[![](http://frlinux.net/pictures/linux/mandriva2006_02s.png)](http://frlinux.net/pictures/linux/mandriva2006_02.png)

    OpenOffice.org 2.0 beta2 est disponible (à ce sujet, la 1.1.5 est
également disponible mais j'avoue avoir un faible pour la 2.0). Mandriva
a fait un bon effort sur les temps de démarrage de la machine et du
noyau. Pour ce faire, ils ont d'ailleurs
utilisé [UDev](http://qa.mandriva.com/twiki/bin/view/Main/Udev) (le
précédent système utilisait hotplug). La différence se fait bien sentir
sur la détection du matériel. Pour ceux rencontrant quelques problèmes
matériels, je conseille un petit passage par la [liste des
errata](http://qa.mandriva.com/twiki/bin/view/Main/MandrivaLinux2006Errata_Fr) qui
contient pas mal de choses.

[![](http://frlinux.net/pictures/linux/mandriva2006_03s.png)](http://frlinux.net/pictures/linux/mandriva2006_03.png)

    Mandriva intègre E 0.17 pour ceux qui voudraient tester. Non, il
n'est pas encore sorti, il s'agit donc ici du 0.16.999.013-20050904
(CVS). Toujours est-il que pour une version non finale, il ne tourne pas
trop mal. La plupart des menus sont a refaire, mais cela ne bloquera pas
la plupart des adorateurs de E. Côté multimédia, notamment le son, je
n'ai pas eu de souci avec mon Audigy2 qui a été parfaitement reconnue
par ALSA. J'ai ensuite utilisé [Amarok](/index.php?tag/Amarok) (le
lecteur audio de KDE) pour lire ma collection. Au niveau serveur X,
X.org 6.9 est fourni pour apporter un meilleur support matériel. Mais
comme le précise la page des errata, il y a quelques problèmes avec les
pilotes libres ati et nv, auquel cas il est conseillé d'utiliser soit le
pilote vesa, soit la version propriétaire des pilotes.

[![](http://frlinux.net/pictures/linux/mandriva2006_04s.png)](http://frlinux.net/pictures/linux/mandriva2006_04.png)

    J'ai également testé [XFce](/index.php?tag/XFce) 4.2 que j'ai
installé. Il est rapide comme à son habitude. J'ai ensuite testé la
reconnaissance de mon [scanner](/index.php?tag/scanner). J'ai donc lancé
le panneau de configuration avant de sélectionner scanner. Une fois le
[périphérique](/index.php?tag/périphérique) branché, il a été détecté
sans encombres. La seule chose qui n'a pas marché est le plugin
[Gimp](/index.php?tag/Gimp) que j'avais également rajouté. J'ai tenté de
le reconfigurer mais il n'a rien voulu savoir. J'ai installé ensuite le
pilote propriétaire [nvidia](/index.php?tag/nvidia) depuis le club
Mandriva, après avoir réglé un petit problème de paquet sur le
[kernel-source](/index.php?tag/kernel-source), il m'a gentillement pris
la dernière version des pilotes nvidia et recompilé le tout pour mon
noyau, comme un grand.

[![](http://frlinux.net/pictures/linux/mandriva2006_05s.png)](http://frlinux.net/pictures/linux/mandriva2006_05.png)

    De retour sous KDE, j'ai testé [kaffeine](/index.php?tag/kaffeine)
pour lire un DVD crypté, ici encore [PLF](/index.php?tag/PLF) fait du
bon travail, j'ai donc installé les [codecs](/index.php?tag/codecs) et
[libdvdcss2](/index.php?tag/libdvdcss2) puis tous mes DVDs ont été
parfaitement lus. Si vous faites partie du club, il vous est également
possible d'enregistrer une machine sur leur site pour recevoir des
notifications de mises à jour (c'était déjà le cas dans la version
précédente) et également d'installer la dernière version
de **mdkonline** depuis leur site qui vous donnera les dernières mises à
jour directement sur votre bureau.

[![](http://frlinux.net/pictures/linux/mandriva2006_06s.png)](http://frlinux.net/pictures/linux/mandriva2006_06.png)

    Mandriva intègre également un nouveau projet de recherche locale de
bureau qui porte le doux nom de [Kat](http://kat.mandriva.com/).
[Kat](/index.php?tag/Kat) est un projet permettant à KDE d'indexer et de
répertorier des fichiers pour vous. Cela marche avec inotify (système de
notification automatique de changement d'états de fichiers intégré au
kernel 2.6.13 pour remplacer dnotify qui pêchait sérieusement).
L'[indexation](/index.php?tag/indexation) est alors enregistrée dans la
base [SQLite3](/index.php?tag/SQLite3). Kat est un projet principalement
supporté par Mandriva et qui s'inscrit en ligne directe d'un équivalent
à [Beagle](/index.php?tag/Beagle) sous Gnome.

[![](http://frlinux.net/pictures/linux/mandriva2006_07s.png)](http://frlinux.net/pictures/linux/mandriva2006_07.png)

    Une autre grande nouveauté dont on a pas mal parlé entre la press
release et les forums
concerne [Kmyfirewall](http://kmyfirewall.sourceforge.net/). J'ai écumé
quelques forums sans trouver une solution à mon problème. Je ne sais pas
si cela était dû à une installation par le réseau mais toujours est-il
que je n'ai pas réussi à le faire fonctionner. L'erreur que j'ai obtenue
en ligne de commande est la suivante : **Library files for
"libkmfcompiler\_ipt.la" not found in paths**. J'ai d'abord cru à un
problème sur plateforme AMD64 mais la version 32bits m'a posée le même
problème ... Si quelqu'un à une solution pour ce problème, je serais
heureux de la publier ici. [Kmyfirewall](/index.php?tag/Kmyfirewall) est
un [pare-feu interactif](/index.php?tag/pare-feu%20interactif) vous
permettant de décider en temps réel de ce que deviennent les paquets
entrants ou sortants de votre machine.

[![](http://frlinux.net/pictures/linux/mandriva2006_08s.png)](http://frlinux.net/pictures/linux/mandriva2006_08.png)

    Mandriva 2006.0 est une bonne cuvée, je n'ai pas rencontré de
problèmes majeurs depuis la version installée par le réseau. Ayant reçu
mon [powerpack](/index.php?tag/powerpack) hier, je vais l'installer sur
mon portable et voir si je rencontre d'autres soucis. Je pense que
l'alliance avec Conectiva a été bénéfique si l'on voit tout ce qui a été
intégré en technologie dans cette version. Je la conseille les yeux
fermés pour les débutants. Les [ISOs](/index.php?tag/ISOs) de la finale
devraient être bientôt disponibles au téléchargement. Mandriva 2006 Club
- version Décembre 2005

[![](http://frlinux.net/pictures/linux/mdk_2006_dec_01s.png)](http://frlinux.net/pictures/linux/mdk_2006_dec_01.png)

<p>
    Mandriva a décidé de sortir une version spéciale Noël pour ses
abonnés, l'annonce a été faite sur le site officiel du [Club
Mandriva](http://club.mandriva.com/xwiki/bin/Main/launchdec2005specreleaseclub).
Dans les correctifs, on notera un X.org sérieusement corrigé (surtout
pour les possesseurs de cartes ATI, mon portable a apprécié), Gnome
2.12, OpenOffice.org 2.0, toutes les mises à jour de sécurité ainsi
qu'un thème spécial Noël. J'ai ajouté une petite capture d'écran pour
vous donner une idée. J'ai lancé un coup de mises à jours et il m'a tout
de même trouvé quelques petites choses. C'est un bel effort de la part
de Mandriva de fournir une version spéciale club pour les abonnés. Elle
coïncide à peu de choses près à la sortie de la 2006.1 0.3 (alpha) dont
les changements sont
disponibles [ici](http://qa.mandriva.com/twiki/bin/view/Main/DistroChangelog).

</div>
