---
title: La connerie de Debian Sid
date: 2017-02-15 12:08
layout: post
---

Aujourd'hui je vais parler du gros point faible selon moi de Debian: sa
version SID... Cette version de Debian qui est censé être instable et
qui ne mérite pas du tout sa réputation. Pour moi le gros soucis est la
période de gèle, je comprend qu'on gèle testing mais Sid devrait garder
sa fraîcheur, Sid devrait être une version totalement a  part, autonome
et qui soit a coté de la version stable la seconde version officiel. Si
on regarde les distributions a succès, on remarque quelque chose qui
frappe, ce sont les distributions a publications continues comme Arch ,
Manjaro, Tumbleweed et autres qui prennent de plus en plus de parts de
marché. Il y a un désintérêt de plus en plus flagrant envers les
distributions a sorties fixes surtout celles qui ont des sorties
rapprochées, seule les distributions dites LTS arrivent a sortir leurs
épingles du jeu.  
<!--more-->  
Debian avec sa version Stable est déjà dans la course des distributions
LTS, sa stabilité, la tranquillité de gestion d'une Stable, les rapides
corrections de failles, bref, tout est fait pour que Debian Stable soit
une distribution populaire parmi ceux qui veulent du LTS. Maintenant
pour ceux qui veulent du Debian en publication continue, il y a Testing
qui est souvent préconisé et Sid sur laquelle je ne vais pas cacher ma
préférence pour de nombreuses raisons que je citerais une par une dans
ce qui va suivre. Tout d'abord, testing n'est pas considéré comme une
distribution autonome, pour une simple raison: elle peut a tout moment
être incomplète avec la danse des paquets venant de Sid qui quant a
elle, est toujours complète. Une autre raison,  très simple celle-ci,
est que les corrections de failles ou de bugs arrivent d'abord dans Sid
par de nouveaux paquets qui corrigent et dans stable par des patchs,
testing quant a elle doit attendre plusieurs jours ou semaines pour voir
arriver de Sid les fameuses corrections, ce qui peut être bloquant avec
des gros bugs ou meme pour la sécurité . Enfin testing n'est pas si
vieille, elle est arrivé bien après pour augmenté la qualité de
l'ensemble, c'est une étape intermédiaire entre Sid qui voit arriver des
nouveaux paquets constamment et Stable. Le soucis c'est que Sid a le
doux nom de Unstable, ce qui est pour le moins explicite: instable =
développement. Ce qui est déjà une première erreur de communication, la
Sid ne comporte aucuns logiciels en version bêta ou autre, seul des
logiciels stable y sont acceptés. Unstable n'est là que pour signaler
que cette version de Debian n'est pas de même qualité que la Stable,
c'est la version où vont les nouveaux paquets venant des développeurs
Debian, il peut y avoir des bugs résultant de l'ajout du logiciel, de
bugs de ce logiciels qui n'est pas suffisamment testé ou même des soucis
dans l'empaquetage Debian. Au bout de plusieurs jours, le logiciel va
migrer dans testing a condition qu'il n'y a pas de bugs pire que ceux de
la version actuellement dans testing. Comme un programme a des
dépendances, il se peut que le paquet ne puisse pas être installé car
ses dépendances ne sont pas encore arrivé dans testing et sont bloqué
dans Sid. C'est la où on arrive a ce qui est pour moi une erreur, un
moment donné, tous les deux ans, Sid est gelé pour que les développeurs
se concentrent sur la correction de bugs, les paquets sont donc a peu
près identique entre Sid et testing, puis après une période plus ou
moins longue, testing ou plutôt la nouvelle Stable sort et on dégel Sid,
a ce moment là, notre Sid est un peu instable car des milliers de
paquets sont mis a jour très rapidement. Alors c'est là que se situe le
soucis, Debian Sid ne devrait pas être gelé, elle devrait garder sa
fraîcheur, testing étant gelé et surtout une version de la futur stable
portant son nom est déjà disponible avec ses dépôts utilisable. Alors je
sais qu'il y a des "y a qu'a faire" mais oui, c'est simple, on ne touche
pas a Sid qui reste une rolling, on gel testing avec laquelle on fait en
plus une version "future stable", ce qui ferait que testing prend la
place actuelle de Sid pendant les périodes de gel, "future stable" celle
de testing et tout le monde y gagne. En effet, on garde le coté pure
rolling de Sid et surtout on évite ce moment délicat, un peu archlinux,
de la période post-gel.... Il me semblait que c'était en cour de
discussion pour justement faire ce qui a été dit, mais je ne trouve pas
plus d'information dans les différentes listes de discussions que sur le
site du projet. Dommage, j’espère vraiment que ça sera fait dans les
prochaines versions.
