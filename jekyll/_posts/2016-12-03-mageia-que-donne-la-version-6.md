---
title: Mageia, que donne la version 6?
date: 2016-12-03 00:09
layout: post
---

Ce billet date d'un test de la Mageia 6 sta1 qui commence a sentir le
vieux (mon test est vieux pas Mageia6...), j'ai fait celui-ci
mi-novembre plus précisément le 22 novembre. Que dire si ce n'est que
c'est une bêta et rien de plus, [ou comment un vieux bug peut encore se
targuer d’être pressent sur une
"stabilisation1"](https://bugs.mageia.org/show_bug.cgi?id=18724). Non je
suis méchant, c'est plutôt une bonne version mais encore une fois on est
loin de l'utilisable, un vilain bug empêchant le démarrage de la session
X, des oublis dans la logithèque comme firefox, kinfocenter ou Ksysguard
qui sont absent alors que la logithèque est rempli d'inconnus comme
Mainslide ou X3270 ou encore des applications doublons comme Aterm,
Xterm alors que Konsole est là, sinon on a droit aux fameux bugs bien
connus de Mageia venant même de l’ère Mandriva..., a corriger au plus
vite.  
<!--more-->  
Pour être sincère jusqu'au bout, ce billet devait être bien plus
positive, je m'étais donné le temps de la réflexion, vu les soucis de la
STA1, sans conséquence a part le fameux bug de X11, je m'étais lancé sur
la récupération de la net-install qui au passage est une STA2, c'est
peut être une erreur qui s'est glissé vu la piètre qualité de
l'installateur... Donc je disais que je voulais partir sur de bonne base
et refaire une installation cette fois avec une net-install fraîchement
téléchargé hier soir et qui d’après le coin gauche de l'installateur est
soit disant une STA2.
![virtualbox\_mageia-6\_02\_12\_2016\_05\_11\_42](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_05_11_42.png){.aligncenter
.wp-image-858 .size-full width="800" height="600"} Noter également et
contrairement a ce qui est dit par l'équipe, c'est bien le bureau KDE
(ici Plasma) qui est mis en valeur et par défaut, sinon pourquoi Plasma
se situe avant Gnome? Pourquoi Plasma est coché par défaut? Oui c'est
bien une STA2 qui est en face de nous, mais là ou je n'ai pas de soucis
avec la STA1 pour installer les paquets après avoir sélectionné le
bureau voulu, la STA2 plante lamentablement et même en attendant une
trentaine de minutes, avec mon Ksysguard (moniteur système de KDE)
ouvert pour voir les interactions de ma connexion internet, je n'ai pas
vu l'ombre d'une activité de mon réseau, donc l'installateur était bel
et bien planté...
![virtualbox\_mageia-6\_02\_12\_2016\_08\_23\_29](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_08_23_29.png){.aligncenter
.wp-image-862 .size-full width="800" height="600"}
![virtualbox\_mageia-6\_02\_12\_2016\_08\_23\_49](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_08_23_49.png){.aligncenter
.wp-image-863 .size-full width="800"
height="600"}![virtualbox\_mageia-6\_02\_12\_2016\_12\_52\_39](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_12_52_39.png){.aligncenter
.wp-image-869 .size-full width="800" height="600"} Sur la première
capture on y voit l'installation des paquets qui se lance puis tout
s’arrête et reste vide comme sur la capture d’après. J'ai tenté de faire
trois fois la même chose mais sans succès et ça s’arrêtait au même
moment, des que ça commençais a charger. Je me demande ce qui se serait
passé si au lieu d'un serveur HTTP j'aurais mis un FTP, peut être que
cela aurait été bon? Noter le look mal fini et vieillot de
l'installateur, on voit le contour du cadre blanc et les messages qui ne
sont pas intégré au reste du look GTK3 (la troisième capture venant de
l'installation de la STA1 DVD qui suit). Pour continuer l'installation,
je me suis dit que c’était sûrement un bug graphique de l'installateur,
certainement un truc venant de GTK, alors je suis passé par une
installation texte. Je m’arrête de suite pour une petite parenthèse,
qu'est ce que c'est moche, autant j'adore l'installation texte ou ncurse
de Debian, celui de SUSE, Frugalware, pour ne citer qu'eux, autant la
c'est même pas du ncurse, c'est véritablement du texte. Au moins il est
superbement bien traduit et léger.
![virtualbox\_mageia-6\_02\_12\_2016\_05\_24\_38](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_05_24_38.png){.aligncenter
.wp-image-859 .size-full width="720" height="400"} Encore Plasma qui est
mis en avant, désolé mais si ce n'est pas le cas, pourquoi ne pas avoir
laissé un ordre alphabétique?
![virtualbox\_mageia-6\_02\_12\_2016\_05\_26\_37](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_05_26_37.png){.aligncenter
.wp-image-860 .size-full width="720" height="400"} L'installation va
jusqu'au bout cette fois et je suis très content de pouvoir redémarrer
après avoir fais une configuration rapide (utilisateur, mot de passe,
ect...). Mais en faite non, je vais pas pouvoir démarrer le système car
un autre bug m'en empêche, ou sinon mon système hôte est vraiment
merdique mais vu que celui ci est capable de faire démarrer une openSUSE
tumbleweed avec plasma, j'ai un doute raisonnable me disant que le
soucis est encore une fois du coté de cette installateur.
![virtualbox\_mageia-6\_02\_12\_2016\_08\_18\_34](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_08_18_34.png){.aligncenter
.wp-image-861 .size-full width="720" height="400"} Une fois cet écran
devant moi, impossible de changer de TTY, impossible de taper des
commandes, rien, j'ai attendu, attendu ... Puis j'ai coupé pour relancer
3 fois sans succès. J'ai pris mon courage et j'ai regarder le torrent de
la version DVD, c’était encore la même STA1 de la dernière fois, celle
au couleur de mageia 5, j'ai lancé une installation, celle-ci ira au
bout sans soucis et démarrera.
![virtualbox\_mageia-6\_02\_12\_2016\_12\_11\_13](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_12_11_13.png){.aligncenter
.wp-image-864 .size-full width="800" height="600"} Toujours Plasma mis
en avant:)
![virtualbox\_mageia-6\_02\_12\_2016\_12\_35\_09](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_12_35_09.png){.aligncenter
.wp-image-865 .size-full width="800" height="600"} Comme ça change de
tout a l'heure, là pas de soucis!!! Du reste noté que je n'ai pas eu de
soucis du bug cité plus haut qu'on a en utilisant la net-install ni
celui du X11... Bon vu que c'est de la STA1, on a le droit au look de
Mageia5. On verra par la suite si en faisant les mises a jour on a le
thème et le look de la version6.
![virtualbox\_mageia-6\_02\_12\_2016\_13\_06\_34](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_13_06_34-1024x768.png){.aligncenter
.wp-image-867 .size-large width="840" height="630"} Enfin GRUB2 est de
la partie, Mageia a été plus frileuse que Debian a ce sujet...
![virtualbox\_mageia-6\_02\_12\_2016\_13\_07\_13](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_13_07_13.png){.aligncenter
.wp-image-868 .size-full width="800" height="600"}
![virtualbox\_mageia-6\_02\_12\_2016\_13\_03\_47](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_13_03_47.png){.aligncenter
.wp-image-866 .size-full width="800" height="600"} On est toujours
accueilli par une fenêtre de bienvenu, c'est agréable et ça rappel ce
que Mandriva faisait mais là c'est en bien mieux!
![virtualbox\_mageia-6\_02\_12\_2016\_13\_23\_37](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_13_23_37-1024x576.png){.aligncenter
.wp-image-874 .size-large width="840" height="473"} Première chose a
faire, virer le support DVD dans le gestionnaire de dépôts, puis ajouter
les dépôts du réseau, je ne sais pas pourquoi Mageia continu a faire sa
têtue malgré les relances de ce "bugs" hérité de sa mère Mandriva, en
2016 je trouve limite que ça soit a l'utilisateur de faire cela. Je ne
suis pas le seul a penser ça, Adrien.d le dit calmement:  

> Chose impérative, CONFIGURER LES SOURCES !!!! Car par défaut (depuis
> toujours?) les médias sur internet ne sont pas installés, il faut donc
> bien penser à le faire. Une aberration pour moi !
> </p>

On peut lire sur [son
blog](http://www.linuxtricks.fr/news/10-logiciels-libres/132-sortie-de-mageia-6-sta1-ou-en-est-mageia-6),
un test effectué en juillet 2016, c'était déjà sur une STA1 a l'époque
c'est dire la vitesse du projet pour évoluer...
![virtualbox\_mageia-6\_02\_12\_2016\_13\_31\_37](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_13_31_37-1024x576.png){.aligncenter
.wp-image-875 .size-large width="840" height="473"} Une fois fait, je
lance la première série de mise a jour, c'est toujours le fonctionnement
de [URPMI](https://fr.wikipedia.org/wiki/Urpmi), il doit déjà mettre a
jour son RPM puis le reste du système. URPMI fait son age, il n'est plus
vraiment de toute première fraîcheur, moi qui le défendais comme un
pestiféré contre l'inclusion de
[DNF](https://fr.wikipedia.org/wiki/Dandified_Yum), qui selon moi est
encore une preuve de la fedorisation et de l'oubli de ses origines
envers Mandriva, comme le faite de dire que Mageia n'est pas tourné vers
KDE, c'est oublier d’où ou plutôt de quoi elle est issues, d'un fork de
redhat avec kde1 qui s'appelait Mandrake... Donc une fois la première
série de mises a jour effectuée, je me tâtonne a jouer avec DNF pour
faire les 1212 mises a jour suivantes, une sorte de baptême de feu!
Avant tout je dois bien admettre que URPMI est bien une chose qui ne me
manque pas, je le trouve indigeste, a part les commandes urpmi pour
installer et urpme pour retirer des paquets, le reste est une série de
commande a rallonge, comme la commande de mise a jour:

    # urpmi.update -a && urpmi --auto-select

c'est tellement plus rapide un dnf update... Je lance donc
l'installation de DNF.

    # urpmi dnf

Ce qui me lance l'installation, entre autres, des paquets deltarpm et
dnf-yum. Une raison de me passer de URPMI est aussi un vieux bugs, en
tout cas pour moi, d'un comportement hérité de Mandriva, le
téléchargement et l'installation des paquets 7 par 7, au lieu de tout
télécharger et d'installer le tout a la suite. C'est a ma connaissance
le seul utilitaire qui a ce comportement, heureusement modifiable dans
sa configuration. J'en profite pour installer kinfocenter avec dnf, il
met en place le cache dont il a besoin, je suppose que c'est un cache
différent de urpmi, je me demande donc comment va se passer les
interactions entre dnf, urpmi et installer/supprimer des logiciels du
CCM. Je me rappel qu'il y a pas si longtemps, sous Debian il était
conseiller de choisir entre
[APT](https://fr.wikipedia.org/wiki/Advanced_Packaging_Tool) et
[APTITUDE](https://fr.wikipedia.org/wiki/Aptitude_(logiciel)) et d'y
rester. En fin de compte je n'utiliserais pas DNF, celui-ci me trouvant
moins de mises a jour que par URPMI. Je me dis qu'il vaut mieux jouer la
sécurité et utiliser les outils prévu par défaut, comme ça si ça merde
ça ne sera pas a cause d'un outils tiers mal intégré. C'est aussi là,
que je trouve que le bon vieux URPMI a fait son temps, des mises a jour
sur ma tumbleweed c'est chose fréquente et sur ma leap aussi, j'arrive
fréquemment avec plus de 200 mises a jour qui sont fait en moins de
temps que 200 mises a jour avec URPMI, qui passe son temps, a le perdre,
il faut bien l'avouer, en lançant je suppose aria2 pour télécharger 7
paquets, puis les installer, puis relancer aria2 pour en télécharger 7
autres, ect..., Je ne comprends pas que l'équipe ne trouve pas important
ce comportement qui est source de ralentissements, de possibles
problèmes, de prise de tête pour les programmes de bas niveau qui
doivent savoir par où commencer, télécharger les 7 premiers logiciels
les installer, tout ça en pensant qu'il faut déjà les dépendances de
ceux la, bref un beau merdier que je n'arrive pas a trouver un autre
exemple... Même le vénérable APT rapatrie tous les paquets puis les
installe. Du coup une mise a jour qui aurait pu mettre entre 30 minutes
et 1 heure va faire facilement 2 heures. En parlant, je vois que Urpmi
ne fait pas que du 7 par 7, il vient de me faire 37 paquets d'un coup
comme quoi c'est un peu la fête du slip la dedans! Je ne comprend pas
non plus cette course a la fraîcheur alors que le projet va mettre une
éternité pour ensuite passer a la prochaine version, je m'explique, on
va avoir gnome 3.22, plasma 5.8.4, un kernel en 4.8 qui va sûrement
passer en 4.9 qui me semble sera le prochain kernel LTS, tout ça est
bien beau, c'est même super, mais par la suite ils vont tellement
attendre que la distribution ne sera plus en mesure de s'installer sur
du matos récent, par exemple Mageia 5 actuellement ne s'installe pas sur
du matos a base de skynet. Je pense ne pas être le seul a préféré un peu
moins de fraîcheur de base mais plus d'évolution en cours de route, un
peu ce que fait Fedora/openSUSE, et peut être plus de versions ou du
moins ne pas attendre pratiquement 2ans pour une version, actuellement
la version 5 à 1 ans et 5 mois, d'ici février elle fêtera ses 20 mois
d'activité... Alors c'est pas la mort en soi, openSUSE a une version
tous les 18 mois a peu prés, mais entre temps, cette distribution évolue
soit par la mise a jour via les dépôts classiques, ou en prenant des
dépôts officiels comme celui de son bureau attitré, chez moi ma leap
42.1 était déjà en plasma5.8.3... Ceci étant dit, après 2 heures 15
minutes, les mises a jour sont enfin faites, je vais certainement
retrouver le bug du X11 au reboot de la machine. Verdict, non le bug a
dû être corrigé entre le 21 novembre et le 2 décembre, ce qui est quand
même sympathique. Bon première chose de vraiment sympa, j'en avais parlé
vite fait la dernière fois dans ma critique sanglante de cette
distribution, c'est le thème par défaut, il est juste magnifique, rappel
parfaitement l'héritage de Mandriva qui nous offrait toujours un look
sympa avec des couleurs vives, chose que Mageia avait un peu oublié avec
des tons sombres et tristes ou souvent laid, notamment le look de la
mageia 1... Le thème de GRUB2 reprend celui de l'ensemble, très jolie
comme on peut le voir.
![virtualbox\_mageia-6\_02\_12\_2016\_16\_53\_11](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_16_53_11-1024x768.png){.aligncenter
.wp-image-882 .size-large width="840" height="630"}Petit soucis pendant
le boot, on peut voir que bootsplash se montre timide sous virtualbox,
certainement un bug dû a celui-ci
![virtualbox\_mageia-6\_02\_12\_2016\_16\_53\_48](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_16_53_48.png){.aligncenter
.wp-image-883 .size-full width="800" height="600"} Toutes les images de
ce theme n'ont pas forcément le même ton, ce qui donne des images plus
clair ou plus sombre, peut être dû a virtualbox, cela ne mange pas de
pain!![virtualbox\_mageia-6\_02\_12\_2016\_16\_54\_31](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_16_54_31.png){.wp-image-884
.alignnone width="800" height="554"} Magnifique SDDM.
![virtualbox\_mageia-6\_02\_12\_2016\_16\_54\_46](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_16_54_46.png){.aligncenter
.wp-image-885 width="800" height="554"} C'est moins facile a voir en
image, mais mater cet écran de chargement de plasma avec le chaudron et
ses bulles qui
apparaissent!![virtualbox\_mageia-6\_02\_12\_2016\_16\_55\_09](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_16_55_09.png){.aligncenter
.wp-image-891 width="800" height="554"}
![virtualbox\_mageia-6\_02\_12\_2016\_16\_55\_30](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_16_55_30.png){.aligncenter
.wp-image-892 width="888" height="615"} Vous pouvez le voir en action
via [la vidéo
d'Adrien.d](https://www.youtube.com/watch?v=dU27G25d_34&t=130s). Enfin
voila le bureau vu par défaut:
![virtualbox\_mageia-6\_02\_12\_2016\_17\_05\_25](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_17_05_25.png){.aligncenter
.wp-image-894 width="888" height="615"}
![virtualbox\_mageia-6\_02\_12\_2016\_17\_04\_45](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_17_04_45.png){.aligncenter
.wp-image-893 width="888" height="615"} Ce qui change de l'ancien thème
de la 5. On voit bien le bond entre la STA1 et cette version mis a jour.
![virtualbox\_mageia-6\_02\_12\_2016\_14\_38\_57](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_14_38_57-1024x493.png){.aligncenter
.wp-image-876 .size-large width="840"
height="404"}![virtualbox\_mageia-6\_02\_12\_2016\_17\_26\_42](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_17_26_42.png){.aligncenter
.wp-image-895 width="888" height="615"} Le look de cette 6éme version
est vraiment sympa a mon sens. L'installation est aussi bien plus
complète, puisque des paquets manquant comme Ksysguard sont a présent
bien là. Il manque toujours une suite bureautique, libreoffice ou
calligra peu importe mais un truc car là il n'y a toujours rien, Firefox
est manquant, peut être que si j'avais passé via une STA2, ces paquets
cités seraient présent, je ne pourrais pas le dire vu que ma STA2
netinstall a merdé. Le tout étant bien francisé, merci plasma 5.8. Je
note quand même que le pack d’icône breeze a bien été installé et c'est
celui utilisé par défaut, je dis ça car précédemment ce n’était toujours
pas le cas, le pack d’icône choisi étant celui d'oxygen (de kde4), un
peu vieillot. Je trouve l’icône du réseau géré par l'éternel Network de
Mandriva et non par NetworkManager de RedHat, vraiment dégueulasse,
dommage car il a l'air joli mais il est flou et baveux comme pas
possible, peut être du a ma résolution sous virtualbox. Le tout ne mange
pas beaucoup de ressources, je note un 513 mo de ram sur 1.8 go et 10%
de processeurs. Correcte pour du KDE.
![virtualbox\_mageia-6\_02\_12\_2016\_17\_29\_45](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_17_29_45.png){.aligncenter
.wp-image-896 width="888" height="615"} Autre chose, je trouve chiant
les sous menu "plus" dans le lanceur d'application, sur mon openSUSE, je
n'ai pas ça et je m'en porte bien mieux.
![virtualbox\_mageia-6\_02\_12\_2016\_17\_45\_28](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_17_45_28.png){.aligncenter
.wp-image-897 width="888" height="615"} Je voulais vous montrer un truc
sympa avec DNF, je regarderais si URPMI le fait aussi par la suite,
c'est l'installation de la langue de l'utilisateur (celle du système par
défaut) quand on sélectionne certains paquets, comme firefox ici:
![virtualbox\_mageia-6\_02\_12\_2016\_17\_44\_11](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_17_44_11.png){.aligncenter
.wp-image-898 width="888" height="615"} Donc comme dit, j'ai fais de
même avec URPMI et c'est a l'utilisateur de sélectionner son pack de
langue, c'est moins bien que DNF mais au moins il demande.
![virtualbox\_mageia-6\_02\_12\_2016\_17\_48\_29](http://download.tuxfamily.org/passionlinux//VirtualBox_mageia-6_02_12_2016_17_48_29.png){.aligncenter
.wp-image-900 width="888" height="615"} Mais bon DNF n'a pas toujours
tout bon puisque par la suite il m'installera libreoffice avec le pack
de langue anglais. Cela me rappel une certaine Fedora... Ce que j'aime
toute fois chez lui, c'est qu'il va télécharger plusieurs paquets en
même temps ce qui fait gagner un peu de temps. Je n'ai pas fait
attention si Zypper (openSUSE) dont DNF s'inspire et utilise ses libs,
le faisait de son coté.  

> *DNF* (Dandified Yum), est le nouveau gestionnaire de paquets pour les
> distributions basées sur « [RPM](http://www.rpm.org/){.external
> .text} » (RPM Package Manager). Conçu de sorte à rester très proche de
> *Yum* à l'usage, il n'en reste pas moins un tout nouvel outil
> nettement plus performant, doté de fonctions de gestions et de
> résolutions des dépendances beaucoup plus avancées (*librairie libsolv
> + API Hawkey*). Disponible depuis *Fedora 18*, DNF est le gestionnaire
> de paquet par défaut depuis *Fedora 22*. Les gestionnaires de paquet
> ont toujours été une composante primordiale des distributions
> Gnu\\Linux, de sorte que cette nouvelle édition de yum permet de poser
> des bases solides qui serviront à ancrer le futur de Fedora.
> </p>

Je trouve tout de même que ce dernier est moins rapide que Zypper par
contre c'est le jour et la nuit face a Yum et URPMI. Je ne change pas
d'avis sur Mageia, une bonne distribution mais qui reste pénalisé par
une équipe fébrile, en manque de ressources et de moyens, en manque de
mains d'oeuvre, qui reste sur les acquis, qui ne font pas forcément des
choix justes, qui n'ont pas le courage de taper dans les bureaux peu
utilisés, qui n'ont pas le courage de choisir un bureau et de s'y
fixer,... Choses qui vont, tôt ou tard, devoir être fait par nécessité,
par obligation, comme peut être choisir un gros bureau, kde pour ne pas
le citer et le rendre officiels et les autres environnements (mate,
xfce, gnome, ect...), en faire des saveurs communautaires, comme Fedora
le fait depuis des lustres avec les SPINS de kde, xfce, pour ne citer
que ces deux la. Je ne mise plus beaucoup sur cette distribution, dans
l'état actuel, elle n'a rien pour se vendre, rien qui puissent pousser a
son utilisation, entre des bugs issus de Mandriva (urpmi installation
7par7, liste des dépôts vierge, CCM qui vieillit mal...), entre des
environnements mal intégrés ou simplement horribles dans leurs
configurations par défaut issus aussi de Mandriva, comme celle de XFCE,
et d'autres joyeusetés qui lui sont propre, je ne conseille pas cette
distribution. Je garde sous le coude cette version 6 dans mon virtualbox
pour voir comment elle évolue.
