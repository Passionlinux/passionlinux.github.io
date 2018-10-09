---
title: L'innovation du côté de chez Debian, est-ce un but en soi? #1 Debian vs RedHat
date: 2016-07-29 16:07
layout: post
---

Je lis beaucoup de blog, je donne mon avis sur beaucoup de billets dans
les commentaires de ces blogs, c'est comme ça que je tombe sur des
pépites de réflexions, comme celui de
[Cascador](https://www.blog-libre.org/author/cascador "Afficher tous les articles de « Cascador »"){.url
.fn .n}: [L’innovation du côté de chez Red
Hat](https://www.blog-libre.org/2016/04/02/linnovation-du-cote-de-chez-red-hat/).
Comme je suis quelqu'un qui manque un peu d'imagination ou plutôt qui
est faignant par moment, je n'ai pas eu d'autre idée que de reprendre
son titre et de le modifier a peine. Cascador a prévu [de nous faire une
série](https://www.blog-libre.org/2016/07/27/en-retour-5/), le premier
billet de cette série est celui de
[RedHat](https://www.blog-libre.org/2016/04/02/linnovation-du-cote-de-chez-red-hat/),
un autre doit parler de la "famille" Ubuntu et le dernier de Debian.
J'aimerais qu'il pousse l’exercice encore plus loin, en parlant des
"familles" Gentoo et Slackware, voir même Archlinux. Je le remercie au
passage pour nos échanges toujours agréable par courriels et surtout de
me donner de quoi écrire.  
<!--more-->  
Voici un extrait qui montre le ton des billets:  

> Debian ferait mieux d’arrêter de toiser du regard les autres
> distributions et redescendre dans l’arène de l’innovation pour
> rappeler à tous qui est la patronne.
> </p>

De mon coté, je ne pense pas que RedHat et Debian soient dans la même
cour, ils n'ont pas les mêmes valeurs, la même histoire, le même but,
ils sont totalement opposés, d'un coté une boite qui vit en vendant un
système et des services autours, de l'autre un projet communautaire qui
vise a donner le meilleur a ses utilisateurs. Je pense que ce n'est pas
comparable, RedHat a un besoin de vendre ses services, de vendre son
systèmes, pour cela il innove forcement, comme le fait SUSE ou Canonical
dans une moindre mesure. Du reste pour se concentrer sur cette tache et
ne pas entacher sa réputation, RedHat avait arrêté le support de sa
distribution "public" gratuite, et passa a un modèle de distribution
portant un autre nom (Fedora) et qui sert de laboratoire, un test
grandeur nature, nous sommes les rats de leur labo... SUSE a pompé le
modèle en faisant exactement pareil. Je voudrais poser une question,
comment vendre un système qui n'innove pas? Qui n'apporte rien de plus
que ceux qu'on peut trouver ailleurs en gratuit et en ayant un support
beaucoup moins chère? Je prends l'exemple de Debian, elle est gratuite
et je peux facilement trouver du support parmi les nombreuses sociétés
qui travaillent dans ce domaine. De plus vu les prix pratiqué par RedHat
et SUSE, je vois pas l’intérêt pour le public, ce n'est pas son but non
plus, son terrain c'est les serveurs et les postes professionnels. Donc
Cascador nous donne des exemples:  

> On commence par [Cockpit](http://cockpit-project.org/) qui fait partie
> d’un projet plus vaste,
> [Atomic](http://www.projectatomic.io/docs/introduction/). Cockpit est
> une interface d’administration de serveurs GNU/Linux comme il en
> existe tant. La particularité étant qu’il est développé par Red Hat
> gage de qualité et de pérennité important. C’est disponible pour Red
> Hat, Fedora, CentOS, Debian (Ubuntu et Arch Linux en bêta) mais je
> précise qu’il n’est pas encore recommandé pour des serveurs en
> production.
> </p>

Cockpit est une nouvelle interface d’administration et de monitoring,
cet [article en
Français](http://www.dsfc.net/logiciel-libre/linux/fedora-linux-logiciel-libre/cockpit-interface-administration-linux-fedora/)
vous en montre un peu plus. Je ne sais pas mais ça me rappel vaguement
quelque chose, je ne suis pas un pro de ces trucs la, mais a première vu
et suite a la description qui en est fait, ça me fait pensé a
[Webmin](https://fr.wikipedia.org/wiki/Webmin). Puis il y avait aussi
[ebox-platform](https://fr.wikipedia.org/wiki/Zentyal), qui était un peu
comme Webmin mais pour Debian, depuis il a l'air de se diriger vers une
distribution autonome a base d'Ubuntu et n'a plus l'air d’être un
programme d'administration... Je pense aussi et surtout a
[YAST](https://fr.opensuse.org/Portal:YaST) de SUSE, qui permet de
paramétrer le système rapidement pendant et après l'installation, il
peut être utilisé pour configurer votre système entier. Configuration
matérielle, configuration du réseau, services système et ajustement des
paramètres de sécurité, toutes ces tâches peuvent être effectuées depuis
le *Centre de contrôle de YaST*. De plus il possède plusieurs
interfaces, Web, Ncurse, QT ou GTK... Donc c'est pas vraiment une
innovation mais un nouveau outils qui permet de faire ce que d'autres
font. Je passe a l'innovation suivante:  

> Les dépôts tiers **EPEL** issus de Fedora sont un principe très
> intéressant. Sur Red Hat/CentOS on peut installer les paquets de
> Fedora, c’est un peu comme si on pouvait aisément (c’est-à-dire sans
> tout casser avec des problèmes de dépendances) installer des paquets
> Ubuntu sous Debian. Les paquets de
> [EPEL](http://fedoraproject.org/wiki/EPEL) sont frais et très stables.
> </p>

Je dois admettre que sur le papier et vu comme ça nous a été vendu c'est
très intéressante, maintenant quand tu payes une licence au prix de
RedHat, je ne sais pas si t'as envie de fragiliser le système avec les
paquets labo de Fedora. Du reste comparé Ubuntu et Fedora, je ne sais
pas si c'est vraiment comparable encore une fois, Ubuntu est moins
"labo" que Fedora et elle a des versions LTS d'une grande stabilité
(égale a Debian?). Donc je vais reformuler cette phrase enthousiaste de
Cascador: *C’est un peu comme si on pouvait aisément (c’est-à-dire sans
tout casser avec des problèmes de dépendances) installer des paquets de
testing/sid sous Debian Stable.* Et donc, ce n'est pas déjà le cas?
Pourtant un simple *apt-get -t testing install nom-du-logiciel* me le
fait déjà. Le point suivant cité par notre ami est a peu prés pareil, en
tout cas pour un non initié:  

> On continue avec les [Software
> collections](https://www.softwarecollections.org/en/) (SCL)... De
> prime abord on peut se dire qu’on peut faire la même chose sur Debian
> car il s’agit d’installer une version plus récente d’un package (PHP
> par exemple), c’est mal analyser la situation. On peut installer
> **ensemble** PHP 5.3 et PHP 5.4,...
> </p>

La j'ai un doute si c'est possible avec Debian, il me semble que oui
mais est-ce faisable simplement, je dirais non. Sous Debian, il nous
faudrait reprendre le deb-source, de lui donner un autre nom et de
relancer la création du paquet. J'ai quand même un doute sur ça, car il
me semblais déjà avoir vu plusieurs php sur ma machine. J'admets de ne
pas savoir si c'est faisable. L'utilité pour moi n'est pas flagrant,
RedHat a une durée de vie de 10 ans, Debian de 3 ans officiellement (+
si affinité), en 3 ans il y a bien moins de paquets totalement obsolète
qu'en 10 ans, de plus avec les backports, on peut quand même se servir,
et en dernier recours il y a soit l'installation de paquets via
Testing/Sid (pinning pour les puristes) ou la possibilité de faire un
paquet pour la version Stable de Debian a partir des sources de Testing
ou Sid. Par contre la on on s’égare réellement c'est:  

> Une release majeure de Red Hat et CentOS c’est quasiment 10 ans de
> mises à jour de maintenance. Par exemple CentOS 6 sortie en juillet
> 2011, c’est Full Updates jusqu’au 2ème trimestre 2017 et Maintenance
> Updates juqu’au 30/11/2020. Oui c’est impressionnant. [Debian
> LTS](https://wiki.debian.org/fr/LTS) a été lancé il y a deux ans et
> vise à étendre la durée de vie de toutes les versions stables de
> Debian à (au moins) 5 ans. Pour résumer chez Red Hat on a la durée de
> vie et la souplesse (SCL, EPEL…).
> </p>

RedHat est, comme dit plus haut, une société a but lucratif, elle doit
se vendre, elle doit garder ses utilisateurs, elle est faite pour le
domaine professionnel, sinon elle mourra. Pour ce faire tout est bon, un
support **payant** de dix ans, des innovations pour faciliter la vie des
administrateurs et elle garantie son utilisation dans le temps et sur du
matériel... Debian quant a elle, n'est pas issue d'une société
commerciale, c'est du communautaire, fait par et pour ses utilisateurs,
a aucun moment il n'est dit qu'elle est prévue pour le domaine
professionnel, aucune garantie de fonctionnement, rien. Un support de 10
ans pour le particulier serait ridicule, 2-3 ans a la rigueur mais même
le projet LTS qui pousse le support a 5 ans n'est pas pour le
particulier mais pour ceux qui utilisent Debian comme outils
professionnel. Si je me trompe pas RedHat c'est du pure gnome, la ou
Debian propose un paquets de bureaux, comme kde, gnome, lxde, mate,
cinamon, xfce... Debian est gratuite la ou il faut débourser 799\$ pour
1 an de Red Hat Enterprise Linux Server... A ce prix la, j’espère qu'il
y a plus que les innovations parlés et que le support est dans le prix.
Peut être qu'une boite peut se permettre de se payer une RedHat mais
certainement pas la petite association du coin et encore moins le
particulier que je suis. Debian n'innove pas, elle n'en a pas besoin
puisqu'elle ne vend ni services ni quelconques autres supports. Elle n'a
donc pas besoin de se vendre, d’être attirante pour appâter le client.
Donc elle n'innove pas, ou plutôt elle ne révolutionne pas comme le font
SUSE, RedHat ou Canonical, par contre elle évolue pas mal. Je sais pas
si vous vous rappelez, mais avant Jessie, il fallait choisir le CD
d'installation du bureau voulu (CD1 c'est gnome, CD kde, CD Xfce...),
sur la net-install et le DVD il fallait aller dans les options de
démarrage du DVD et sélectionner le bureau voulu (kde, xfce,...) ensuite
lancer *install* ou *install-gui*, gnome étant le choix par défaut si on
faisait *enter*. Maintenant, l'installateur nous permet de sélectionner
le bureau voulu pendant le choix de paquets. Encore mieux, il est même
possible de cocher plusieurs bureaux, chose plutôt rare chez les autres
distributions qui permettent la plupart du temps d'installer un seul
bureau pendant la phase d'installation. Pas d'innovation mais des
améliorations, ou comment appel t'on alors un installateur qui
s’améliore de version en version, qui facilite de plus en plus la vie,
qui automatise certaine action? Pourquoi toujours s'attendre a des
révolutions alors que la plupart de celles-ci n'ont apporté plus de
terreurs que de bonheurs? Un exemple dans ma tête, la révolution
Française, bien sur qu'elle partait d'une bonne intention, mais ce qui
suivirent fut plus terrible, la période de la Terreur, décapitation d'un
roi, décapitation de nombreux innocent, guerre, ... Gnome3 est une
révolution, est ce mieux que l’évolution douce de Xfce? Celle de KDE4
vers KF5? Gnome2 était apprécié, je l'aimais bien même si je suis un
kdeiste convaincu depuis 2006... Mais gnome3, j'ai mis longtemps avant
de l'apprécier, convaincu qu'il y avait besoin de faire un tel
changement? Non et je ne suis pas le seul vu la création et le succès de
Cinamon, Mate, Unity... Une évolution en douceur aurait eu moins
d’impacts négatifs. Xfce bouge peu, mais il avance, il évolue sans faire
de révolutions, il compte pas changer pour changer mais de s’améliorer
pour devenir parfait. Debian a le même layout de raisonnement, comme SPIP,
Dotclear, PluXml, qui évoluent en douceur car ils ont un modèle de
business de layout communautaire ou plutôt ils n'ont pas de business
contrairement a RedHat, SUSE, et même Wordpress dans son domaine (le
CMS). Sans rire, qui irait payer une somme pas négligeable pour un
produit qui se reposerait sur ses lauriers alors que des alternatives
gratuits existent? Maintenant on va parler du support, dix ans de
support et même plus il me semble pour Redhat si on adhère a des
options, c'est tout bénef sur des serveurs, sur des postes de travail
professionnel c'est déjà un peu trop long mais ça laisse de la
tranquillité et vu le nombre d'entreprise qui restent avec des XP, ça
semble pas si fou... Mais, car il y a un mais, il n'est pas encore
possible de passer d'une version de RedHat a une autre par simple
Update, pas encore possible car Redhat travail sur ce problème... Donc
si je prend Debian maintenant, je n'ai que trois ans de supports, voir 5
ans avec le support LTS, par contre le passage d'une ancienne version
stable de Debian a la suivante est prévu, c'est testé de longs mois et
approuvé, parfois il faut faire des manipulations qui sont indiqués sur
le site. Donc en théorie, il est possible de faire le passage d'une
version a une autre en faisant de simples mises a jour, donc d'avoir
toujours la version Stable supporté par le projet. Si je parle de
tarifs, Debian est gratuite, on peut faire des dons en nature ou en
argent, mais rien ne vous y oblige et le support est gratuit pour ce qui
est des forums, listes ou salons IRC, il y a aussi du support payant
apportée par des sociétés externes. RedHat c'est des tarifs indiqué sur
leur [site](https://www.redhat.com/wapps/store/allProducts.html), alors
je n'ai pas bien compris si on paye pour un an de support, a t'on au
delà des 1ans, encore les mises a jour venant du chapeau rouge ou non?
Le fameux support, qu'il y a t'il dedans? Les mises a jour seules, ou le
support téléphonique ou autre est aussi compter dedans? Une personne
comme moi en a rien a foutre de dix ans de support, il veut du stable
mais pas trop obsolète non plus, la ou sont nombreux ceux qui critiquent
déjà l'obsolescence de Debian et de ses versions sortant tout les deux
ans, on oublie alors le support de dix ans. Pour une organisation
non-lucratif, une association de quartier pourra et se tournera plus
facilement vers une Debian pour sa gratuité, sa stabilité, son support
gratuit, son entretien... Du reste pas mal de grosse boite tournent sur
du Debian et participe a rendre un peu a celle ci en mettant a
disposition des développeurs ou en donnant du matériel ou encore en
donnant de l'argent... J'avais cru comprendre que les serveurs de Google
tournaient sur du Debian/Ubuntu mais n'arrivant pas a mettre la main
dessus je n'en dirais pas plus. Je dirais encore une chose, dans le
modèle purement communautaire de Debian, il serait suicidaire de faire
du support de 10ans pour la simple raison, que pour le faire il
faudrait:

-   soit faire une Stable tout les dix ans, ce qui a terme tuerait
    Debian car moins de sorties est égale a moins de visibilité sur
    le net. On peut voir que Debian est devenu bien plus populaire
    depuis que le projet sort fréquemment une version tous les deux ans,
    alors qu'avant ça pouvait varier.
-   soit on garde les sortie toutes les 2ans mais du coup ça augmente la
    charge de travail pour la maintenance, il y aurait 5 version stable
    a maintenir en même temps...

Pour RedHat, le soucis ne se pose pas, il y a une ou deux version a
maintenir dans les dix ans. Bon ce billet étant déjà plus long que
prévu, je continuerais la suite sur un prochain mettant en scène Debian
vs Centos. D'autres devraient aussi venir prochainement.
