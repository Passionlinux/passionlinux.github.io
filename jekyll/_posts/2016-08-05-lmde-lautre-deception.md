---
title: LMDE, l'autre déception...
date: 2016-08-05 22:12
layout: post
---

J'en avais déjà parlé
[ici](http://passiongnulinux.tuxfamily.org/2016/07/09/20160709de-handylinux-a-dflinux-une-fin-ou-un-eternel-recommencement/)
mais je voulais redonner une chance a cette version de Mint qui a pour
base Debian. Je parlais notamment des différentes failles de cette
distributions dont le manque d’intérêt de ses développeurs:  

> ... comme Mint Linux Debian Edition (LMDE) pour ne citer qu’elle…
> Celle-ci a raté le coche, d’abord elle a fait une première version de
> lmde basé sur testing de Debian avec une temporisation des paquets
> permettant, en théorie, de stabiliser la bête sauf que préoccupé par
> le succès de sa Mint basé sur Ubuntu, elle l’a délaissé tellement que
> l’écart entre testing et lmde s’agrandit, qu’il n’était plus possible
> pour l’équipe de proposer des mises a jour sans casser la
> distribution,...
> </p>

<!--more-->  
Je l'ai dis dans ce même billet mais je vais le redire, c'est mal joué
et a terme ils vont se tuer a essayer de refaire marche arrière. La
famille Mint et moi avons un passif des plus désagréable, je dois bien
admettre que je ne suis pas fan des forks, des dérivés et rare sont les
dérivés qui me fassent dire le contraire. La LMDE ne fait décidément pas
partie des distributions que j'admire, elle et sa sœur Mint, je préfère
vraiment utiliser les originaux que sont Debian et Ubuntu. Les défauts
pour moi de ces deux distributions, sont d'un coté le "<span
class="dico_title_2">je-m'en-foutiste"</span> de la sécurité, on le vois
avec ce qui c'est passé ces derniers temps comme les dépôts, archives et
forums corrompus. [Cyrille en parle sur son
blog](https://www.cyrille-borne.com/article2239/linux-mint-site-pirate-donnees-a-vendre-et-iso-infecte)
bien mieux que je ne pourrais le faire:  

> Mauvaise nouvelle pour Mint et pour Linux en général, des isos ont été
> modifiées pendant un moment, ce qui prouve bien qu'on n'est à l'abris
> de rien. Vous avez dans l'annonce officiel de Clément Lefebvre la
> procédure à suivre si vous êtes concernés. Couper la machine du net,
> faire la backup des données, formater et réinstaller.
> </p>

Mais c'est pas tout, quand je dis que l’équipe des Mints se foutent de
la sécurité c'est bien pour autre chose qu'une attaque d'un con de
pirate qui a rien mieux a faire de ses dix doigts ou pas qui n'a pas les
couilles de s'attaquer a la marque de la fenêtre informatique, ou a la
pomme! Non je parle surtout de la méthode un peu picoré de faire des
mises a jour sous Mint et LMDE.
[Frédéric](http://frederic.bezies.free.fr/blog/) en parle
[ici](http://frederic.bezies.free.fr/blog/?p=14848) dans un billet bien
intéressant et je dois dire que je suis totalement et pour une fois ou
rare fois, de son avis. Cette manière de catégoriser et de sélectionner
les mises a jour a faire et d'autre qu'on peut éviter car sensible a
faire, c'est d'un ridicule! Donc si le kernel est atteint par une grosse
faille de sécurité, on ne nous propose pas de la faire, elle sera en
rouge ou orange, car sensible et peut casser le système, donc toujours
d’après eux, en tout cas c'est comme ça que je le comprend, il vaut
mieux être en présence d'une faille que de mettre a jour car sensible...
Je ne suis pas le seul a penser au ridicule de la situation, avant
Frédéric, [Cep a lui aussi balancé sur cette méthode de Mint sur le blog
de
Cyrille](https://www.cyrille-borne.com/article2291/linux-et-la-securite-quelques-elements-factuels):  

> À titre d'exemple je prendrai la **Mint**, et plus exactement sa
> version **LMDE 2 Betsy**. Là, c'est flagrant, ses utilisateurs courent
> des risques, et plus particulièrement s'ils font les mises à jour avec
> l'utilitaire dédié, mintupdate. Ce dernier va récupérer la liste des
> paquets à mettre à jour, liste bien différente de ce qui se passe si
> on utilise apt ou aptitude pour maintenir sa distribution à jour. Par
> exemple à l'heure ou j'écris ce billet, sur une LMDE 2 amd64 (mais
> c'est la même choses avec une i386) le dernier noyau disponible est le
> noyau Debian 3.16.0-4 version 3.16.7-ckt7-1 du 01 mars 2015 alors que
> la Debian Stable propose le 3.16.7-ckt20-1+deb8u4 du 29 février 2016
> incorporant jusqu'au CVE-2016-2550. ..... Si on utilise aptitude ou
> apt pour les mises à jour, ou activer les niveaux 4 et 5 de mintupdate
> désactivés par défaut, on pourra installer le dernier noyau ainsi que
> de nombreux autres paquets non pris en charge par leur programme
> mintupdate. Mais alors quid de la gestion de toutes les dépendances ?
> S'ils ne les incorporent pas c'est qu'ils ont des raisons. Et puis
> cela n'est pas conseillé à des débutants, cœur des utilisateurs de
> Mint paraît-il. ....
> </p>

C'est la ou je veux en venir, c'est dangereux, cette manie de cacher des
choses aux utilisateurs pour ne pas les effrayer ou les induire en
erreurs... Mais la par dessus tout, on préfère cacher des mises a jour,
ou plutôt les placer dans des catégories, non pas par dangerosité mais
par délicatesse d’appliquer la dite mise a jour.  Encore une fois je
reprend ce que mes compères disent, notamment Fred:  

> une politique de mise à jour par niveau. ... Il est très généreux de
> vouloir éviter que les utilisateurs se retrouvent avec une
> distribution inutilisable après une mise à jour un peu lourde, mais
> c’est aussi des plus **casse-gueule**. Il suffit qu’un composant de
> bas niveau du système, comme le noyau ou encore la glibc soit
> fragilisée par une faille de sécurité quelconque et que l’utilisateur
> ait choisi une politique trop conservatrice en terme de mise à jour…
> Ça peut faire très mal. Il y a un principe de base en terme de
> maintenance linuxienne : éviter autant que possible les mises à jour
> partielles. Cela peut être source à terme de problèmes de sécurité ou
> de stabilité.
> </p>

Il prend un exemple tout bête mais qui reflète exactement le problème,
il compare la mint a un vélo, je vous laisse lire l'extrait:  

> La politique de la Linux Mint en matière de mise à jour peut-être
> dangereuse. Pour prendre une image parlante, tu récupères un vélo : la
> selle est morte, le pneu avant dégonflé et les patins de freins à
> changer. Si tu appliques la politique par défaut des mises à jour de
> la Linux Mint, tu changerais la selle et gonflerais le pneu. Mais tu
> laisserais les patins de freins en l’état… Je voudrais pas dire, mais
> je n’aurais pas envie d’utiliser un tel engin.
> </p>

Oui de cette manière, on voit tous là oû il veut en venir, et oui, il a
entièrement raison. Utiliser Mint ne devrait pas être conseiller, ce
n'est pas un conseil, c'est une tentative de viroler votre pc.
Sérieusement, comment peut on conseiller cette distribution qui prouve
bien son amateurisme sur la sécurité? Comment peut t'on le faire avec
une telle possibilité de choix? Car faut avouer, si ce n'est que pour
éviter d’être client chez Canonical et pour ne plus dépendre de cette
boite, il y a pas mal d'autre choix... Surtout que LMDE est juste une
Debian avec une meilleur finition graphique mais qui reste une faille
béante sous le capot. Je suis sur que ma Debian est plus a jour que
cette merde immonde qu'on veut nous faire croire meilleur. Oh mais bien
sur, Mint n'est guère mieux, mais ça fera un autre débat, dans un autre
billet, la pour le moment je vide mes cartouches sur ce truc qui
n'aurait jamais du naître. Alors le choix le plus logique quand on est
utilisateur de ce dédale de failles, c'est de passer par la mère Debian.
Je dois bien avouer que je ne comprend pas l’intérêt de LMDE, surtout
pour ceux qui ont connu la première saveur basé sur une Debian testing,
mais vu que l'équipe en plus de ne pas être sérieuse, a les yeux plus
gros que le ventre, ils ont fait une indigestion et ont simplement
abandonner la première LMDE. A priori, ils comprennent le besoin de
passer a une base Debian tôt ou tard pour être indépendant des choix de
Canonical, du moins je suppose car sinon je ne comprend pas leur
obstination avec LMDE2, par contre ils abandonnent testing pour stable,
mais continuent leur entêtement de faire des mises a jour par catégorie.
Premièrement, je pense que continuer a se baser sur testing aurait été
un choix judicieux, a l'image de Manjaro qui prouve que ce que voulait
faire LMDE était faisable, Manjaro le faisant pour Archlinux, c'est a
dire temporiser les mises a jour pour laisser le temps de faire des
scripts facilitant et automatisant les changements a effectuer après les
mises a jour et surtout le temps de les tester. Deuxièmement, passer a
stable, enlève selon moi de l’intérêt pour cette version de Mint, que
propose t'elle de plus? Un bureau cinnamon ou mate, au choix, Debian les
proposant a son tour, peut être dans une version moindre mais puisque la
1ere LMDE ne proposait même pas les dernières versions de ces deux
bureaux, qui était pourtant et pour moi le seul intérêt et qui m'avait
poussé a l’époque de la tester en principale, je ne suis pas sur que ça
est changé depuis. Donc la fraîcheur des bureaux n'est pas une raison de
l'utiliser. Il reste quoi a cette distribution, pas grand chose, c'est
une Debian mais sans la qualité du sérieux de celle ci, les bureaux mate
et cinnamon ne sont plus exclusif, et vu la qualité de finition du
bureau Gnome sous Debian, je ne vois pas de "bon point" pour LMDE.
Troisièmement, cette distribution reste la cinquième roues du carrosse
Mint, donc on ne doit pas s'attendre a grand chose, a l'époque Clément
m'avait répondu que la priorité c'est la Mint a base d'Ubuntu. Je ne
pense pas qu'il ait changé d'avis donc je ne change pas d'avis. Donc je
résume, LMDE n'est plus basé sur Debian testing mais sur stable, n'a
plus l'exclusivité des bureaux phares que sont cinnamon et mate, n'est
pas aussi sérieuse que son "original", elle est considéré comme
cinquièmes roues, a un système de mise a jour qui choisit "stabilité" a
"sécurité", bref rien de top face a une Debian. Ah, je dois bien dire
qu'il y a eu un effort consentit pour ne pas prendre pour des cons les
utilisateurs, maintenant c'est a eux de décider ce qu'il veuillent pour
les mises a jour, soit la stabilité, soit mettre a jour sans risque,
soit mettre a jour normale. C’était déjà le cas dans la première mais
moins accessible me semble t'il...  
![](http://download.tuxfamily.org/passionlinux/images/png/lmde1.png){.shrinkToFit
.transparent .aligncenter width="1141" height="642"} Est ce suffisant
pour faire d'elle une distribution sérieuse, clairement non. Doit t'on
la conseiller? Non plus et surtout pas a des débutants qui tomberont
dans le piège des mises a jour et comprendront pas comment leur pc
peuvent être affecter. J’espère que j'ai été claire sur cette
distribution, mais la Mint a base d'Ubuntu n'est guère mieux, et
pourtant celle-ci a toute l'attention de l’équipe... Ce qui me fait
encore plus peur pour la LMDE. Vous voulez avoir une Debian simple et
belle, alors prenez Handylinux.
