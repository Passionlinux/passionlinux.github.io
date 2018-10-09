---
title: Haiku, un système pour faire revivre les PC
date: 2017-08-27 14:12
layout: post
---

![](http://download.tuxfamily.org/passionlinux//2017/08/HAIKU-logo-black-on-white.png){.aligncenter
.size-full .wp-image-1514 width="316" height="102"}
[Haiku](https://www.haiku-os.org/) qu'est ce que c'est? D’après
[Wikipdia](https://fr.wikipedia.org/wiki/Haiku_(syst%C3%A8me_d%27exploitation));  

> Haiku est un système d'exploitation pour les ordinateurs de bureau (on
> ne vise ni les serveurs, ni les téléphones et tablettes, pour le
> moment). Il fonctionne sur les plateformes x86 (32 et 64 bits) et est
> compatible avec [BeOS](https://fr.wikipedia.org/wiki/BeOS) (au niveau
> binaire pour la version 32 bits, en recompilant les applications pour
> la version 64 bits). L'objectif du projet est de continuer là ou BeOS
> s'est arrêté, et de fournir un système d'exploitation facile à
> utiliser, réactif et efficace. Et bien sûr, de permettre à tous les
> développeurs intéressés de se lancer dans un projet de grande
> envergure et de découvrir l'intérieur d'un système d'exploitation.
> Haiku est écrit principalement en C++, et tous les composants (noyau,
> pilotes, applications, serveur graphique, etc.) sont réalisés par la
> même équipe, ce qui simplifie les possibilités d'intégration entre les
> différents composants. Il n'est pas encore complètement compatible
> [POSIX](https://fr.wikipedia.org/wiki/POSIX), mais ça avance petit à
> petit.
> </p>

On peut aussi aller voir sur [LinuxFr](https://linuxfr.org/), dans sa
section liée à cet [OS](https://linuxfr.org/sections/haiku).  
<!--more-->  
Alors qu'elle est le rapport entre ce projet et moi, rien mais il
m’intéresse pour plusieurs raisons, je l'ai testé et en fait il peut
totalement remplacer ma vieille SUSE9.3 sur le 32bit de 256Mo et la
NuTyX sur celui de 512Mo. Il est ultra léger, rapide, assez complet pour
une utilisation classique. Il y à des dépôts d'applications où l'on
trouve par exemple [Qbittorrent](https://www.qbittorrent.org/) ou
[Transmission](https://transmissionbt.com/),
[Vlc](http://www.videolan.org/vlc/) et pas mal d'autres applications. Il
vient avec une flopée d'applications comme un navigateur web du nom de
[webpositive](https://www.haiku-os.org/docs/userguide/fr/applications/webpositive.html),
mais pas que, Haiku est fourni avec un certain nombre d'applications
légères mais essentielles. Vous les trouverez dans les dossiers <span
class="path">/boot/system/apps/</span>. Les applications qui ne sont
généralement pas lancées par un double-clic sur un fichier de données
(comme par exemple ShowImage pour les fichiers d'images) peuvent êtres
trouvées dans le menu <span class="menu">Applications</span> de la
Deskbar.  

  -------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------- -- ---------------------------------------------------------------------------------------------------------
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/activitymonitor-icon_16.png){width="16" height="16"}    [ActivityMonitor](https://www.haiku-os.org/docs/userguide/fr/applications/activitymonitor.html)        Permet de surveiller les ressources système comme le processeur et la mémoire.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/bootmanager-icon_16.png){width="16" height="16"}        [BootManager](https://www.haiku-os.org/docs/userguide/fr/applications/bootmanager.html)                Installe un menu d'amorçage dans le "Master Boot Record" (MBR) au début du disque.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/charactermap-icon_16.png){width="16" height="16"}       [CharacterMap](https://www.haiku-os.org/docs/userguide/fr/applications/charactermap.html)              Affiche la table des caractères Unicode.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/codycam-icon_16.png){width="16" height="16"}            [CodyCam](https://www.haiku-os.org/docs/userguide/fr/applications/codycam.html)                        Cet outil permet d'envoyer régulièrement les images d'une webcam vers un serveur.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/debugger-icon_16.png){width="16" height="16"}           [Debugger](https://www.haiku-os.org/docs/userguide/fr/applications/debugger.html)                      un débogueur graphique.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/deskcalc-icon_16.png){width="16" height="16"}           [DeskCalc](https://www.haiku-os.org/docs/userguide/fr/applications/deskcalc.html)                      Une calculette.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/diskprobe-icon_16.png){width="16" height="16"}          [DiskProbe](https://www.haiku-os.org/docs/userguide/fr/applications/diskprobe.html)                    Un éditeur hexadécimal pour les fichiers et les mémoires de masse.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/diskusage-icon_16.png){width="16" height="16"}          [DiskUsage](https://www.haiku-os.org/docs/userguide/fr/applications/diskusage.html)                    Affiche une représentation graphique de l'espace disque consommé sur un disque dur.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/drivesetup-icon_16.png){width="16" height="16"}         [DriveSetup](https://www.haiku-os.org/docs/userguide/fr/applications/drivesetup.html)                  Un outil de partitionnement de disque dur.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/expander-icon_16.png){width="16" height="16"}           [Expander](https://www.haiku-os.org/docs/userguide/fr/applications/expander.html)                      Permet de décompresser les formats d'archive les plus courants.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/haikudepot-icon_16.png){width="16" height="16"}         [HaikuDepot](https://www.haiku-os.org/docs/userguide/fr/applications/haikudepot.html)                  Un outil pour trouver, télécharger, installer, mettre à jour et désinstaller (application) des packages
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/icon-o-matic-icon_16.png){width="16" height="16"}       [Icon-O-Matic](https://www.haiku-os.org/docs/userguide/fr/applications/icon-o-matic.html)              Une application de création d'icônes vectorielles pour Haiku.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/installer-icon_16.png){width="16" height="16"}          [Installer](https://www.haiku-os.org/docs/userguide/fr/applications/installer.html)                    Permet l'installation de Haiku sur une partition du disque dur.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/magnify-icon_16.png){width="16" height="16"}            [Magnify](https://www.haiku-os.org/docs/userguide/fr/applications/magnify.html)                        Fournit une image agrandie de la zone autour du curseur de la souris.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/mail-icon_16.png){width="16" height="16"}               [Mail](https://www.haiku-os.org/docs/userguide/fr/applications/mail.html)                              Un client e-mail.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/mediaplayer-icon_16.png){width="16" height="16"}        [MediaPlayer](https://www.haiku-os.org/docs/userguide/fr/applications/mediaplayer.html)                Un lecteur audio/vidéo supportant un grand nombre de formats.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/midiplayer-icon_16.png){width="16" height="16"}         [MidiPlayer](https://www.haiku-os.org/docs/userguide/fr/applications/midiplayer.html)                  Un lecteur de fichiers MIDI
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/packageinstaller-icon_16.png){width="16" height="16"}   [PackageInstaller](https://www.haiku-os.org/docs/userguide/fr/applications/packageinstaller.html)      Installeur de paquets BeOS au format PKG.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/people-icon_16.png){width="16" height="16"}             [People](https://www.haiku-os.org/docs/userguide/fr/applications/people.html)                          Un gestionnaire de contacts.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/poorman-icon_16.png){width="16" height="16"}            [PoorMan](https://www.haiku-os.org/docs/userguide/fr/applications/poorman.html)                        Un serveur web simple et léger.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/screenshot-icon_16.png){width="16" height="16"}         [Screenshot](https://www.haiku-os.org/docs/userguide/fr/applications/screenshot.html)                  Un outil de capture d'écran.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/showimage-icon_16.png){width="16" height="16"}          [ShowImage](https://www.haiku-os.org/docs/userguide/fr/applications/showimage.html)                    Une visionneuse d'images.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/soundrecorder-icon_16.png){width="16" height="16"}      [SoundRecorder](https://www.haiku-os.org/docs/userguide/fr/applications/soundrecorder.html)            Permet d'enregistrer du son depuis une entrée audio ou microphone. \[*pas encore documenté*\]
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/stylededit-icon_16.png){width="16" height="16"}         [StyledEdit](https://www.haiku-os.org/docs/userguide/fr/applications/stylededit.html)                  Un éditeur de texte simple.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/terminal-icon_16.png){width="16" height="16"}           [Terminal](https://www.haiku-os.org/docs/userguide/fr/applications/terminal.html)                      Accès au shell bash.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/textsearch-icon_16.png){width="16" height="16"}         [TextSearch](https://www.haiku-os.org/docs/userguide/fr/applications/textsearch.html)                  Un outil de recherche dans les fichiers texte.
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/tv-icon_16.png){width="16" height="16"}                 [TV](https://www.haiku-os.org/docs/userguide/fr/applications/tv.html)                                  Un visualisateur de TV analogique \[*pas encore documenté*\]
  ![icon](https://www.haiku-os.org/docs/userguide/images/apps-images/webpositive-icon_16.png){width="16" height="16"}        [WebPositive](https://www.haiku-os.org/docs/userguide/fr/applications/webpositive.html)                Un navigateur Web natif.
  -------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------- -- ---------------------------------------------------------------------------------------------------------

On trouve pas mal d'explications, de documentations sur le site du dite
[projet](https://www.haiku-os.org/docs/userguide/fr/contents.html).
Pourquoi m’intéresse t'il? J'ai plusieurs machines récupérées par-ci
par-là, se sont toutes des machines vouées à la casse, des machines qui
fonctionnent mais dont les OS sont soit HS, comme des XP à l'abandon et
qui n’intéressent plus leurs propriétaires qui sont passés à autre
chose, soit des linux qui n'arrivent plus à rester dans la course faute
à des applications toujours plus lourdes années après années. Des
machines que je ne peux me résoudre à jeter car de mon côté je m'en sers
toujours et arrive à leur donner une seconde jeunesse, soit dans un but
de serveur multimédia, soit de serveurs multi-usage, ou de PC
"secondaire" ayant comme seule but des choses simples. Avec Linux faudra
que je passe par des distributions destinées à ce layout de PC,
c'est-à-dire [Slitaz](http://www.slitaz.org/fr/), [Pupy
linux](http://www.puppylinux.org/main/Overview%20and%20Getting%20Started.htm),
choisir des applications économes en ressources, car le souci n'est pas
le noyau Linux, les applications Gnu, les environnements comme Xfce ou
Mate, non le souci vient uniquement des applications, je prendrais un
exemple connu, Firefox qui est de plus en plus lourd années après
années, je suis actuellement avec un Firefox qui pompe 400Mo, c'est
juste énorme c'est ce que prend Xfce sur ma bécane... Un Thunderbird qui
frôle les 200Mo...
[![](http://download.tuxfamily.org/passionlinux//2017/08/Capture-décran-de-2017-08-27-13-25-25.png){.aligncenter
.wp-image-1517 .size-full width="960"
height="551"}](http://download.tuxfamily.org/passionlinux//2017/08/Capture-décran-de-2017-08-27-13-25-25.png)Bref,
le souci c'est qu'on a beau prendre un bureau léger, cela ne suffit
plus, il faut aussi regarder les applications et là c'est problématique
car ça suit pas. Alors oui, on peut toujours trouver des pépites comme
Claws-mail, un courrielleur léger et rapide, il y a aussi Qupzilla et
Midori des navigateurs rapides et assez légers mais rien n'est prévu de
base pour être aussi peu économique. Et c'est là que rentre en jeu
Haiku! Pour être rapide et sans tourner autour du pot, tout est pensé
pour être rapide et léger, on oublie notre bon vieux système à qui on
rajoute un environnement de bureau (GNOME, KDE, Mate, Xfce...) et des
applications. Là c'est un OS complet et uniforme, alors ce n'est pas
aussi à la pointe que ce qu'on peut trouver sous GNOME ou KDE, mais
c'est vraiment pas mal. Et comment ne pas parler de [la gestion des
fenêtres](https://www.haiku-os.org/docs/userguide/fr/gui.html),
transcendant!
![](https://www.haiku-os.org/docs/userguide/fr/images/gui-images/gui-s+t.gif){.aligncenter
.size-medium width="775" height="308"} Je ne sais pas vendre un projet
que j'aime bien, alors je vais laisser parler Fred qui le fait bien
mieux: http://frederic.bezies.free.fr/blog/?s=haiku Notamment cette
vidéo: https://youtu.be/\_EqK-yFs7IE Je parlerais prochainement de son
installation.
