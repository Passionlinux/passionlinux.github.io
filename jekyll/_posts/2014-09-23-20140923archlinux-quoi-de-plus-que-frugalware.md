---
title: Archlinux, quoi de plus que Frugalware ?
date: 2014-09-23 19:11
layout: post
---


Deux ans après avoir quitté arch pour de bon suite a un raz le bol de
ses grosses mises a jour qui cassent tout, et après avoir retrouvé un
certain confort avec frugalware(que j'avais lâché en 2009 pour aller sur
arch) que j'avais perdu suite a une longue errance sur
ubuntu/unity(10.04-&gt;14.04), j'ai voulu voir ce qu'apportait arch par
rapport a frug. Je commence tout de suite par j' ai fait ça pour
répondre a certain qui demandait ce que frug apportait par rapport a
arch, et le constat est amère de mon coté !
[http://linuxfr.org/users/seb95/journaux/frugalware-une-distribution-pas-comme-les-autres](https://linuxfr.org/users/seb95/journaux/frugalware-une-distribution-pas-comme-les-autres)  

### Téléchargement et installation officiel : {#outil_sommaire_0}

Tout d'abord, je télécharge le média officiel, vous savez ce truc qui se
dit être un installateur, qui pour moi n'est qu'un live qui se copie sur
le disque ! Je prend le torrent car ça va vite et le mdsum sera déjà
contrôlé, c'est un bon point car frug n'a pas de torrent, ou si mais pas
de seed. Je commence a installer en suivant la doc, le wiki au passage
est toujours une mine d'or, je reboot après 40min pour démarrer sur une
arch vierge de tout, en faite il n'y a que la base( c'est voulu) mais
comment j'ai pu mettre autant de temps pour installer la base ? Tout
s'explique par je suis lent a taper les commandes et a les adapter pour
mon matos, j'installe par la suite kde, kde-l10n-fr, firefox,
qbittorrent, de la j'ai une erreur, qbittorrent n'est pas dans les
dépôts ! J'installe a alors le reste et j’attends, j’attends,j’attends,
pourtant j'ai configuré les miroirs mais le débit tourne a peine a
400kb/s. Kde se lance, kdm est toujours en qwerty, au passage, dans le
terminal, suis toujours en qwerty alors que c'est réglé pour azerty,
j'ai du le refaire, j'avais oublié de mettre un dièse devant l'anglais,
mais pour kdm, faut que je retouche un fichier, ça fait tellement
longtemps que j'avais zappé ! Donc pas loin d'une heure vingt pour avoir
un système opérationnel sous kde avec firefox, libreoffice, quelques
jeux et le tout en français avec la manière d'installation officielle !  

### Téléchargement et installation archboot : {#outil_sommaire_1}

Je télécharge ensuite l'archboot pour comparer l'installation des barbus
prétentieux et celui des gens normaux, je prend le torrent bien sur. Je
lance, c'est simple ça rappel AIF, l'installation n'est pas des plus
compliqué, suffit de suivre les étapes, dont une qui n'est plus par
rapport a AIF c'est la partie démons, faut dire que systemd facilite
grandement cette étape. Comme d'habitude je n'installe que la base, le
tout dur a peine une dizaines de minutes(15 minutes pour être précis…),
au reboot, j'ai mon arch d'installé et fonctionnelle, le clavier est
bien en azerty, utf8 est bien activé(je l'ai fait pendant
l'installation), donc comme en haut je lance l'installation de kde,
kde-l10n-fr, firefox, puis je redémarre pour voir kdm en action, kdm
toujours en qwerty, bon faut vraiment que je me décide a régler le
fichier en question, pour le reste de kde c'est bien en azerty ! Je
rajoute le dépôt d'archlinux.fr pour avoir yaourt qui est le seul truc
que je trouve géniale sous arch, et que j'ai besoin pour avoir deux ou
trois truc qui me manque sous arch, déjà qbittorrent, on a beau me dire
que arch a plus de paquets que frug, si c'est pour aller sur AUR je ne
vois pas l'intérêt, pour moi AUR est comme une boite de chocolat, on ne
sait jamais sur quoi on va tomber(forest gump), le pire côtoie le
meilleur. La ou sous frug en même pas dix seconde j'ai la construction
de mon paquet qbittorrent via le frugalbuild, sous arch ça me prends pas
loin de la minute, et surtout ça me fait gueuler les processeurs de mon
pc, chose que frug ne fait pas quand je build un paquet ! Âpres
qbittorrent j'ai besoin de cowsay-futurama et de fortune-mod-futurama-fr
et encore une fois je ne les trouve pas dans les dépôts mais sur AUR,
cette fois cowsay c'est parfait mais fortune-mod-futurama-fr s'installe
mais reste introuvable…, pas grave je passe a autre chose. Le pc est
aussi vivace que sous frug et consomme autant donc tout va bien. Les
paquets sont bien sur a jour, arch est réputé pour ça, mais a part le
kernel que arch possède en 3.16 alors que frug se contente du 3.14 tout
est identique, kde 4.14, un début de plasma 5, les produits Mozilla sont
aussi dans leurs dernières versions, libreoffice aussi, vraiment si je
dois choisir sur les versions des programmes pour faire un choix entre
arch et frug, ça serait pas déterminant !  

### Conclusion {#outil_sommaire_2}

Alors qu'est ce que arch a de plus que frug, qu'est ce qui pourrait me
faire passer a arch ? La réponse est rien, l'installateur officiel est
une horreur sans nom qui me fait perdre un temps fou a tout configurer
pour recommencer une fois le bureau installé comme si j'allais avoir une
érection de l'avoir fait moi même, le tout plus d'une heure pour avoir
une arch configuré avec kde et deux trois programmes que je me sert ;
archboot est très bien, mais je préfère ne pas passer plus de trente
minutes pour avoir mon système avec kde et qu'il me reste encore de la
configuration(kdm en azerty notamment), trente minutes a cause
certainement des miroirs blindés, avant il y avait une méthode pour
savoir quel miroir utilisé mais en deux ans j'ai perdu pas mal de
notion ! Je continue aussi a dire que AUR n'est pas un dépôt, et donc il
n'y a pas tant de logiciels que ça dans les vrais dépôts, la plupart des
programmes que je me sert ne sont pas dans les dépôts… AUR est dangereux
pour un non initié, AUR contient de bons builds comme des merdes sans
noms qui devraient pas avoir lieu ! Et je ne pige toujours pas pourquoi
les fameux builds qui sont potable dans AUR ne sont toujours pas
incorporé dans les dépôts ? A moins que la participation des
utilisateurs soit ralentit par tout une procédure comme debian ? Sous
frug suffit de faire le build de l'envoyer sur la liste avec son patch
et si c'est bon c'est accepté avec un gentil merci !!! Plus simple je ne
connais pas !  

### Méthode Antergos {#outil_sommaire_3}

On va faire encore un essai, cette fois méthode Antergos anciennement
connu sous le nom de Cinnarch, qui n'est rien d'autre qu'une arch avec
un dépôt rajouté en plus de ceux par défaut d'arch, c'est encore un
live, on démarre sous gnome par défaut et on a accès a une icône pour
l'installateur, celui ci est très bien foutu, c'est même rare pour que
je le dis, il est simple, expliqué et bien traduis, j'ai bien aimé
notamment que l'on puisse choisir directement le bureau qu'on veut, dans
mon cas on ne change pas une équipe qui gagne, c'est kde ! Ensuite on
nous demande les services qu'on veut installer et activer par défaut, on
a le choix cup, ect,… Vraiment sympathique, après ça télécharge les
paquets directement sur le net, et c'est long, très long, plus d'une
heure dix dont plus de 40 minutes pour télécharger les 900 paquets….
Soit leur dépôt Antergos a peu de débit soit c'est encore les miroirs
d'arch qui sont lents. Au redémarrage on se retrouve sur un beau bureau
kde, tout est francisé et surtout le matos est reconnu, cette fois on
est bien en azerty même dans le kde que j'ai installé par la suite car
c'est lightdm par défaut et celui ci est un peu, beaucoup ou a la
folie,…, planté ! Je me pose une question, pourquoi chez moi c’était un
vrai sapin de noël ??? Je me demande encore si antergos est une vrai
arch avec des programmes en plus et un dépôt rajouté et donc en enlevant
ce dépôt et en faisant une installation de base, si on se retrouverait
sur une arch ? Tout marche vraiment bien, sauf les icônes et le thème
par défaut qui me convient guère, une installation commencée a 16h50 et
fini a 18h(kde +cupd +libreoffice +chose propriétaire et codecs +fonts +
ufw+ réglage fr), le tout sans intervention de ma part. Ensuite je
recommence avec une installation de la base sans bureau, donc il me
demande ce que je veux, alors ça sera cupd+ drivers et codec+ fonts+ ufw
et le tout dure 34min pour 333 paquets, installation commencée a 18h05
fini a 18h39. Au reboot, je lance su, pour voir ce que je me doutais un
peu, le passe de su est celui de l'utilisateur simple… Pendant
l'installation je n'ai pas vu la possibilité de rentrer la configuration
de root… c'est pas grave je tente l'installation de kde, ça se solde par
un échec car les dépôts ne répondent pas. Je regarde les fichiers en
question(comme sous arch), je rajoute le miroir de archlinux.fr, je vire
celui d'antargos, et je reste avec une belle erreur malgré mon pacman
-Sy… J'abandonne… En tout cas de mon point de vu, elle a le mérite de
permettre une installation pour Monsieur 'tout-le-monde' de arch, et de
plus, elle me paraît a terme plus intéressante que manjaro, qui
incorpore trop de chose entre arch et elle, un peu comme lmde vis a vis
de debian. Je ne dis pas que manjaro n'est pas bien, elle l'est, elle
permet d'avoir une distribution a jour, en roling release, et facile
d’entretien, mais en fin de compte elle n'est plus arch, d'une part les
dépôts sont totalement différents, alors que chez antergos ce sont bien
les mêmes dépôts, d'une autre part, les mises a jours de arch arrivent
dans un dépôt 'testing' après un petit retard de deux jours(c'est pas
mortel), puis passe dans les autres dépôts (au bout d'un certain temps)
et si besoin on patch, et pour les grosses mises a jour qui demande un
changement manuelle dans la configuration et donc l'attention de
l'utilisateur, manjaro s'occupe de tout via des scripts. Sous antergos
c'est les programmes d'arch qu'on retrouve et c'est a nous de faire les
changements de configurations comme sous arch ! D'une coup pour une
demande d'aide c'est plus facile a demander sur les forums d'arch !
N'empêche, que je préfère toujours ma frugalware, et que si celle ci ne
me convenait plus du tout alors oui je pourrait partir sur du antergos
pour accéder a une arch tranquillement.  

### Conclusion finale {#outil_sommaire_4}

Si je dois résumer le succès d'arch par rapport a frug, je dirais deux
ans, oui deux ans, deux ans qui sépare arch de frug, arch est arrivé en
2002, a une époque ou mandrake était reine mais pas super fiable, ou
fedora n'existait pas, ou suse était a moitié libre (yast fut autrefois
propriétaire) et debian avait des versions stable toujours aussi fiable
mais bien plus obsolètes et pas si accessible qu'aujourd'hui, il n'y
avait pas en ce temps la, le rouleau compresseur canonical et son
ubuntu, il y avait comme aujourd'hui, gentoo qui était la seule (me
semble t'il), pour proposer une distribution en roling release et être a
jour sans réinstaller le système entier. Du coup arch a pu se faire
connaître, car c’était la première qui proposait un système comme gentoo
en roling release mais avec des paquets pre-construits, vous vous
imaginez un peu comment c’était cool ? Avoir un système sans besoin de
tout réinstaller a chaque nouvelle version, avec mise a jour en
continue, logiciels dans leurs dernières versions, paquet pre-construit
et aussi car c'est important, des paquets qu'on fait tres simplement, un
simple fichier qui résume tout, la ou debian demande une hiérarchie de
dossiers et des fichiers a mettre dans certains dossiers, la ou rpm
demande aussi plus de travail manuel, et puis il y avait pacman, un
gestionnaire rapide, bien plus rapide que le vieux apt, urpmi et surtout
yast… Frugalware est arrivé la même année qu'ubuntu, en 2004, ou celle
ci a tout ravagé sur sa route a sa sortie, embarquant des devs debian,
en faisant une pub d'enfers avec ses cd gratuit, sa stabilité hérité de
debian, sa facilité d'utilisation, ce fut le début de la fin de mandrake
qui bien qu'un changement de nom du a un procès, n'a pu éviter ce qui
arriva en 2011… Ce fut aussi les premiers oui dire que suse allait
devenir plus libre, déjà yast fut libéré tres peu de temps après(2005 me
semble t'il), ce qui lui permis d’intéresser encore plus de monde car sa
stabilité était reconnu ! Frugalware a tout de même grandit très vite,
et des gars comme Devil505, la porta a bout de bras pour la faire
connaître, on le voyait partout, on entendait partout cette
distribution, l'apogée fut je pense en 2007-2009. Aujourd'hui elle tombe
dans l'oublie, certain croyant même qu'elle avait rendu l'âme… Pourtant
elle est toujours la aussi fiable que d'autre plus populaire
