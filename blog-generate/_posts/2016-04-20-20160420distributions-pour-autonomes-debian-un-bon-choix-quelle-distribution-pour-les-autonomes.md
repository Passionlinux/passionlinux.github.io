---
title: Distributions pour autonomes, Debian un bon choix ? Quelle distribution pour les autonomes ?
date: 2016-04-20 17:55
layout: post
---
<div class="main">

<div class="chapo surlignable">

Dans le dernier article [Distributions pour novices, Debian un bon
choix ? Quelle distribution pour les
novices ?](http://passiongnulinux.tuxfamily.org/?p=55), on a parlé des
éternels débutants, ceux qui ne veulent pas apprendre et veulent juste
se servir de leurs pc, pas faire des mises a jour mais naviguer sur le
web, ne pas installer des paquets mais avoir déjà ce qu’ils leur faut.  
C’est au tour des débutants autonomes cette fois ci, on va voir quelle
distribution leurs convient et pourquoi debian plus particulierement.
Ces utilisateurs qui vont installer par eux même la distribution ou par
un tier, qui vont être autonome, qui vont chercher les réponses dans les
forums et sur irc,

</div>

<div class="texte surlignable">

Au dernier billet, j’avais commencé par :  
> « Dans les deux premiers cas, je serais plutôt tenter de dire qu’une
> distributions comme Mageia serait idéale, j’ai eu la même approche a
> mes débuts avec Mandriva et je ne regrette rien, c’est une
> distribution solide, stable, a jour mais en privilégiant les versions
> avec support a long terme (firefox esr, kernel lts,…). Elle a
> notamment un centre de contrôle (du nom de ccm ou mcc) qui permet de
> faire toutes les choses réserver a l’administrateur et qui se fait
> normalement en ligne de commande comme l’installation ou suppression
> de paquets, mise a jour, activation ou désactivation de services, mise
> en place de serveur(serveur web, mail,…), un pare feu et même une
> partie sécurité qui permet de gérer au mieux la sécurité de son
> système avec un nombre de vérification automatique. Ce qui caractérise
> cette distribution est le sérieux de l’équipe derrière, la plupart de
> l’équipe sont des anciens de Mandriva, son ccm, ses outils non
> graphique hérité eux aussi de Mandriva (commençant par drakX) et un
> installateur simple, compréhensible avec peu de terme « pro linux ».
> On peut aussi penser a (?)Ubuntu et openSUSE. Pour les plus courageux
> on peut penser a Debian mais j’y reviendrais plus tard dans un autre
> article ! »
> </p>

Je pense qu’il y aura assez de personnes ou de sites qui parleront des
avantages des distributions comme mageia, opensuse, mint ou ubuntu donc
on va se recentrer sur debian, pourquoi et comment debian peut être
parfait pour les novices.  
<!--more-->  
On va certainement me dire que je suis un fanatique qui prêche pour son
église mais debian a toutes les qualités imaginables pour une telle
aventure. Tout d’abord, c’est une des distributions les plus pérennes,
elle a plus de vingt ans, une des plus grosse (voir la plus grosse)
communauté, elle a la plus grosse bibliothèque de paquets, elle est
disponible en trois saveur (stable, testing et sid) toutes utilisables
et destinés a différents usages et différents utilisateurs. On pourrait
par exemple imaginer commencer sur une stable qui permet grâce a sa
grande stabilité d’apprendre les rouages puis une fois les bases
apprises et assimilé, migrer vers une testing ou une sid… Mais avant
tout commençons par le début c’est a dire une stable.  

### Debian, un projet, une méthode, qui a fait ses preuves : {#outil_sommaire_0 .spip}

Pourquoi commencer avec une stable ? C’est assez simple, c’est la seule
qui est reconnue par debian pour être utiliser en tout temps, c’est la
seule qui a du support, c’est aussi celle qui est la finalité du projet.
Pour comprendre, il faut remonter a la source et voir comment le projet
debian travail :  
![Comprendre
Debian](http://download.tuxfamily.org/passionlinux/images/infographic_debian-v2.1.en.png)  
Comme on peut voir, les développeurs debian commence par empaqueter
leurs logiciels attitré dans sid, qui au passage veut dire Still In
Developpement (traduis comme on peut par toujours en développement),
c’est donc la que les nouvelles versions des programmes arrivent, le
dernier firefox, le dernier gnome, ect,… C’est un peu le bac a sable, ça
bouge beaucoup, les bugs ne sont pas forcement détecté, il peut y avoir
des problèmes de dépendances, des incompatibilités avec d’autres
paquets, des bugs amont non vu car trop frais, en faite tout les soucis
qui peut arriver quand on utilise des distributions a jour ou a
publication continue dite « rolling release ». On est sous sid déjà
quand on a un certain niveau ou plutôt une certaine connaissance de son
système, pour avoir les dernières versions de tous les logiciels, pour
participer au développement de debian. En tout cas pas pour passer pour
quelqu’un de cool, ni se la péter, car si il y a un soucis, et ça
arrivera, il n’y aura aucune aide. Ensuite, après plusieurs jours dans
les dépôts de sid, les paquets vont migrer dans testing, après divers
vérifications, les paquets ne doivent pas comporter de grosse faille ni
de faille plus important que la version déjà présente dans testing.
C’est la futur stable, c’est une version de transition, je préfère
souvent etre sous sid que sous testing, car les paquets d’un ensemble
comme gnome par exemple, peuvent arriver en compte goutte, souvent parce
que les dépendances ne peuvent être satisfaite, ou que tel programme a
un bug,… Tous les deux ans, testing est gelé pour ne laisser passer que
les corrections de bugs. Après un certains nombre de mois (8 mois en
moyenne), testing devient la stable. La stable est quant a elle et comme
son nom indique, stabilisé, aussi bien au niveau des failles ou des bugs
mais aussi des depots qui doivent plus bouger. Seul des corrections de
failles et de bugs peut être proposer. L’évolution de cette distribution
peut ressembler a une pyramide, en bas les fondations, c’est sid,
beaucoup de changement, beaucoup de mise a jour, puis au milieu les
arrangements, c’est la testing, un peu moins de mises a jour qui doivent
surtout comporter moins de bugs que la version actuellement dans ce
dépôt, et au sommet c’est la stable, seul des correction de bug ou de
faille, on vise la perfection au niveau stabilité. Bon tout ça est dans
un [autre
article](http://passiongnulinux.tuxfamily.org/?p=52){.spip_in}, bien
plus compréhensible.  

### Qualité de la version stable de debian : {#outil_sommaire_1 .spip}

Debian stable comporte plusieurs avantages face aux autres pour
commencer,

-   c’est la plus connue et la plus populaire des distributions, ce qui
    nous donne une certitude de sa pérennité et la sûreté de trouver de
    l’aide dans sa langue.
-   La version stable comme on a pu voir plus haut, ne bouge pas, les
    mises a jour ne sont la que pour corriger des failles ou des bugs,
    pas d’ajout ou de perte de fonctionnalités et pas de mises a jour
    pour augmenter les numéros de versions.
-   Des dépôts qui ne bougent pas, donc pas de risque de voir
    disparaître son logiciel ni d’avoir la chance de voir apparaître le
    dernier logiciel a la mode, pendant toute la durée de vie de la
    stable actuelle.
-   Un installateur qui ne bouge pas, qui ne change pas a chaque sortie,
    cependant il s’améliore mais pas de révolution ! Traduit dans
    plusieurs langue dont le français. Il permet d’installer différents
    bureaux comme kde, gnome, xfce, mate, cinnamon, … et différent
    services comme des serveurs web, ftp, ssh, mail, …
-   Une documentation très complète dans différentes langues, dont le
    français, comme des wikis, des livres disponible gratuitement ou a
    l’achat sur le web et dans les commerces…
-   Plusieurs forums français.
-   De nombreux outils reconnues par tous pour géré sa debian.
-   Un outils de gestion de paquets très robuste connu sous le
    nom d’APT.
-   Un format de paquets parmi les plus populaires.
-   Des milliers de développeurs.
-   Un nombre important de logiciels installable dans ses depots.

Nous verrons tous ces points ensemble.  

### L’installation de notre debian : {#outil_sommaire_2 .spip}

L’installation n’est pas très compliqué, c’est sur que c’est pas aussi
facile que Mint, Ubuntu, Mageia, openSUSE ou Manjaro mais ça n’a rien a
voir avec la technicité d’une installation de arch ou de gentoo. Si on
connais déjà un peu les distributions, on aura aucun soucis et a part le
moment de partitionner, il n’y a rien de compliqué. Surtout que
l’installateur par défaut cache pas mal de chose plus technique, on peut
si on veut choisir le niveau de personnalisation qui par ricochet
augmente les questions et par la même la difficulté de l’installation.
Une installation classique de debian :  
[Étapes du programme d’installation de Debian
Jessie](http://passiongnulinux.tuxfamily.org/?p=53){.spip_in}  
ou  
[Installation Debian 8
(Jessie)](http://passiongnulinux.tuxfamily.org/spip/spip.php?article211){.spip_in}  

### Les dépots free, nonfree et contrib : {#outil_sommaire_3 .spip}

Si vous venez d’installer debian depuis une clé USB ou un CDROM,
commencez par commenter ou supprimer les lignes des sources commençant
par : `deb cdrom:[Debian GNU/Linux etc...`{.spip_code dir="ltr"} Le
fichier sources.list suivant propose les même paquets que le
sources.list de base, et inclut également les paquets non libres ou
dépendants de ressources non-libres proposés dans les sections contrib
et non-free.

<div class="spip_code" dir="ltr">

`# Debian Jessie, dépôt principal + paquets non libres deb http://httpredir.debian.org/debian/ jessie main contrib non-free # Debian Jessie, mises-à-jour de sécurité + paquets non libres deb http://security.debian.org/ jessie/updates main contrib non-free # Debian Jessie, mises-à-jour "volatiles" + paquets non libres deb http://httpredir.debian.org/debian/ jessie-updates main contrib non-free`

</div>

Le dépôt backports propose des paquets plus récents ou absents du dépôt
principal. Ces paquets sont dérivés de la version de test et peuvent
être installé sur une Debian stable. Il servira à ceux qui ont
absolument besoin d’une version plus récente d’un logiciel, mais ne
veulent pas compromettre la stabilité générale de leur système en
migrant vers testing. Si vous avez besoin d’installer un paquet depuis
le dépôt backports de la branche jessie, ajoutez le dépôt suivant à
votre fichier sources.list :

<div class="spip_code" dir="ltr">

`# Debian Jessie, dépôt de rétroportages ("backports") deb http://httpredir.debian.org/debian jessie-backports main contrib non-free`

</div>

Pour installer un paquet depuis le dépôt backports, il faut le spécifier
explicitement.  
Exemple : pour installer la dernière version de libreoffice disponible
de le dépôt backports :
`apt-get -t jessie-backports install libreoffice`{.spip_code dir="ltr"}
Par la suite, les paquets installés depuis les backports se mettront
automatiquement à jour comme pour les paquets issus de la branche
principale, seule la mise-à-jour initiale vers la version rétroportée
nécessite cette déclaration explicite de la branche. Ce système est en
place pour éviter que tous les paquets proposant une version candidate
dans les backports soient automatiquement mis-à-jour dans cette version,
ce qui n’est généralement pas le comportement souhaité par
l’utilisateur.  
[Voir le wiki de
debian-facile](https://debian-facile.org/doc:systeme:apt:sources.list){.spip_out}
Nous pouvons bien sur tout faire en graphique via Synaptic :  
Les dépôts permettent de mettre à jour et d’installer des paquets
supplémentaires. Ouvrez le gestionnaire de paquets Synaptic (dans le
menu : Système &gt; Gestionnaire de paquets Synaptic). Dans le menu de
Synaptic, cliquez sur configuration puis Dépôts.  
Une fenêtre comme celle-ci s’ouvre :

<div style="text-align: center;">

![synaptic
depots](http://download.tuxfamily.org/passionlinux/IMG/distant/jpg/file-Rb91aff65da.jpg)

</div>

Il ne vous reste plus qu’à modifier vos sources de dépôts à votre
convenance. Cliquez simplement sur une source pour pouvoir la modifier
ou sur nouveau si vous voulez ajouter une nouvelle source.  
Une fois vos modifications validées, vous serez invités à recharger la
liste des dépôts pour qu’elles soient prises en compte.  

### Les finitions, apparence et logiciels : {#outil_sommaire_4 .spip}

Ce n’est pas comme sous certaines distributions telle que Mageia ou
Ubuntu, les applications ne sont pas forcement bien intégré a son
environnement, par exemple, des applications gnome dans kde sont pas du
tout intégré et des applications kde ne seront pas intégré a un
environnement gtk(gnome,xfce, mate, cinnamon). Il faut donc installer
des paquets qui sont installé chez d’autres distributions (toujours les
même), notamment pour kde : Pour que les applications gtk aient leur
apparence native avec Plasma, on doit installer les paquets suivants et
configurer l’apparence des applications avec configuration du système
&gt; Apparence des applications. kde-config-gtk-style -&gt; module de
configuration de KDE pour la sélection du style GTK+ 2/3.x
gtk2-engines-oxygen -&gt; Thème Oxygen pour les applications basées sur
GTK2+ gtk3-engines-oxygen -&gt;Thème Oxygen pour les applications basées
sur GTK3+  

### Apt, gestionnaire de paquets : {#outil_sommaire_5 .spip}

APT (Advanced Packaging Tool) est une collection d’outils permettant de
gérer les logiciels installés sur une machine de façon relativement
simple et complète. C’est un système de gestion de paquet robuste et
élégant, qui a longtemps fait la fierté de Debian. Le fonctionnement est
le suivant : APT conserve une liste des paquets installés, avec leur
version, et leur état. Par exemple, lorsque vous installez un paquet,
celui-ci est marqué comme manuellement installé. En revanche, si ce
paquet dépendait d’une bibliothèque, alors celle-ci a été installée
automatiquement, et marquée comme telle. En parallèle, APT conserve une
liste des paquets installables. Il récupère cette liste depuis les
dépôts précisés dans les fichiers /etc/apt/sources.list et
/etc/apt/sources.list.d/\* (ces dépôts sont la plupart du temps des
sites internet, mais peuvent également être des cdrom ou des miroirs
locaux). Les outils permettent ensuite d’installer des paquets
facilement depuis ces dépôts, ou depuis des fichiers .deb téléchargés
manuellement (bien que cette dernière méthode soit déconseillée.) **Pour
Mettre à jour (Update) :**  
Cette opération a deux buts bien précis :

-   Rechercher les méta-données d’une archive depuis l’archive distante.
-   Reconstruire et mettre à jour les méta-données locales pour qu’elles
    puissent être utilisées par APT.

`apt-get update`{.spip_code dir="ltr"} **dist-upgrade Mise à jour
complète :**  
`apt-get dist-upgrade`{.spip_code dir="ltr"} **Installation d’un
Logiciel :**  
`apt-get install LeNomDuLogiciel`{.spip_code dir="ltr"}
**Désinstallation d’un logiciel :**  
`apt-get remove lenomdulogiciel`{.spip_code dir="ltr"} [Voir une
documentation
complète](https://debian-facile.org/doc:systeme:apt){.spip_out} Rassurez
vous tout peut se faire de façon graphique avec par exemple l’outils
Synaptic :

<div style="text-align: center;">

![synaptic](http://download.tuxfamily.org/passionlinux/IMG/distant/jpg/file-R5469f09f80.jpg)

</div>

Synaptic est un outil complet qui permet la gestion des paquets
(=installer un logiciel) et la gestion des dépôts debian, en mode
graphique.  
Il fournit les mêmes fonctions que l’outil aptitude ou apt-get ou apt.  
Il est installé par défaut si vous avez coché la tâche bureau en
installant votre Debian, sinon il faudra l’installer.  
Vous aurez besoin du mot de passe de l’administrateur pour ouvrir et
utiliser Synaptic.  
Une connexion internet active est également nécessaire.  
[Voir en
ligne](https://debian-facile.org/doc:systeme:apt:synaptic){.spip_out}  

### Ou trouver la documentation ? {#outil_sommaire_6 .spip}

Alors avec debian c’est très simple, un peu partout !  
On peut la trouver dans des livres commerciaux de bonne qualité, comme
[Debian Administration et configuration
avancée](http://passiongnulinux.tuxfamily.org/?p=119){.spip_in} ou
[Debian Etch(cahier de
l’admin)](http://passiongnulinux.tuxfamily.org/?p=118){.spip_in}
disponible dans une [version plus
récente](http://www.eyrolles.com/Informatique/Collection/1416/cahiers-de-l-admin){.spip_out}.
On peut aussi trouver le livre [Le cahier de l’administrateur
Debian](https://debian-handbook.info/browse/fr-FR/stable/index.html){.spip_out},
livre communautaire, libre et gratuit (mais on peut aussi l’acheter et
participer a sa création). Il y a de nombreux wiki comme
[Linuxpedia](http://www.linuxpedia.fr/doku.php){.spip_out} ou des wiki
plus centrer sur debian, comme celui de
[debian-facile](https://debian-facile.org/wiki){.spip_out} ou encore la
[documentation
officiel](https://wiki.debian.org/fr/FrontPage?action=show&redirect=PageD%27Accueil){.spip_out}
du projet traduite dans plusieurs langues. Il n’est vraiment pas dur de
trouver ce que l’on a besoin pour son utilisation quand on est sous
debian. Je devrais pas le dire, mais on peut tout aussi bien utiliser la
documentation très complète de
[ubuntu](http://doc.ubuntu-fr.org/){.spip_out} qui issu de debian, a de
nombreux points communs, on peut donc facilement trouver une solution et
l’adapter a debian.  

### Plusieurs forums français. {#outil_sommaire_7 .spip}

On a la possibilité de trouver de l’aide dans plusieurs forums,
[andesi](http://forum.andesi.org/){.spip_out} ,
[Debian-facile](https://debian-facile.org/forum.php){.spip_out} ou
[debian-fr.org](https://www.debian-fr.org/){.spip_out} , il y en a
d’autres aussi qui ne sont pas dédié uniquement a debian.  

### Pourquoi debian ? {#outil_sommaire_8 .spip}

Alors pourquoi debian et pas d’autres déjà prévu pour les novices ?
C’est simple, debian stable avec sa politique d’être la plus stable, qui
veut dire selon debian, stabilité des dépôts, stabilité des logiciels,
stabilité du système, permet de ce recentrer sur le plaisir d’utiliser
et d’apprendre son système au lieu de le maintenir. Imaginez un système
qui est toujours en train de changer, des applications qui du jour au
lendemain apparaissent ou disparaissent des dépôts, des mises a jour
quotidienne qui ne font que changer les versions des programmes,
incluant donc des risques de nouveaux bugs, des logiciels qui changent
de noms sans prévenir ou leurs fichiers de configuration changent
d’emplacement, des ajouts mais aussi des pertes de fonctionnalités,…,
tout ça se trouvent chez les autres mais pas chez debian !!! Chez
debian, les programmes ne changeront pas de noms, leurs fichiers ne
changeront pas d’emplacement, les fonctionnalités des logiciels ne
bougeront pas, les dépôts auront toujours le même nombre de logiciels,
donc pas de perte de logiciels ni d’ajout, seulement des mises a jour de
corrections, et tout ça pendant le temps de vie de la version (3 a 5
ans). Ce qui laisse assez de tranquillité pour apprendre tout le reste,
l’usage, les commandes, la particularité de son système linux par
rapport aux autres systèmes notamment l’absorption des divers
environnements sous linux et j’en passe. Je pense avoir passé en revu
les points que je voulais aborder, je pense surtout que toute personne
un peu curieuse pourra d’elle même regarder dans les différents lien
donné et en faire son idée pour se lancer.

</div>

</div>

   

<footer>
 

</footer>

