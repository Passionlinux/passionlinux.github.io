---
title: Les tests des distributions de FRlinux 2, SuSE 9.3 Pro
date: 2007-06-10T11:44:35+02:00
layout: post
---
<div>

Ce qui suit est ma 2eme et l'une de mes préféré distribution.

</div>

<div>

*Dernière mise à jour : 11/07/2005*
<div style="text-align: center;">

    La nouvelle [SuSE](/index.php?tag/SuSE) est dans les bacs et depuis
un peu plus de deux semaines, disponible en
[téléchargement](/index.php?tag/téléchargement) gratuit sous la forme de
5 CDs sur les [FTPs](/index.php?tag/FTPs) et autres miroirs. Comme vous
le savez probablement, [Novell](/index.php?tag/Novell) a racheté SuSE il
y a un petit moment et cela nous donne une présence un peu plus
renforcée à chaque version du géant Américain. Dans la liste des
nouveautés, SuSE 9.3 Pro se pose avec plein de bonnes choses pour votre
machine : [Noyau](/index.php?tag/Noyau) 2.6.11,
[KDE](/index.php?tag/KDE) 3.4, [Gnome](/index.php?tag/Gnome) 2.10,
[Firefox](/index.php?tag/Firefox) 1.0.1, [GCC](/index.php?tag/GCC)
3.3.5, [Glibc](/index.php?tag/Glibc) 2.3.4,
[X.org](/index.php?tag/X.org) 6.8.2,
[OpenOffice](/index.php?tag/OpenOffice).org 2.0PR,
[Beagle](/index.php?tag/Beagle), Adobe Acrobat 7 et RealPlayer 10. Cela
donne pas mal de petites raisons de tester la bête.

</div>

</div>

<!--more-->

<div style="text-align: center;">

    Pour les configurations de test, j'ai utilisé deux machines, mon
Athlon 2600+ avec 1GO de RAM et mon portable IBM T42 Pentium-M 1800Mhz
avec 512MO de RAM. Les deux configurations bénéficiaient d'une partition
de 6GO sur laquelle j'ai fait (presque) la même installation (à savoir
que j'ai rajouté les outils portables pour le T42, ce qui me semble
rationnel :) L'[installation](/index.php?tag/installation) n'a posée
aucune difficulté quelque soit la machine, se passant en deux étapes, le
premier CD installant la base et un redémarrage plus tard, le reste des
CDs à installer puis la [configuration](/index.php?tag/configuration) du
[matériel](/index.php?tag/matériel). Encore une fois, mention spéciale à
SuSE pour avoir un installateur évitant pas mal de prises de têtes au
niveau installation de matériel (y compris mon chipset wireless ou bien
encore ma 6800GT).

</div>

<div>

    SuSE 9.3 vient avec KDE 3.4 qui est soigné au possible, intégrant
tous les derniers raffinements de la suite de bureau qui reste la suite
par défaut lorsque vous démarrez votre machine pour la première fois. Un
truc qui m'énerve depuis déjà quelques versions : lorsque j'ouvre un
terminal, je me retrouve avec un police immonde pas du tout lissée et
j'avoue que cela n'est pas grand chose, mais ce sont les petits détails
qui font des montagnes. Comme vous le remarquerez lors du premier
démarrage le logo de Novell devient de plus en plus présent.

<div>

[![](http://frlinux.net/pictures/linux/suse93_01s.png)](http://frlinux.net/pictures/linux/suse93_01.png)

</div>

    SuSE vient avec Firefox 1.0.1 par défaut (patché bien sûr avec les
derniers correctifs). Cela devient d'ailleurs le navigateur par défaut
(ce qui n'est pas un mal). Notons par contre l'absence de Thunderbird
qui représente pourtant un client mail sérieux. Comme dans la version
précédente, vous pouvez utiliser SuseWatcher pour vérifier que vous êtes
toujours à jour au niveau sécurité. Lors de mon premier démarrage, j'ai
eu 65MO de mises à jour à faire y compris un patch pour le kernel
(comprenez, nouveau kernel, donc redémarrage de la machine). J'ai choisi
un des miroirs de la distribution et j'ai téléchargé ça rapidement. SuSE
vient également avec Acrobat Reader 7.0 d'Adobe qui vous permettra de
lire ces documents bien propriétaires qui ne passent pas sur gpdf (si,
si, croyez moi il y en a ...).

<div>

[![](http://frlinux.net/pictures/linux/suse93_02s.png)](http://frlinux.net/pictures/linux/suse93_02.png)

</div>

    Gnome 2.10 vient en standard dans cette version. Novell aime Gnome
plus que KDE et ce depuis longtemps et cela commence à se ressentir. En
effet, là où on pouvait précédemment se plaindre du manque de paufinage
de SuSE sur Gnome (pour intégrer ses outils), on note à présent une
présence beaucoup plus affirmée. Il sera intéressant de voir si dans les
versions qui vont suivre, ils comptent garder le même niveau entre KDE
et Gnome ou bien avancer Gnome comme environnement de bureau par défaut.
Un petit téléchargement plus tard, SuSE m'a proposé les pilotes
propriétaires Nvidia pour une accélération 3D correcte. J'ai donc au
passage essayé TORCS (que je n'avais pas retenté depuis longtemps) et
qui a bien évolué. Une petite chose m'a énervé lors de la mise à jour
des pilotes Nvidia, YaST m'a enlevé kdm en gestionnaire de sessions pour
mettre xdm (qui ne donne pas beaucoup de choix dans la vie), je pense
que c'est clairement un bug. Facilement corrigeable si l'on sait où
chercher (c'est-à-dire dans /etc).

<div>

[![](http://frlinux.net/pictures/linux/suse93_03s.png)](http://frlinux.net/pictures/linux/suse93_03.png)

</div>

    Concernant l'intégration Bluetooth j'ai encore une fois rencontré
des problèmes avec Gnome alors que les outils KDE marchent parfaitement.
J'ai ainsi pu télécharger depuis mon téléphone des vidéos et photos
prises récemment. SuSE intègre également Evolution 2.2.1 qui marche
comme il se doit mais aussi Beagle. Alors, pour ceux qui ne connaissent
pas, Beagle est un outil de recherche de bureau, vous permettant de
retrouver nombre de fichiers et média depuis votre bureau. Je vous
invite à faire un passage par le [site
officiel](http://www.beagle-project.org/) pour plus d'informations sur
le sujet.

<div>

[![](http://frlinux.net/pictures/linux/suse93_04s.png)](http://frlinux.net/pictures/linux/suse93_04.png)

</div>

    Une fois le démon de beagle en route (suivez les release notes, si
beagle ne marche pas, démarrez le démon à la main, sous votre
utilisateur), il commence à indexer le contenu de votre disque dur.
Comme vous le remarquerez ci-dessous, j'ai fait une petite recherche sur
slayer, et les photos/vidéos que j'ai téléchargées de mon appareil sont
instantanément trouvées. SuSE est la seconde distribution (après Fedora
Core 4) à proposer OpenOffice.org 2.0 PR (Pré-Release) et je les en
remercie vivement, ce pour la bonne raison qu'il est bien plus rapide
que la branche 1.1.x et que j'aime bien les logiciels cutting edge :)

<div>

[![](http://frlinux.net/pictures/linux/suse93_05s.png)](http://frlinux.net/pictures/linux/suse93_05.png)

</div>

    [YaST](/index.php?tag/YaST) fait également un travail tout à fait
exceptionnel sur la détection de tout nouveau matériel (comprenez
matériel non encore connecté à la machine lors de l'installation). J'ai
fait le test avec ma webcam et mon scanner USB et ils sont été tous deux
reconnus sans aucun effort de ma part. La partie multimédia de
surprendra personne, la lecture de fichiers DivX/Xvid particuliers ainsi
que les DVDs cryptés vous posera problème, ce qui peut être facilement
résolu par une visite sur le site de <http://packman.links2linux.org/>.
Il vous faudra un peu jouer avec les [RPMs](/index.php?tag/RPMs) pour
installer une nouvelle version de kafeine avec tout le support des média
qui va bien mais cela vaut le coup. Précisons enfin que bien que je ne
l'ai pas testé cette fois-ci, le
site [suivant](http://ftp.gwdg.de/pub/linux/suse/apt/SuSE/9.3-i386/RPMS.suser-rbos/) propose
apt pour RPMs pour SuSE et le
site [http://www.usr-local-bin.org](http://www.usr-local-bin.org/rpms/) vous
propose des RPMs tout frais pour votre SuSE notamment pour Gnome.

<div>

[![](http://frlinux.net/pictures/linux/suse93_06s.png)](http://frlinux.net/pictures/linux/suse93_06.png)

</div>

    SuSE 9.3 est un bon millésime, vous permettant de mettre rapidement
votre machine à contribution en terme de productivité. Elle privilégie
toujours la pléthore d'outils rendant ainsi le besoin d'un
administrateur quelques peu inutiles. SuSE 9.3 est la seconde
distribution à fournir Xen de base, avec noyau patché et tout, ce qui
est à signaler pour ceux que cela intéresse. Encore une fois, il vous
faudra ajouter quelques sources pour bien profiter de la partie
multimédia, ce qui énerve un peu. La version pro est gratuite depuis sa
disponibilité en FTP, la rendant forcément attractive à une certaine
population. Pour les débutants, je pense que Mandriva (certains vont
encore m'accuser de favoritisme) ou bien Ubuntu feront l'affaire.

http://frlinux.net/index.php?section=distributions&article=251

</div>
