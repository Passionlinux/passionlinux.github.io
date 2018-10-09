---
title: L'attente de la Debian 9 va être longue
date: 2017-06-13 00:26
layout: post
---

Je me suis mis récemment une Calculate linux en attendant la sortie de
ma Debian et de son XFCE 4.12, quelle belle connerie de ma part. Je vous
explique les raisons de mon agacement. Tout d'abord le rendu de xfce "en
dur" n'est pas le même que celui du live, c'est un comportement
différent par rapport au live par exemple la gestion des fenêtres quand
celles-ci s'approchent des bords, du reste xfce me demande au premier
lancement ce que je veux, à choisir entre bord vide ou double panneaux
classiquement le choix officiel de xfce. Normalement j'aurais du avoir
le look qu'on peut voir dans cette vidéo:
https://www.youtube.com/watch?v=tU7sJ7A7GF8&t=1361s Autre point, la
barre du bas est simplement à moitié vide/complète par des icônes de
programmes mais qui sont, comment dire, non trouvés. Icônes qui sont
donc de simple cases grisés. J'ai simplement viré toutes ces icônes pour
remettre ceux  des applications présentes.  
<!--more-->  
Par la suite j'ai aussi remarqué que les "tips" de thunar présent dans
le live n'étaient pas présent dans ma version installé, j'ai très vite
compris qu'en faite le live n'avait pas copié dans mon /home le dossier
xfce et du coup je suis repassé en live pour copier/coller depuis le
live le dite dossier xfce directement dans mon home, à partir de là ce
fut bon et j'avais le comportement souhaité par cette distribution. Bon
je dois dire que de toute façon le comportement de Xfce dans cette
distribution n'est pas un comportement classique, ici pas de tiling: pas
de fenêtres qui prennent un quart de notre écran si on la place sur un
des bord... Ceci étant dit, ce n'est simplement pas un Xfce des plus
classique, la moitié des programmes ne sont pas des programmes de ce
bureau mais des logiciels venant de partout, par exemple les images se
seront pas ouvert dans [Ristretto](https://doc.ubuntu-fr.org/ristretto)
mais dans [Nomacs](http://nomacs.org/)(???) , choix d'un programme comme
Clémentine au lieu du classique Quodlibet, Smplayer au lieu de Parole,
bref pas mal d'applications qui ont été mis aux rebuts comme la plupart
des plugins de Xfce. Le menu application n'est pas celui habituellement,
c'est bien dans l'ensemble le même sauf qu'il n'a pas les 3 ou 4
raccourcies qui sont juste avant les applications rangés par thèmes. Je
ne parle pas non plus de l'absence du menu Whisker... Dans les délires
propres à la distribution, j'ai réussi à faire planter ma session, à
freezer mon PC avec Thunar et les aperçus de mes films qui se font à
l'aide de Tumbler. En faite pour les vidéos , deux moteurs se battent,
d'un coté le moteur mplayer avec mplyerthumb et de l'autre gstreamer, du
coup sur ma bécane ça me faisaient des "sauts" visible sur mon écran 1
(j'ai deux écrans côte a côte) et qui faisaient planter ma session. Je
précise que sur aucune autre distribution je n'ai eu ce soucis, de ce
fait pour arrêter ce problème, j'ai simplement mis à "true" le "disable
gstreamer" dans /etc/xdg/tumbler/tumbler.rc. Autre merveille de cette
distribution, j'ai réussi à planter ma session xfce avec 0ad, chose
jamais eu sur les autres distributions, là simplement en lançant 0ad, ma
session fut ingérable, plus de souris et les touches claviers ne
fonctionnant plus, le visuelle fut haché, je pouvais néanmoins passer à
un autre TTY ce qui me sauva un peu de la mise hors tension brutale. Je
dois oublier encore quelques délires de cette versions, mais dans
l'ensemble je me demande réellement si les développeurs de cette
distribution utilisent encore le bureau Xfce.  
