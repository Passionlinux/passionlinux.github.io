---
title: Les tests des distributions de FRlinux 10, Frugalware 0.7 (Sayshell)
date: 2007-11-10 10:19
layout: post
---

**Frugalware 0.7 (Sayshell)** *Dernière mise à jour : 21/10/2007*
Frugalware est une petite distribution qui monte... Preuve en est déjà
son cycle de développement car alors que la précédente version est
sortie en début d'année, la voici de retour avec la 0.7, au programme,
il y a de quoi faire saliver : Linux kernel 2.6.22.9, Glibc 2.6.1, GCC
4.2.1, KDE 3.5.7, GNOME 2.20, XFCE 4.4.1, OpenOffice 2.3.0 et Firefox
2.0.0.7. On notera également que plusieurs architectures sont
disponibles comme x86 ou bien x86\_64. Vous pouvez aussi utiliser le
liveCD (FwLive) qui est disponible pour cette version. De nouveaux
outils spécifiques font leur apparition tels que : Gfpm et gnetconfig.
Les utilisateurs internationaux apprécieront les nouvelles langues :
Roumain, Suédois, Italien et Danois. Enfin la documentation s'étoffe
également. J'ai testé seulement la version 32 bits de cette distribution
essentiellement par contrainte de temps. Je verrais si j'ai plus tard le
temps de jouer avec la 64 bits (qui m'avait posé quelques tracas lors du
test de la 0.6). J'ai donc téléchargé le DVD d'installation de la
version 32 bits et ai testé cela sur une machine que j'ai sous la main
pendant mes congés (un Pentium 4 3.2Ghz avec 1Go de RAM, disque dur de
160G, carte vidéo nvidia 7900 GS et un écran LCD 17' NEC).
L'installation n'a pas présentée de problème majeur, je n'aime toujours
pas le fait de sélectionner la partition swap avant la racine, mais
c'est un grief personnel. Pour le reste, j'ai sélectionné une
installation quasi-complète, ce qui m'a donc pris un peu plus de 5Go une
fois décompressé. Frugalware vous propose bien évidemment tout un tas de
gestionnaires de bureaux dont le principal est KDE. J'aimerais également
rappeler que Frugalware est basée sur Slackware mais recompilée pour
i686. Comme je le précisais également auparavant, KDE 3.5.7 est fourni
avec cette version, le tout est très réactif et complet. Firefox 2.0.0.7
est également installé de base. Je n'ai rien à redire sur l'apparence
graphique, mes polices préférées (bitstream vera) sont installées.
J'avouerais que la partie qui pêche un peu concerne la configuration
automatique des imprimantes (comme Ubuntu et Mandriva par exemple). J'ai
du installer une HP PSC 2575 et celle-ci est restée muette jusqu'à ce
que j'installe [hplip](http://hplip.sourceforge.net/) (gestionnaire
d'imprimante HP sous Linux). Après avoir démarré le serveur CUPS, je
suis passé dans le panneau de contrôle KDE et en mode super-utilisateur
pour ajouter une imprimante. Quelques clics plus tard, j'avais mon
imprimante. Ceci dit, je doute que Lucette et Roger aient la même
approche en terme de simplicité.
[![](http://frlinux.net/pictures/linux/frugalware07_01s.png)](http://frlinux.net/pictures/linux/frugalware07_01.png)
Des outils signalés dans cette dernière version, il est important de
parler de Gfpm (Graphical Frugalware Package Manager). Cet outil
s'intègre très bien et propose à la mode des dernières distributions un
outil simple et ergonomique pour installer/mettre à jour/supprimer des
paquets. Les mises à jour sont d'ailleurs proposées par la même
interface. Gfpm est souple, dynamique et simple à utiliser (connaître le
nom du paquet peut aider :) C'est indéniablement un pas en avant par
rapport à l'ancien gestionnaire de paquets qui était tout de même
archaïque. Le second outil fort sympathique est gnetconfig, il vous
propose en quelques clics de configurer votre carte réseau sans prise de
tête, j'ai n'ai ici encore rien à signaler. Je me connecte d'ailleurs
essentiellement en DHCP (fixe avec MAC, mais c'est un autre débat). Ici
encore, un pas vers une distribution plus souple pour le débutant.
[![](http://frlinux.net/pictures/linux/frugalware07_02s.png)](http://frlinux.net/pictures/linux/frugalware07_02.png)
Dans la série c'est la fête, signalons la présence d'OpenOffice.org
2.3.0 (dernière version lors de l'écriture de cet article). J'ai un seul
bémol par rapport aux autres distributions, c'est le manque
d'intégration avec le thème de gestionnaire de bureau. Ce qui nous donne
une interface relativement moche (celle de base) comparé aux
concurrents. J'avoue que ce n'est pas critique mais le débutant fait
généralement assez attention à ce layout de détail. Gnome 2.20 est
également livré. C'est actuellement le dernier de sa catégorie. Le tout
est aussi utilisable que KDE, et je ne rentrerais pas dans une guerre
des gestionnaires de bureau.
[![](http://frlinux.net/pictures/linux/frugalware07_03s.png)](http://frlinux.net/pictures/linux/frugalware07_03.png)
XFCE 4.4.1 est également installé avec Thunar 0.8.0 (gestionnaire de
fichiers pouvant accompagner XFCE). Je vous conseille ici encore ce
gestionnaire si vous avez une configuration un peu plus modeste ou
désirez simplement un environnement bien réactif. J'en ai profité pour
écouter quelques radios de métal sur internet. Mon lecteur de choix
comme toujours s'est tourné vers Kaffeine. J'ai essayé le lecteur de
base attaché à Firefox : mplayer mais celui-ci a tout bonnement refusé
de me lire des urls. Le tout silencieusement. Mais comme Linux c'est
tout d'abord le choix, j'étais content de retrouver kaffeine qui marche
parfaitement bien.
[![](http://frlinux.net/pictures/linux/frugalware07_04s.png)](http://frlinux.net/pictures/linux/frugalware07_04.png)
J'ai d'ailleurs enchaîné sur la lecture de DVDs et kaffeine ici encore
sort grand gagnant. Les autres lecteurs font bien l'affaire une fois les
bonnes bibliothèques installées (surtout pour votre collection de DVDs
protégés avec un verrou en chocolat). Donc tout DVD crypté ou non a pu
être lu sur mon lecteur sans aucun souci. Concernant les mises à jour
évoquées plus haut, les patches de sécurité sont bien suivis avec les
dernières failles déclarées sur Linux. La plupart des paquets populaires
sous Linux sont d'ailleurs disponibles et librement télé-chargeables.
Ais-je déjà mentionné que gfpm est bien plus rapide que son prédécesseur
? J'en remet juste une petite couche alors.
[![](http://frlinux.net/pictures/linux/frugalware07_05s.png)](http://frlinux.net/pictures/linux/frugalware07_05.png)
J'ai aussi installé les derniers pilotes nvidia propriétaires dont la
(presque) dernière version est disponible toujours par votre
gestionnaire préféré. J'en ai d'ailleurs profité pour tester la sortie
du client officiel de Enemy Territory : Quake Wars pour Linux. Force est
de constater que les performances sont tout de même au rendez-vous. Côté
configuration X.org, frugalware m'a tout installé comme un grand et j'ai
juste eu à redémarrer le serveur X pour que tout soit pris en compte.
[![](http://frlinux.net/pictures/linux/frugalware07_06s.png)](http://frlinux.net/pictures/linux/frugalware07_06.png)
En définitive Frugalware confirme ici son petit bonhomme de chemin et sa
stabilité. Il reste encore un peu de chemin pour proposer un
installateur un peu plus convivial au débutant et quelques outils pour
la configuration des différents périphériques mais le résultat en
comparant à la 0.6 est tout de même flagrant : une bonne évolution et
une communauté IRC toujours aussi chaleureuse. Bref, à conseiller si les
distributions classiques vous embêtent ou bien si vous cherchez une
alternative plus complète à slackware.
