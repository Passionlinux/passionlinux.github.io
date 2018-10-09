---
title: Debian 9 "Stretch" est sorti
date: 2017-06-21 20:14
layout: post
---

Vous avez dû le voir un peu partout, parfois en avance comme [la vidéo
d'Adrien.D](https://www.linuxtricks.fr/news/10-logiciels-libres/344-debian-9-dit-stretch-est-la/),
qui au passage est superbe car contrairement à beaucoup de vidéos, la
sienne nous montre un saut de version. J'ai été un peu étonné du reste
que notre ami avait déjà réussi à trouver une image officiel alors que
celle-ci était encore du nom de stretch-release donc la version non
finit :) Bref, j'entends déjà certaines personnes crier au loup, cette
Stretch est pourrie car ne contient pas Virtualbox, c'est honteux et
autre chose... Entre temps je vois aussi le niveau des mecs sur
[certains
commentaires](https://linuxfr.org/news/debian-9-stretch-deploie-ses-tentacules)
qui volent pas très haut, juste au dessus de la merde en faite, qui pour
la plupart ont soit pas compris le concept de Debian Stable soit veulent
simplement jouer à celui qui fait le plus gros troll... Notamment un
débat inutile sur la version Gcc présente dans Debian, puis un autre
toujours lié sur la difficulté d'installer depuis backport  et un autre
sur l'absence de virtualbox... Bref ça vole pas très haut surtout venant
de gens qui font souvent des retours sur Windows en crachant sur linux
au passage et qui reviennent toujours sous linux...  
<!--more-->  
Je vais répondre ici à certain commentaire, pourquoi ici sur mon blog et
pas sur [linuxfr](https://linuxfr.org/)? D'abord car c'est mon blog et
je peux dire ce que je veux dessus, d'un autre coté répondre la bas
serait seulement entretenir un troll qui ne cesse de grossir et qui
commence à faire pourrir ce fabuleux site qu'est linux.fr, de plus on
finirait par oublier la dépêche de qualité qui a été faite sur ce site
pour cette sortie. Pour Gcc &gt; 7 je pense qu'il sera dans les backport
d'ici peu, attendons donc que Sid soit bien rodé et totalement remis sur
les rails pour y voir apparaître ce Gcc et sûrement le voir descendre
dans les backport! La soi-disant difficulté d'utiliser backport sous
Debian, premièrement c'est du passé et deuxièmement c'est ajouter une
ligne dans son sources.list, en l'occurrence celle-ci:

    deb http://ftp.fr.debian.org/debian stretch-backports main contrib non-free

Puis d'installer le paquet en indiquant à Apt qu'on veut la version du
dépôt backport:

     apt-get -t stretch-backports install nom-du-paquet 

Et c'est tout, compliqué? Je ne comprend pas qu'une personne qui
développe un programme a autant de mal à utiliser backport... Il a juste
voulu faire un troll de plus. Pour ce que Debian entend par stabilité
c'est simple, cela veut dire ou sous-entend:

-   stabilité du logiciel, le moins de bugs possible(comme toute
    distribution de qualité normalement)
-   stabilité des fonctionnalités, pas d’ajouts ni de pertes de
    fonctions, tel programme doit être en mesure de faire les mêmes
    choses au début de la version stable et jusqu’à la fin de cette
    stable
-   stabilité de l’archive, pas d’ajout ni de perte de programmes, les
    dépôts debian doivent contenir le même nombre de paquets à la sortie
    de la stable(etch admettons) et jusqu’à la fin de sa vie.
-   aucun changement dans les fichiers de configuration

De ce fait, on n’est pas « surpris » de ne plus trouver tel paquet, de
voir tel programme perdre telle fonction… Et surtout une mise à jour
debian ne change rien et ne touche à rien, elle corrige seulement… Voila
ce qui est attendu  par les utilisateurs de Debian stable et ce que
sous-entend stable pour les développeurs. Fermons ce sacs à merde, qui a
été ouvert à la base pour un gars qui développe un programme serveur si
j'ai bien suivi... Concentrons nous sur Virtualbox. Alors Virtualbox,
comme vous le savez maintenant, n'est pas dans cette Debian9. La raison
est simple et ne dépend pas de Debian, ou plutôt pas que, en faite
Oracle qui entre nous a tué OpenOffice, OpenSolaris et Mysql (peut être
que celui-ci vit encore mais est remplacé sur la plupart des
distributions), a décidé qu'il ne fournirait plus les patchs des
anciennes versions de son logiciel de virtualisation, que le seul moyen
d’être avec une version corrigé des failles et bugs connus est
d'utiliser la dernière version de ce programme. Donc en résumant, Debian
avait seulement trois choix:

1.  le développeur/mainteneur Debian fournit la dernière version
2.  il maintenait lui-même la version choisie pour Debian et patchait
    la-dite version
3.  virtualbox quitte les dépôts de Debian stable

Ce qui a été choisi est la dernière possibilité,  il est inconcevable
que dans les dépôts de stable un programme bouge et évolue, ça peut
incorporé des bugs, des failles ou simplement un comportement non voulu
car non testé. Le mainteneur se sentant pas capable (d’après ses dires)
de corriger et de patcher virtualbox lui-même a préféré le retirer des
dépôts de stable. Je vais être sincère, pour moi utilisateur de
virtualbox c'est pas très important, je m'explique, si je veux vraiment
l'avoir j'ai plusieurs solutions, tout d'abord récupérer les sources
debian  venant de Sid car oui il sera disponible pour Sid, et le
retroporter donc en faire un paquet maison. J'en ai déjà parlé à
plusieurs reprises sur ce blog. L'autre possibilité est d'utiliser le
[Deb fournit sur le site de
virtualbox](https://www.virtualbox.org/wiki/Linux_Downloads). Enfin et
je pense que c'est celle qui sera utilisé par moi dès sa mise en place,
c'est utiliser les backports de Debian, si le paquet est dans Sid, il y
a de bonne chance pour qu'il soit dans backport par la suite. Maintenant
que tout ça est derrière nous, regardons de plus prés la vidéo d'Adrien,
il a fait une mise a jour de Jessie vers Stretch, il a eu des soucis
avec systemd et mate, honnêtement en ayant fait pas loin de "dix sauts
de version" depuis la release de la 9, je peux assez facilement et
sûrement jeter la faute sur mate. En faite ce bureau sous Debian a été
incorporé  que depuis la Debian 8 et pas mal de soucis se sont avérés et
du reste corrigés depuis. De mon coté pas eu le moindre soucis que ce
soit sous Gnome, Kde ou Xfce ou bien simplement des
multi-environnements. Par exemple chez mes parents c'est Gnome et Xfce,
et a la maison c'est Kde et Xfce. Pour le reste, j'ai vraiment apprécié
sa vidéo. Que dire de cette version? Cette publication inclut un nombre
important de paquets logiciels mis à niveau, tels que :

-   Apache 2.4.25 ;
-   Asterisk 13.14.1 ;
-   Chromium 59.0.3071.86 ;
-   Firefox 45.9 (dans le paquet firefox-esr) ;
-   GIMP 2.8.18 ;
-   une version mise à jour de l'environnement de bureau GNOME 3.22 ;
-   l’ensemble de compilateurs GNU, GCC 6.3 ;
-   GnuPG 2.1 ;
-   Golang 1.7 ;
-   KDE Frameworks 5.28, KDE Plasma 5.8 et les applications KDE 16.08
    et 16.04 pour les composants PIM ;
-   LibreOffice 5.2 ;
-   Linux 4.9 ;
-   MariaDB 10.1 ;
-   MATE 1.16 ;
-   OpenJDK 8 ;
-   Perl 5.24 ;
-   PHP 7.0 ;
-   PostgreSQL 9.6 ;
-   Python 2.7.13 et 3.5.3 ;
-   Ruby 2.3 ;
-   Samba 4.5 ;
-   systemd 232 ;
-   Thunderbird 45.8 ;
-   Tomcat 8.5 ;
-   Xen Hypervisor ;
-   l'environnement de bureau Xfce 4.12 ;
-   plus de 51 000 autres paquets prêts à l'emploi, construits à partir
    de près de 25 000 paquets source.

On apprend aussi via la
[dépêche](https://www.debian.org/News/2017/20170617) que cette version
est
[dédiée](http://ftp.debian.org/debian/doc/dedication/dedication-9.0.txt)
à Ian Murdock fondateur du projet, disparu le 28 décembre 2015 et sera
gérée pendant les cinq prochaines années grâce à l'effort combiné de
[l'équipe de sécurité de Debian](https://security-team.debian.org/)
ainsi qu'à celui de [l'équipe de gestion à long terme de
Debian](https://wiki.debian.org/LTS). Dans “Stretch”, la variante par
défaut de MySQL est maintenant MariaDB. Le remplacement des paquets de
MySQL 5.5 ou 5.6 par la variante MariaDB 10.1 se produira
automatiquement lors de la mise à niveau. Firefox et Thunderbird sont de
retour dans Debian avec la publication de “Stretch”, et remplacent leurs
versions sans marque Iceweasel et Icedove présentes dans l'archive
pendant plus de 10 ans. Un truc qui me parait important et assez
novateur est les constructions reproductibles, plus de 90 % des paquets
source fournis dans Debian 9 construiront des paquets binaires
identiques au bit près. Cette propriété de vérifiabilité protège les
utilisateurs des tentatives malveillantes pour altérer les compilateurs
et les réseaux de construction. Les versions futures de Debian incluront
des outils et des métadonnées de manière à ce que les utilisateurs
finaux puissent valider la provenance des paquets dans l'archive. J'ai
aussi subi les "je sais tout" qui m'ont dit que [c’était le mal absolu
de mettre "stable" dans son
sources.list](https://www.youtube.com/watch?v=yuQTP6YcGTM) au lieu du
nom de la version, ce que je sais pertinent mais oh combien utile quand
tous annoncent la sortie d'une distribution avec de l'avance... Du reste
on m'a dit que c’était encore peu stable et pas totalement au point le
passage de version en version, de mon coté ça fait dix ans que je la
pratique sans soucis et d’après Debian pour cette version , des efforts
additionnels d'assurance qualité tels que des tests automatiques
d'installation et de mise à niveau pour tous les paquets de l'archive
Debian garantissent que “Stretch” répond aux fortes attentes de nos
utilisateurs lors d'une publication stable de Debian.  La mise à niveau
vers Debian 9 à partir de la version précédente, Debian 8, (nom de code
“Jessie”) est gérée automatiquement par l'outil de gestion de paquets
apt-get pour la plupart des configurations. Comme toujours, les systèmes
Debian peuvent être mis à niveau sans douleur, sur place, et sans
période d'indisponibilité forcée, mais il est fortement recommandé de
lire les [notes de
publication](https://www.debian.org/releases/stretch/releasenotes) ainsi
que le [guide
d'installation](https://www.debian.org/releases/stretch/installmanual)
pour d'éventuels problèmes et pour des instructions détaillées sur
l'installation et la mise à niveau. Les notes de publications seront
améliorées et traduites dans les semaines suivant la publication. Bref,
je retourne vite fait sur les commentaires de Linuxfr, sur celui qui
demande assez stupidement si il y a vraiment des utilisateurs qui
utilisent stable pour leurs bureaux, je lui répond seulement, que oui on
est vraiment nombreux, d'abord tout ceux qui veulent du stable et qui ne
change pas un matin sans rien dire, ceux qui ne se sentent pas capable
d'utiliser autre chose car ils savent pertinemment pour l'avoir vécu
qu'une mise à jour sur une distribution qui se veut récente peut péter
le serveur X, comme Ubuntu LTS qui un jour sans vraiment crier garde a
décidé de virer le pilote proprio de certaines cartes Ati et qui m'a
obligé à intervenir sur quatre machines dont les utilisateurs m'ont
appelé en panique... Ceux qui veulent juste que ça marche et se foutent
de la dernière mode... Bref, il y en a... De mon coté, elle marche
vraiment bien cette Stretch, depuis un mois chez mes parents et chez
d'autres, je n'ai rien à dire dessus.    
