---
title: Les forks qui font doublons pour faire plaisir à l'ego des développeurs de distributions #2 Le cas Devuan
date: 2016-07-23 15:52
layout: post
---

Après le [billet sur
openMandriva/Mageia](http://passiongnulinux.tuxfamily.org/?p=415), me
voila parti cracher sur le fork de Debian, la fameuse et inutile Devuan,
vous savez, le feu d'artifices qui n'a été qu'un pétard mouillé... Elle
est né le 27 novembre 2014 alors qu'un groupe d'administrateurs de
Debian
[annoncent](https://lists.dyne.org/lurker/message/20141127.212941.f55acc3a.en.html)
qu'ils ont forké Debian et lui ont donné pour nom Devuan, pour une
raison, ils ne voulaient pas de systemd... Même si je simplifie a fond
en schématisant, c'est déjà tout un programme, on voit déjà le peu
d’intérêt a donner pour cette nouvelle énième distribution.  
<!--more-->  
Fred, encore lui et non j ne lis pas que son blog mais..., en parle a
plusieurs reprises, dont [1 journée après sa
création](http://frederic.bezies.free.fr/blog/?p=12139). Il en parle
avec sa façon un peu méprisante mais si juste, pensant même que ce fork
ne durerait pas:  

> Pour tout dire, je reste très circonspect sur l’avenir de ce fork, ne
> serait-ce que par son ambition presque démesurée. Forker un
> environnement de bureau, comme l’a fait [Mate
> Desktop](http://www.mate-desktop.org/), c’est réaliste. Mais une
> distribution aussi complète que Debian GNU/Linux ? C’est déjà plus dur
> à concevoir. Je sais qu’il y a le précédent de
> [Mageia](http://www.mageia.org/), mais la distribution répondait à un
> besoin de faire survivre Mandriva Linux, et non sur le rejet d’une
> technologie. Pour le moment, ce fork ne fait qu’alimenter l’image
> d’une cour de petite section d’école maternelle où des enfants se
> bagarre pour une paquet de bonbons que donne la communauté du libre en
> ce moment.
> </p>

Je pensais pas non plus que celle ci durerait, encore moins qu'elle
auraient su convaincre quelques érudits. D’après [leurs dires (je vous
laisse chercher sur leur site)](https://devuan.org/), les érudits en
question, seraient en nombre, plus de 800 personnes auraient déjà
signalé leurs soutiens. Leur première version est une pré-alpha en mai
2015, Fred (toujours lui) [en a testé la
teneur](http://frederic.bezies.free.fr/blog/?p=12836), et finit par
conclure:  

> La phrase qui me vient à l’esprit est simple : « tout ça pour ça ? »
> Car oui, mis à part le système d’initialisation .... rien ne
> différencie l’original de sa dérivée. ... Sinon, **rien ne
> différencie** une Devuan d’une Debian du moins sur ce que peut voir
> l’utilisateur final.
> </p>

Alors qu'en est t'il en 2016? On reprend les mêmes et on refait pareil,
rien de neuf en 2016, ah si, en avril 2016, la béta de [la Devuan 1.0
est sortie... :](https://devuan.org/)  

> Devuan GNU+Linux is a fork of Debian without systemd. Its Beta release
> marks an important milestone towards the sustainability and the
> continuation of Devuan as a universal base distribution.
> </p>

Qu'on traduit par:  

> <span id="result_box" lang="fr" tabindex="-1"><span>Debian</span> GNU
> + Linux est un fork de Debian sans systemd. Sa version bêta
> <span>marque une étape importante</span> vers la durabilité et la
> poursuite de devuan comme une distribution de base
> <span>universelle.</span></span>
> </p>

Attendre 2 ans pour pondre une copie de Debian sans systemd montre que
le ridicule ne tue pas. Je sais ce qu'on va me dire, systemd ça pu,
c'est compliqué a maintenir, ect... De là a faire un fork de Debian pour
cette unique raison c'est encore un beau gâchis, comme ou pire que celui
de
[OpenMandriva/Mageia](http://passiongnulinux.tuxfamily.org/2016/07/20/les-forks-qui-font-doublons-pour-faire-plaisir-a-lego-des-developpeurs-de-distributions-ou-heritage-quand-tu-nous-tiens/).
Surtout que Debian est assez souple, il suffisait de maintenir une
compatibilité avec un autre système d'Init et de maintenir un dépôt,
voir même une ISO contenant les paquets lié a cette Init. A aucun moment
le projet Debian a imposé le choix de systemd mais puisque personne se
proposait pour maintenir une compatibilité avec un autre système, il a
été décidé de faire ainsi. C'est pas possible de faire un dépôt semi
officiel? Ah bon, pourtant le [dépôt
DEB-multimedia](https://deb-multimedia.org/) en est un qui ne pose aucun
soucis. Donc Devuan est bien un projet qui ne sert qu'a masturber l'ego
des développeurs, un de plus dans la famille Debian/Ubuntu, car sa fille
est aussi attaqué de toute part par des forks inutile Ceci sera l'objet
d'un future billet.
