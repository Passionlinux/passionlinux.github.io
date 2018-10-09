---
title: Pour votre station bureautique libre à domicile, plutôt fixed ou rolling ? Ma réponse.
date: 2017-05-18 17:52
layout: post
---

En matant du coté de chez Fred, je m’aperçois d'un super billet avec
parti pris sur les [distributions à publication fixe ou
continue](http://frederic.bezies.free.fr/blog/?p=15991). Bien sur il y a
parti pris comme je le disais, de Fred pour les rollings, allant jusqu’à
dire que les "fixed releases pour l'utilisateur particulier sont plus
proches du cercueil que du berceau". Je me permet de mettre en doute,
encore une fois le fait que les distributions avec sortie de versions
vont mal, c'est pas totalement vrai mais pas forcément faux comme pour
certaines rollings, au contraire des distributions comme Debian vont
même plutôt pas mal. Il y a deux sortes d'utilisateurs, les premiers
veulent tout et tout de suite, ce sont les fans des "rollings", et les
autres veulent surtout que ça soit stable et fiable dans le temps, ce
sont les fanatiques des "fixeds". Dans la première école, on trouve
surtout du Archlinux, du gentoo, ou de la Manjaro et dans la seconde,
nous avons du Debian, de la Ubuntu, de la slackware...  
<!--more-->  
Alors notre ami Fred part dans des explications qui arrangent bien sur
les rollings en passant outre certains faits comme les distributions
sérieuses qui maintiennent leurs logiciels. Je cite ses argument qui
sont censé mettre à mal les distributions "fixeds":    

> Nombre de logiciels sont maintenant dans un cycle de publication
> courts, voir ultra-courts. Désolé pour l’inventaire à la Prévert qui
> suit, mais il faut savoir se mettre dans le contexte actuel. ....
> Autant dire qu’avec un tel développement frénétique, il devient de
> plus en plus dur de dire : « *bon, on prend telle version des
> principaux logiciels, on gèle le tout, on tue les bugs les plus
> méchants, et on publie une version de notre distribution. »* ....
> Autant ce genre de choix était viable il y a encore une dizaine
> d’années, autant **il me semble** qu’avec des ordinateurs désormais
> connectés en 24/7 au réseau des réseaux, c’est plus complexe… Ne
> serait-ce qu’au niveau de la sécurité qu’il faut avoir pour éviter de
> se retrouver avec des logiciels *potentiellement* victimes de failles
> de sécurité.
> </p>

Alors je vais me répéter, mais non, il n'y a aucun danger à utiliser une
distribution sérieuse comme Debian car malgré que celle-ci ait bloqué
ses versions dans sa logithèque, elle maintient ses logiciels en
corrigeant les bugs et les failles des dites versions. Du reste Debian
fait souvent référence dans la rapidité de corriger des failles dans ses
paquets. Je continue avec la suite de son billet:  

> J’ai été séduit par l’idée de ne pas avoir à activer de dépôts
> additionnels pour avoir accès à toute la logithèque dont j’ai
> potentiellement besoin. Ni à me poser la question : est-ce que tout ne
> pas va partir en vol à la prochaine montée en version majeure de ma
> distribution ? **Le gros problème des fixed releases ?** La montée en
> version une fois tous les 6 mois à 2 ans. Donc, celui des utilisateurs
> qui sont parfois obligés d’ajouter une floppée de dépots tiers pour
> accéder à certains logiciels, indisponibles autrement.
> </p>

Il donne les deux raisons du pourquoi j'ai choisi Debian et rien
d'autre, l’idée de ne pas avoir à activer de dépôts additionnels pour
avoir accès à toute la logithèque dont j’ai potentiellement besoin me
séduit aussi. Et comme Debian met un point d'honneur pour que le passage
entre deux versions se passe bien, on est sûr que la prochaine montée en
version majeure de ma distribution ne pas va tout casser en vol. Pour
son **gros problème des fixed releases,** je dois dire que ça dépend des
distributions, il doit surtout se baser sur des Ubuntu et des Mint avec
leurs PPA, qui je dois dire, que bien plaisant a l'utilisation, devient
vite casse gueule quand on en active tout un paquet. Mais encore une
fois, ce n'est pas le cas sous Debian, on a bien un dépôt backport mais
pour installer un paquet venant de ce dépôt il faut passer par une
option d'APT (-t jessie-backport en l’occurrence). Par la suite seul le
paquet installé depuis backport suivra les mises à jour de ce dépôt.
Donc on peut très bien jouer au dernier 0ad, Minetest, utiliser un
Libreoffice 5.2, et plein de bonnes choses... Mais encore une fois,
c'est juste du bon sens et connaître un peu le système. Pour moi c'est
clair, les rollings ne sont clairement pas le futur, bien que pendant un
temps j'y ai cru aussi, aux alentours de 2008-2009, j'ai vite changé
d'avis. Je pense que le modèle "fixed" n'est pas prêt de voir le
cercueil et au contraire elle reviendra à la mode quand les fans de
rollings auront marre de prier avant toute mise a jour. Je pense surtout
que le modèle "fixed" est beaucoup plus tranquille, tellement tranquille
qu'on se lasse de cette tranquillité mais qu'on est heureux de pouvoir
se concentrer sur autre chose que la maintenance de son PC. Il y a
encore peu, je pensais réellement que le rolling layout Gentoo était
parfait pour moi, avec Calculate linux, j'avais une distribution à jour
sans être dans l’excès mais non, trop de temps à faire des mises à jour,
je passais de nombreuses minutes à faire de la maintenance avec des
mises à jour de 50 à 150 paquets par semaine. Alors c'est vrai, je
jouais avec les dernières nouveautés comme plasma et autres logiciels
mais en fin de compte c'était beaucoup de maintenance pour pas grand
chose. Le **gros problème des rolling releases,** c'est le temps passer
à faire de la maintenance, les nombreuses interventions manuelles à
pratiquer car en face de nous, les logiciels changent leurs
configurations ou l'endroit contenant leurs configurations, certaines
mises à jour se passent mal et cassent des services (donc encore des
interventions à effectuer...), certains développeurs ne font pas en
sorte que leurs mises à jour se passent pour le mieux, on a pu en voir
un aperçut chez Manjaro et Archlinux dernièrement. Le modèle hybride ou
*bâtard* en semi-rolling est pour moi une perte de temps, tôt ou tard on
va avoir une mise à jour qui casse ou passe mal, Manjaro  nous l'a
encore démontré récemment comme dit plus haut, quant à LMDE qui pour moi
est une blague à peine maintenue avec des updates choisis par les
développeurs selon le danger de casser le système est juste ridicule.
Bien sûr ce comportement est changeable mais par défaut et c'est ce que
l'utilisateur de base se contentera, c'est selon un classement de danger
de casser le système. Après, je pense qu'il peut avoir des améliorations
de faite dans les distributions de layout fixed, peut être mettre plus de
choses dans les dépôts backport, comme par exemple des petits bureaux
léger de layout XFCE ou MATE dans leurs dernières versions. Cela me
plairait pas mal d'avoir une version mis a jour de mon XFCE en plein vol
de ma Debian stable, ou de Mate; je comprend qu'on ne puisse pas le
faire avec des gros bureaux comme Gnome ou KDE, trop de paquets, trop de
vérifications à faire pour voir les éventuels bugs et failles, mais avec
des environnements comme XFCE qui représente approximativement une
vingtaine de paquets, c'est dans l'ordre du faisable. Alors j'entends
déjà les extrémistes débianeux à deux balles qui vont me faire une leçon
de morale sur l'utilisation des backports sur une Debian stable, que ce
n'est pas bien, que ça fragilise la dite version et qu'il faut dans ce
cas utiliser testing ou Sid... Je leur répondrais pourquoi Debian met à
disponibilité ce dépôt? Pourquoi ce dépôt est officiel dans ce cas
puisque il met en danger la stabilité légendaire de cette distribution?
En quoi avoir claws-mail, minetest, hexchat et autre va me foutre le
boxon ou casser le système? Et puis pour finir sur les conneries de
leurs déclarations, c'est très facile de faire marche arrière, il suffit
de désinstaller/purger le paquets en question puis de faire un
autoremove et d'installer le paquet par un classique "apt install
nom-du-paquet", donc rien d'insurmontable. Pour finir, je pense que le
layout de distributions n'est pas important, c'est quelque chose dont il
faut penser mais c'est pas plus que ça, ce qui compte c'est de se sentir
bien sur la distribution que l'on à choisie, la qualité de la dite
distribution, le sérieux de l'équipe qui est derrière et la santé de
celle-ci.
