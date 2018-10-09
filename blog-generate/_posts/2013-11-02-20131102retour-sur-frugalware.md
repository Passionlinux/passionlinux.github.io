---
title: Retour sur Frugalware
date: 2013-11-02 20:08
layout: post
---

<div class="main">

<div class="chapo surlignable">

Comme souvent je l'ai dis, j'ai trois distributions importantes et a qui
je suis resté fidele, la regrétté Mandriva, la vénérable Debian et
openSuse, puis une que j'ai accroché et dont je pense le plus grand
bien : Frugalware. Frugalware est une distribution différente des autres
habitués des podiums, elle n'a pas une base debian ni RPM, mais a
l'origine elle est basé sur Slackware, avec une version amélioré du
gestionnaire Pacman d'Archlinux. Pacman-G2 est un fork de pacman,
l'équipe de frug ayant apporté des améliorations jamais pris en compte
par celle d'arch, ont décidé de le forker. Il est rapide comme son aîné,
et peu le différe vraiment a premiere vue ! il est simple a prendre en
main :
-   mettre a jour le depot de logiciel suivit de la mise a jour systeme
    revient a faire un pacman -Syu ce qui vaut sur Debian a apt-get
    update && apt-get dist-upgrade.
-   Installer un logiciel (par exemple mldonkey) se fait avec un pacman
    -S mldonkey = apt-get install mldonkey sur debian.
-   supprimer un paquet avec ses dependances se fait avec pacman -Rc
    mldonkey

Il est rapide et le peu qu'il dit suffit, j'ai toujours trouvé apt et
aptitude trop bavard, pacman dit autant mais de maniere plus propre, un
peu comme zypper (openSuse) pour ceux qui le connaisse. On pourrait
comparer Frugalware a une archlinux, comme elle c'est une rolling
release c'est a dire que les logiciels sont mis a jours de façon
continue sans version de Frugalware. En gros comme sous Arch, Debian
testing/sid, gentoo, une personne qui fait ses mises a jour une fois
dans l'année(c'est pas a faire) va se retrouver au même niveau que celui
qui les fait tout les jours et dans les deux cas c'est pacman -Syu !
Comme Arch et vu qu'elle uilise pacman(version amélioré), la fabrication
de paquets est tres simple par rapport a des rpm ou des deb, un simple
fichier appelé simplement frugalbuild est a renseigner, cette partie de
frugalware sera vue plus en détail dans un prochain article, mais en
gros on rempli les champs mainteneur, nom du paquet, source, dependance
et si le paquet n'a pas besoin de "build" spéciale, on n'a pas a
renseigner cette partie ! Bon j'admet volontier que j'ai cherché a bien
assimiler la doc, donc avec l'exemple du wiki, j'ai cherché la petite
bete pour tout comprendre et un exemple tres simple, m'a demandé presque
une heure le temps que je comprenne tout plus ou moins grace une
communautée vraiment tres patient, sympa et acceuillante, le tout dans
la bonne humeur ! La ou elle change de sa copine Archlinux, c'est
qu'elle est bien plus facile a prendre en main, en tout cas la ou on
peut voir une difficulté de passer de Debian a Archlinux, avec
Frugalware ça passe tout seul ! Pour commencer, contrairement a Arch qui
avait un installateur pas du tout automatisé et pas evident pour la
partie configuration mais avec lequel on se débrouillait grace a la
documentation de leur wiki (tres bonne au passage !), et qui s'est vu
remplacé dans les dernieres versions par des scripts (ce qu'on ne peut
pas qualifié de plus facile pour une installation !), sous Frug, c'est
différent, jusqu'à la version 1.8, il y avait un installateur tres
simple a prendre en main bien qu'etant non graphique (en gros comme sur
debian, on remplit et suivant), la partie délicate se résumant au
partitionnement. Cette etape est de toute façon jamais a prendre avec
des pincettes, et de mon coté je regarde bien ce qui est dit même sur
ubuntu ou mandriva, une erreur d'inattention et c'est des centaines de
go de données qui seront perdus, et ça arrive tres vite (d'ou les
fenêtre de confirmation). Cette partie la aurait pu être facilité en
proposant un partionnement automatique comme sur debian, mais bon une
fois cela fait on doit choisir les groupes de paquets que l'on veut et
c'etait la ou ça merdait pour moi. Beaucoup trop de groupe coché par
défaut, kde, gnome, xfce, base, lib, dev, multimedia, xmultimedia...
presque tout les groupes etaient deja coché. Bon c'est pas compliqué, il
suffit de décoché mais pour le nouveau, qui généralement, veut avoir le
bureau par defaut de sa distribution c'est moins simple, et frug lui en
colle 3... Du coup l'installation prenait du temps, j'ai été jusqu'à
50minutes par DVD, et oui 3 bureau(kde, gnome, xfce), plusieurs
naviguateur web(firefox, konqueror, epiphany...), gestionnaire de
fichiers..., tout a chaque fois multiplier par 3 au moins, ça fait
beaucoup de paquets a télécharger, a installer, ça prend donc du temps
et de l'espace disque dur. Une version graphique existe, mais vu que je
ne suis pas fan des version graphique, je préfére un bon ncurse fiable
qu'une interface graphique bugué, je ne m'en suis jamais servit, comme
la version live, je ne suis pas fan des lives. Dans cette nouvelle
version 1.9, tout ça a changé, et c'est la cause principale du retard de
cette version, l'installateur est peaufiner a son paroxisme, et le gars
qui y travail, le fait avec amour ! Enfin la ou Frug differe totalement
de sa rivale, c'est qu'elle possede une version stable, qui sort tous
les 6 mois mais supporté 6 mois. Un simple pacman -Syu suffit pour
passer a la nouvelle stable et sans rien changer dans la liste des
depots, vu que seule deux dépôts sont la par défaut, un current qui est
la version rolling release et l'autres est stable, cette partie la ne
m'interesse pas trop, mais ça permet d'avoir un serveur par exemple dont
on ferait une grosse mise a jour tout les 6 mois. A savoir que par la
suite, je parle de la version 1.9 qui devrait pas tarder a sortir, mais
je suis sur current c'est a dire la version rolling release.

</div>

<div class="texte surlignable">

1. Installation
---------------

Donc comme je le disais, l'installateur a changé avec cette 1.9, et n'a
plus rien avoir avec l'ancien sauf qu'il est toujours en version ncurse
(et tant mieux). Mon reseau ethernet a été detecté comme toujours mais
cette fois avec le nom du matériel au lieu de l'eternel "eth0", pour moi
c'est pareil, mais pour certain ça sera bien plus pratique. ensuite on
rentre le nom de la machine entiere avec le nom de domaine puis juste le
nom de machine simple, on demande le passe root puis c'est au tour de
l'utilisateur, nom et passe. On arrive a la liste des groupes de paquets
et cette fois c'est a nous de cocher les groupes qu'on veut, ce qui
contrairement a l'ancien installeur, est une amelioration, comme quoi
l'equipe de frug a beau être restreinte elle en reste pas moins tres a
l'ecoute de ses utilisateurs ! Une fois fait, l'installation des paquets
se lance, une barre de progression est présente mais reste longtemps a
zero, en faite l'installation va si vite que j'ai pas trop fait gaffe,
je suis partie m'assoire sur le canapé moins de dix minutes et a mon
retour c'etait deja fini ! A titre d'exemple, debian m'aurait mis cinq
bonnes minutes de plus au bas mot pour s'installer sans bureau, et je
parle pas des openSuse ou Ubuntu ! En tout moins de 15 minutes pour
m'installer les groupes kde, multimedia, xmultimedia, base, xserver,
plus d'autres que je n'ai plus en tete, ce qui me donne un pc avec tout
les codec et outils que je me sers ! Quand je parle de 15minutes pour
l'installation, faut comprendre du debut ou on tape dans le grub pour
lancer l'installation jusqu'à l'ejection du cd, et je dis 15min mais
quand suis revenu c'etait deja finit sauf que je n'etais pas devant
l'écran... Le seul soucis c'est que malgré le mesage qui nous dit
"installation fini" on doit rebooter via le bouton du pc(un enter ne
suffit pas chez moi...), ceci etant dit c'est pas la mort non plus !  

2. Post-installation et Utilisation
-----------------------------------

La bécane redemarre, on vois un jolie grub, ça change du theme debian
c'est plus frais, puis grub disparait et a peine 15 secondes plus tard
je suis sur kde, la ou debian me met 30secondes, la difference c'est
systemd qui le fait, je suis pas fan de ce fait tout, mais il est
efficace et j'aurais certainement moins de soucis que sur opensuse avec
yast qui se battait avec systemd pour savoir quels services lancer. En
parlant de boot et de temps de boot, frugalware se positionne tres bien
et est dans les même temps que opensuse, mais pour moi c'est pas
essentiel, je préfére un truc a la debian qui met plus de temps mais que
je sais ce qu'il fait, que systemd qui fait tout et bientot le café,
surtout que je fais partie de ceux qui redémarre le pc rarement, ça peut
être une semaine comme plusieurs mois, donc suis pas a 30 secondes par
semaine. Bon j'ai dis le mal que je pensais de systemd passons a autre
chose, frugalware etait tres a jour quand je l'ai connu c'etait les
versions de paquet les plus a jour avec arch, c'est presque toujours le
cas mais vu le peu de dev on peut comprendre certain retard et puis
c'est peut être du a la sortie de la 1.9 dans les jours a venir ! C'est
peut être un mini gel de current le temps que stable sorte. Kde est tres
vivace, deja bien plus vivace que sur debian, qui etait elle même bien
plus vivace que sous opensuse ! J'ai pu remarquer aussi que je gagne
encore en consommation cpu et processeurs, ce qui n'est pas négligeable,
le tout étant plus du peut être a la version de kde, 4.11 sous
frugalware contre 4.10 sous debian sid ! J'ai commencé par changer
l'ordre des mirroires pour mettre ceux d'Irelande en tete, plus rapide
et plus fiable, suivit d'une mise a jour des depots et des paquets via
pacman -Syu. J'ai installé ensuite mes paquets habituelle, c'est a dire
kde-extra, mlnet, et quelques autres,... Ensuite, et au vu de l'accueil
des gars présents sur le irc fr, \#frugalware.fr, j'ai commencé a
regarder la documentation pour faire des paquets, pour le moment ça
roule, et suis bien content d'être de nouveau sur cette ditribution qui
m'a marqué en 2007. Prochaine étape sera de faire quelques paquets et
pourquoi pas en maintenir ; mais ça sera dans un prochain article !

</div>

</div>
