---
title: Sabayon linux et Calculate linux, deux Gentoo pour humain #1
date: 2017-01-08 15:46
layout: post
---

J'ai voulu voir ce que donnait, depuis le temps, la Sabayon, une
distribution linux basé sur Gentoo mais bien plus facile d'utilisation.
J'avais déjà testé la distribution dans ses premières années, ses atouts
étant qu'elle installe par défaut tout ce qui peut faciliter la vie
comme les codecs, ce qui fait d'elle une distribution peu ou pas libre.
J'ai aussi eu le temps et l'envie de tester une distribution que je
n'avais jamais trop eu dans les mains, une aussi a base de Gentoo et qui
la rend utilisable simplement et facilement: la Calculate.  
<!--more-->  
Bon je vais commencer par Sabayon, il n'y a vraiment pas que du bon a
dire dessus, je sais pas trop pourquoi j'en parle du reste, elle n'est
pas mauvaise, juste pas bonne, un peu comme Mageia voir carrément pire.
Allez je commence, tout d'abord ça commence très mal pour télécharger
une ISO, pas de soucis si on prend le lien direct (HTTP) mais ça se
complique si on veut passer par du torrent, c'est simple une belle
erreur 550 nous arrive en pleine face!!! C'est pas grave, je me laisse
pas abattre et je lance les téléchargements de l'ISO KDE et XFCE via
Kget. Une fois téléchargé, je les ai chacune "graver" sur une clef USB
au lieu d'un CD pour un lancement en dur du live voir une installation
par la suite et fait aussi une installation dans virtualbox pour tester.
J'ai vite abandonné l'idée de faire fonctionner l'ISO KDE, elle se
lance, je choisi ma langue et lance la session live, ce qui me donne un
joli bootsplash, je suppose que c'est plymouth qui fait ce rôle et puis
plus rien, non juste un beau écran noir qui reste désespérément noir...
J'ai quand même la possibilité de passer aux autres TTY donc le live
n'est pas planté,  juste il ne lance pas KDE ni sur ma clef USB ni sous
virtualbox... Je crois que [Frederic Bezies est dans le même
cas.](http://frederic.bezies.free.fr/blog/) J'ai trouvé la cause que
bien plus tard, c'est encore l'histoire de mes deux écrans qui me font
un sale coup, j'ai le même cas avec calculate version kde, alors que
sabayon et calculate dans leurs saveurs xfce se lancent parfaitement. Je
me suis donc ensuite attelé a la version Xfce, dans les deux cas, c'est
a dire dans virtualbox et sur ma clef USB, je n'ai pas eu de soucis
contrairement a la version KDE. C'est la ou je suis un peu triste de
voir cette version, pour être honnête je ne comprend pas qu'en 2016 on
donne encore a Xfce le look de gnome2 alors que pour les nostalgiques de
ce bureau, il y a Mate... Si c'est pour que Xfce ressemble a Mate,
arrêtez de distribuer les deux bureaux a la fin! Xfce par défaut a 2
panels, un en haut c'est le classique, celui qui contient le lanceur
d'application ou menu application, le gestionnaire de fenêtres réduites,
la boite a miniatures et enfin l'heure, l'autre panel est en bas, c'est
simplement une barre avec des raccourcies vers les applications les plus
utiles (navigateur, mail, terminal,ect...). Par exemple ma Debian et une
Debian xfce out of the box:
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2015-08-15_23-08-02-1024x576.png){.aligncenter
.wp-image-939 .size-large width="700" height="394"}
![](http://download.tuxfamily.org/passionlinux//2017/01/debian-look-1024x576.png){.aligncenter
.wp-image-940 .size-large width="700" height="394"} Avec Sabayon, on a
le droit a deux panels de même taille, qui donne un look a la gnome
2....
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-02_20-40-25sabayon-1024x576.png){.aligncenter
.wp-image-941 .size-large width="700" height="394"} Bref, je vais pas
m'éterniser dessus, c'est une question de gout, je trouve de toute façon
que mettre le look de gnome2 a Xfce alors qu'il y a Mate qui reprend le
flambeau est ridicule! Bon ça c'est dit passons a autre chose. Je n'ai
pas aimé grand chose de cette distribution, dans les choses que j'ai
trouvé sympa, je cite l'installation de toutes les choses sales et non
libre qui permettent de faciliter la vie, comme les codecs multimédia,
flash... J'ai aussi aimé d'avoir [Gufw installé par
défaut](http://gufw.org):
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_19-10-58-1024x768.png){.aligncenter
.wp-image-957 .size-large width="700" height="525"} J'ai aimé le boot de
la distribution graphique par plymouth (je suppose). Comme je l'ai dis
plus haut, tout n'est pas rose, la distribution prend pas mal de
ressources surtout pour du Xfce, le look a l'ancienne de Xfce (gnome2),
des choix d'applications tordus notamment je citerais google chrome
comme navigateur ou bien gnome-video comme lecteur multimédia... Le pire
est sûrement la grosse lenteur du gestionnaire de paquets, je n'ai
jamais vu aussi lent et Urpmi de Mandriva/Mageia a un sacré concurrent
en terme de lenteur, je pense même qu'il est battu... Les installations
de paquets sont lentes, que ça soit en graphique ou en console, les
mises a jour sont encore plus lents, on nous demande même de patienter
pendant la mise a jour et d'aller prendre un café... Comme quoi on peut
être développeur et humoriste...  
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-05_20-30-12-1024x576.png){.aligncenter
.wp-image-951 .size-large width="700" height="394"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-05_20-24-03-1024x576.png){.aligncenter
.wp-image-964 .size-large width="700" height="394"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_19-58-48-1024x768.png){.aligncenter
.wp-image-963 .size-large width="700" height="525"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_19-46-37-1024x768.png){.aligncenter
.wp-image-962 .size-large width="700" height="525"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_19-36-14-1024x768.png){.aligncenter
.wp-image-961 .size-large width="700" height="525"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_19-27-52-1024x768.png){.aligncenter
.wp-image-960 .size-large width="700" height="525"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_19-13-02-1024x768.png){.aligncenter
.wp-image-959 .size-large width="700" height="525"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_19-12-22-1024x768.png){.aligncenter
.wp-image-958 .size-large width="700" height="525"} C'est lent que ça
soit en console ou avec l'interface graphique, rien que la mise a jour
des dépôts est lente, pas loin de 5 bonnes minutes a chaque fois pour
juste rafraîchir les dépôts... Puis ensuite le calcule des dépendances a
prit au bas mot 20 minutes, j'ai eu quand même a faire 289 mises a jour
qui s’arrêtent en plein au milieu après pas loin de 2 heures, faute de
place sur le disque dur (15 GO). j'ai eu le courage de retenter avec une
plus grosse partitions racine(30 GO) juste pour voir le temps totale
d'une mise a jour, j'ai l'habitude de tester en virtualbox et sur clef
USB les différentes distributions, je dois dire que je n'ai jamais vu ça
de ma vie, les 289 mises a jour ont débuté a 20h32 et n’étaient toujours
pas fini a 5h44 sur l'installation USB.
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-05_21-56-54-1024x576.png){.aligncenter
.wp-image-952 .size-large width="700" height="394"}
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-06_05-43-27-1024x576.png){.aligncenter
.wp-image-953 .size-large width="700" height="394"} Je sais bien que
l'on ne peut pas mesurer la vitesse d'un OS surtout sur une clef USB, et
vu le temps record de la mise a jour, j'ai installé Sabayon sur le
portable, un PC de 2009 avec double cœurs et 4 go de RAM avec disque dur
de 700 GO, c'est pour cela que je me permet de dire que le gestionnaire
de paquets est le plus lent que j'ai vu mais je continue sans parler des
tests en virtualbox et celui sur USB pour passer directement sur celui
en vrai, en dur comme disent les pros. La seule chose de vraiment
potable sur cette distribution, est le choix d'Anaconda, l'installateur
de Fedora, pour sa propre installation. Il est simplissime, élégant,
facilement compréhensible, et rapide sur Fedora mais avec Sabayon
l'installation a duré 1h contre 2h23 sur une clef USB, c'est a dire une
éternité, heureusement qu'il passait un bon film a la TV: les dents de
la mer!!! J'ai réussi a le faire planter deux fois simplement en
supprimant une partition et puis quelle lourdeur, c'est ralentit comme
pas possible et on ne sait pas vraiment ce qu'il fait. Puis j'ai eu la
bonne idée de faire les mises a jour en console via equo et non en
graphique vu la lenteur de l'interface, toujours 289 a faire mais je me
suis dit que cette fois c'est directement en dur ça devrait aller plus
vite et bien non, les mises a jour ont mis plus de 2h pour être fait, en
faite je ne sais pas exactement, car au bout de deux heures je suis
partis de chez moi et j'ai laissé la machine tourner. En rentrant
c'était fini et je me suis attelé a installer 6 paquets dont 0ad,
minetest, thunderbird, amule, minidlna vivaldi et scummvm pour voir un
peu comment était "equo", en faite je m'attendait a peut être cinq
minutes mais non, la mise a jour des dépôts a mis pratiquement 5-10
minutes, la recherche des dépendances a mis 10 minutes pratiquement et
enfin l'installation en a mis trois fois plus de temps, il y a eu deux
ou trois paquets a compiler.... Donc presque une heure complète pour
installer si peu! Je dois dire que j'ai vite arrêter là, j'en avais
plein le cul de cette lenteur, pour moi c'est rédhibitoire d'avoir un
gestionnaire de paquets lent. La moitié du système est en anglais car
les paquets de langues ne sont pas installés comme pour Libreoffice:
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_19-31-29-1024x768.png){.aligncenter
.wp-image-965 .size-large width="700" height="525"} Je pense que Sabayon
va retourner dans son carton et que je ne la lancerais plus jamais, je
n'en vois pas l’intérêt, c'est lent a utiliser, c'est lent a mettre a
jour, c'est lourd et même avec un bureau léger et simpliste, ils ont
réussi a l'alourdir, le gars a la tète du projet a des jours avec et
d'autres sans, ceci arrive a tous mais on ne sait jamais si le gars va
lâché ou pas. Je me suis attardé plus que je ne voulais sur cette
distribution, en tout cas ce n'est pas cette Sabayon qui va me donner
envie d'aller sur Gentoo! Ce billet devait être en une fois et parler de
Sabayon et de Calculate, en fin de compte je le divise en deux pour plus
de clarté.
