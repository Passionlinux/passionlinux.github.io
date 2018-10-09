---
title: Distributions pour novices, Debian un bon choix ? Quelle distribution pour les novices ?
date: 2016-04-18 19:52
layout: post
---

<div class="main">

<div class="chapo surlignable">

On se pose souvent la même question, mais quelle est donc la meilleure
distribution pour les débutants, les fameux madame et monsieur Michu,
une distribution qui se veut simple, facile d’accès, une installation
claire, simpliste et rapide, accessible, avec installation et
désinstallation des logiciels compréhensible, qui dure dans le temps...
Je m’en suis fait une idée. J’ai essayé un grand nombre de distribution,
en l’occurrence Mandriva, Ubuntu, Archlinux, Frugalware, openSUSE,
Debian, Mageia, et quelques autres qui étaient a la mode pendant un
temps.  
<!--more-->

</div>

<div class="texte surlignable">

### Différents layouts d’utilisateurs : {#outil_sommaire_0 .spip}

Dans mon cas, ça dépend fortement de comment va être la personne pour
qui la distribution va être installé, on peut noter trois layouts de
personnes :

-   les personnes qui vont installer par eux même la distribution, qui
    vont être autonome, qui vont chercher les réponses dans les forums
    et sur irc,
-   les personnes qui vont installer la distribution par une personne
    tiers, un ami ou dans une install party, et qui par la suite vont
    tenter d’apprendre et d’être autonome,
-   les personnes qui vont dépendre d’une personne tiers pour
    l’installation et la maintenance sans rien vouloir comprendre, ceux
    qui « utilisent leurs ordinateurs comme leurs voitures, une panne et
    au garage. », qui n’iront jamais installer un programme et vont se
    contenter de ce qui est installé.

### Les indépendants : {#outil_sommaire_1 .spip}

Dans les deux premiers cas, je serais plutôt tenter de dire qu’une
distributions comme Mageia serait idéale, j’ai eu la même approche a mes
débuts avec Mandriva et je ne regrette rien, c’est une distribution
solide, stable, a jour mais en privilégiant les versions avec support a
long terme (firefox esr, kernel lts,…). Elle a notamment un centre de
contrôle (du nom de ccm ou mcc) qui permet de faire toutes les choses
réserver a l’administrateur et qui se fait normalement en ligne de
commande comme l’installation ou suppression de paquets, mise a jour,
activation ou désactivation de services, mise en place de
serveur(serveur web, mail,…), un pare feu et même une partie sécurité
qui permet de gérer au mieux la sécurité de son système avec un nombre
de vérification automatique. Ce qui caractérise cette distribution est
le sérieux de l’équipe derrière, la plupart de l’équipe sont des anciens
de Mandriva, son ccm, ses outils non graphique hérité eux aussi de
Mandriva (commençant par drakX) et un installateur simple,
compréhensible avec peu de terme « pro linux ». On peut aussi penser a
(?)Ubuntu et openSUSE. Pour les plus courageux on peut penser a Debian
mais j’y reviendrais plus tard !  

### Les véritables « Michu » : {#outil_sommaire_2 .spip}

Dans le dernier layout de cas, qui me semble être la majorité, je ne
serais pas du même avis, je penserais avant tout a celui qui va devoir
jouer le rôle de la personne tiers, le mainteneur ou plus communément
appelé réparateur. Un article de [Cyrille
Borne](https://www.cyrille-borne.com/article2354/le-reparateur-d-ordinateurs){.spip_out}
va aussi dans ce sens, je le cite :  

> "… A force d’être confronté aux mêmes problèmes en permanence, je
> crois que ce n’est peut être pas la bonne question, la bonne question
> c’est quelle est la meilleure distribution pour faciliter la vie du
> réparateur, à qui on ne réfléchit pas assez.  
> J’ai fait migrer des centaines de postes sous Linux, des dizaines de
> personnes, en plus de 10 ans, un seul s’est sérieusement mis à la
> compréhension du système pour réussir à se débrouiller, un seul
> débutant qui essaie de s’élever, les autres le sont restés. Pourquoi
> s’intéresser au réparateur ? Tout simplement parce que dans notre
> relation non tarifée que nous entretenons avec nos proches, nos
> familles, ces gens que nous avons dans notre parc informatique
> personnel, et bien justement on est dans une relation non tarifée.
> Alors que le commerçant peut se réjouir du plantage et avoir la
> satisfaction qu’on lui apporte la machine dans un état le plus minable
> possible pour dire « ça va coûter cher », « ça va coûter tellement
> cher en réparation que je peux vous proposer une nouvelle machine »,
> « y a rien à faire faut tout changer », vous choisirez la phrase de
> l’escroc, nous sommes dans un cadre totalement opposé, il vaut mieux
> pour nous que la machine fonctionne parfaitement quoi qu’il arrive car
> on sait qu’on va y passer du temps, beaucoup de temps, bénévolement.  
> Et même parfois, à vouloir trop faire de distributions en pensant pour
> le débutant, on en vient presque à rater l’essentiel, la grande
> majorité des débutants restera débutant et dans son attitude de
> débutant, elle fera appel à vous quoi qu’il arrive. Pire parfois, la
> distribution trop pensée pour le débutant peut poser des problèmes à
> l’expert,..."
> </p>

En effet, c’est ce fameux réparateur qui va installer et maintenir ce
système, alors vaut mieux pour lui que cette distribution soit la plus
pérenne possible et qu’il la connaisse bien, voir l’utilise au
quotidien. Comme dit Cyrille, le but est de ne pas mettre un truc
bancale, qui va causer plus de soucis de maintenance, mais un truc
fiable, qui tiendra la route sur le long terme, après tout on est
bénévolement mainteneur, ce qui compte avant tout c’est la connaissance
que l’on en a, car quand ça plante c’est le mainteneur qu’on appel. De
plus il faut une distribution qui ne change pas a tout va, qui bouge le
moins possible, car de ce que je vois dans mon entourage, les mises a
jour on s’en fiche. J’ai tenté des ubuntu LTS, opensuse, arch mais entre
celles qui demandent trop de soins et celle qui tiennent pas leurs
promesses sur le long terme, qui cassent(perte de clavier, de souris,
d’écran...) a la moindre grosses mises a jour comme des passages de
ubuntu 12.04.x a 12.04.z, je me suis fait un saint Graal. Ce Graal doit
avoir plusieurs choses :

-   être une distribution que je maîtrise bien,
-   avoir une grosse communauté, française de préférence,
-   avoir un support assez long (au moins deux ans),
-   être de layout rpm ou deb,
-   faire partie du top 10 de distrowatch (je sais ce classement ne veut
    rien dire mais quand même…),
-   ne pas être une « petite fille » de,
-   ne pas être une rolling release,
-   ne pas dépendre d’une entité commercial.

Pendant un temps, Ubuntu fut l’élue, mais certains points ne
correspondaient pas au cahier des charges et surtout des remontés de
problèmes des utilisateurs comme la perte de clavier/souris et surtout
des écrans a la suite des mises a jour et après vérifications de ma part
m’ont poussé a choisir autre chose.

<div style="text-align: center;">

![Logo
debian](http://download.tuxfamily.org/passionlinux/IMG/png/10png-a2d700a2d7.png "Logo debian")

</div>

Ce fut avec ma distribution de tous les jours, Debian, que j’ai pu avoir
la sérénité. Debian c’est avant tout la plus grosse et la plus populaire
distribution communautaire, l’une des plus vieille (slackware la devance
de très peu), sans aucune dépendance envers une société commerciale, une
grosse communauté derrière notamment française, un support de deux/trois
ans voir plus avec le projet LTS, des paquets deb, c’est la « mere » de
toute les distributions deb (dont ubuntu, knoppix, mint,... ), elle sort
en version dite stable tous les deux ans approximativement, elle est
déployée en plusieurs versions( trois : sid, testing et stable) adapté a
chaque utilisation/utilisateur…  Son installation n’est pas
indéchiffrable, malgré les termes explicite linuxien, c’est simple,
automatisé au maximum par défaut, seule la partie partition incombe a
l’utilisateur. Plusieurs environnements sont installable (gnome, kde,
xfce, cinnamon, mate, lxde…) et des services aussi (http, mail, ssh,
ftp…). Une installation qui dure grossièrement 45min. Pour le bureau,
j’ai remarqué, depuis le temps que je fais ça, que les personnes sont
capable de s’habituer a un tout autre environnement que leur
traditionnel windows. Au début, je ne mettais que du kde, pour sa
ressemblance avec windows (leur ancien environnement)et donc éviter de
les troubler, celui ci étant personnalisable a souhait, j’ai souvent eu
des déboires (donc des appels) comme des panels qui ont été supprimé par
inadvertance. Maintenant, je met selon le layout d’ordinateur, gnome-shell
pour les pc récents et xfce pour les pc plus vieux. Gnome surprend
encore au début car c’est vraiment un tout autre comportement que
l’habituelle principe du bureau comme on peu connaître sous windows ou
kde/cinnamon/xfce…, mais sa modernité plaît.

![Gnome sous
Debian](http://download.tuxfamily.org/passionlinux/IMG/distant/png/800px-Debianccae.png)

Par la suite, il ne reste plus qu’a fignoler, amélioration du look des
applications gtk dans kde ou vice-versa, ajout d’application selon les
besoins, installation des imprimantes (normalement automatiquement
effectué si pilote installé).  
Pour les applications, je met un maximum pour être capable de répondre a
tous les besoins, en plus de demander a la personne ses désirs. On a
beau penser a tout ou du moins essayer, on ne sera jamais a l’abri d’un
oubli ou d’un besoin soudain de la personne. Pour le matériel, je
conseille aussi, généralement imprimante tout-en-un hp par exemple. Ceci
pour éviter de me retrouver en face d’un soucis de compatibilité.  
Pour les mises a jour, ça dépend des personnes et des liens, soit je
laisse l’utilisateur le faire en expliquant comment faire(c’est
graphique et rapide) soit pour les plus proches, je m’occupe de tout via
ssh. Une fois fait, généralement ça prend facilement deux a trois
heures, la personne découvre son nouveau système, couramment me signal
un gain de performance. Et c’est fini, j’entends sonner mon téléphone
pour autre chose que des ordinateurs !!! Donc on a vu que Debian était
tout destiné pour les grands débutants, les fameux Michu, ce genre
d’utilisateurs qui veulent juste utiliser leurs pc comme on peut vouloir
utiliser sa voiture, utiliser et non faire de la maintenance,
utilisateur qui doit bien représenter neuf personnes sur dix.
Utilisateurs qui représente chez moi mes parents, oncles et bien
d’autres…

[Dans un prochain
article](http://passiongnulinux.tuxfamily.org/?p=56){.spip_in}, on verra
si debian est idéale pour commencer sous linux quand on est un
utilisateur autonome.

</div>

</div>

 
