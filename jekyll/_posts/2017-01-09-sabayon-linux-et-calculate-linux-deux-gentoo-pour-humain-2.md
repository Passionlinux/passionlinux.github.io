---
title: Sabayon linux et Calculate linux, deux Gentoo pour humain #2
date: 2017-01-09 15:59
layout: post
---

Alors voici la suite du dernier billet qui parle cette fois-ci de
Calculate, je reviens toute fois vite fait sur mon essaie de Sabayon,
c'est vraiment le layout de distribution qui donne envie de retourner a
Windows, clairement je m'attendais a beaucoup mieux et j'ai eu bien pire
que prévu... Ceci étant dit, partons sur cette Calculate dont j’entends
le plus grand bien! Ce qui m’intéresse avant toute chose est son
calculate-console qui me permettrait de me connecter sur l'ordinateur de
mes parents pour effectuer les mises a jour par exemple sans devoir
gérer une connexion SSH par moi même. Pour commencer, Calculate est
proposé comme pour Sabayon en plusieurs saveurs (Xfce, KDE, Gnome,
Mate...) et contrairement a Sabayon, elle est proposé en 32 et 64 bits.
Je suis partis pour faire trois test, un en virtualbox, un sur une clef
USB et un autre en dur (en vrai) sur ma machine pour remplacer mon
openSUSE qui m'ennuie tellement elle est stable et qui se passe rien. Je
ne parlerais que du test en durs sur ma machine puisque les autres
n'ayant peu ou pas de valeur.  
<!--more-->  
Le test en virtualbox me donna vraiment envie de la mettre sur ma
machine principale, me disant que les lenteurs d'installations seraient
bien moins visible sur ma bécane en dur. Dès le live je suis vraiment
bluffé, que ce soit la version Xfce ou KDE, mes deux écrans sont réglés
de façon qu'il sont complémentaire et non en miroir ou affichant les
deux le même écran, seul mon openSUSE me faisait ça auparavant.
L'installateur est un peu susceptible, j'ai réussi facilement a le faire
planter mais rien de grave car si on le relance il garde en mémoire ce
qui a été déjà fait comme réglage. L'autre bonne chose c'est que
l'installation est simple et ne durs pas longtemps, a peu prés le même
temps que openSUSE, c'est a dire 10 ou 15 minutes. J'ai tout de suite
aimé le look de kde et de xfce, une barre en haut (barre principale) et
une en bas pour des raccourcies d'applications. Je vais me centrer sur
la version xfce:
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_20-22-33-1024x576.png){.aligncenter
.size-large .wp-image-967 width="700" height="394"} Tout est bien
traduit, Libreoffice est bien dans la langue de molière, l'environnement
aussi, Firefox est aussi dans ma langue, bref c'est tout bon, cerise sur
le gâteau, si on lance hexchat pour avoir de l'aide sur le canal IRC de
Calculate, on est directement dans le salon FR!
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_21-39-22-1024x576.png){.aligncenter
.size-large .wp-image-969 width="700" height="394"} J'ai apprécié le
Calculate-console qui permet tout un tas de configuration un peu comme
ce que fait Yast (SUSE) et le CCM (Mageia).
![](http://download.tuxfamily.org/passionlinux//2017/01/Capture-décran_2017-01-04_21-30-44-1024x576.png){.aligncenter
.size-large .wp-image-968 width="700" height="394"} J'ai voulu voir
comment se passait les mises a jour, on a la possibilité de le faire en
graphique ou en mode console avec cl-update, j'ai tenter les deux sur
deux machines différentes et c'est vraiment très long, on se retrouve
dans les mêmes travers que Sabayon, c'est a dire une mise a jour des
dépôts très longue puis une recherche de dépendances encore plus longue
suivit du téléchargement et de l'installation des paquets vraiment très
longs, exemple concret sur ma machine, la mise a jour de 17 paquets a
duré pratiquement 50 minutes... Puis je me suis lancé dans
l'installation de paquets, comme pour Sabayon, j'ai pris les même pour
voir un peu, c'est a dire thunderbird, amule, minidlna, scummvm, vivaldi
et 0ad. Le gestionnaire de paquet, ici c'est emerge de Gentoo, est
encore plus lent que equo, on a le droit a la recherche de dépendances
qui dure bien trop longtemps (pas loin de 10-20 min) puis l'installation
avec compilation presque le double... Comme pour Sabayon, c'est
rédhibitoire cette lenteur. Alors oui, on ne fait pas de mise a jour ou
d'installation de paquets tous les jours mais je ne me vois pas aller
chez quelqu'un et y passer toute la journée pour installer quelques
paquets alors qu'avec une autre distribution on aurait mit 5 minutes...
Dans mon cas et pour l'utilisation que j'en fais, ce n'est pas valable,
j'ai pas envie de lancer une mise a jour et d'aller me coucher car elle
dure la nuit, non je n'ai pas envie de mettre une plombe pour installer
un logiciel que j'ai voulu essayer, oui ça m'arrive souvent d'installer
un paquet de ce layout... Et puis honnêtement, Calculate étant une rolling
cela veut dire qu'il y a des mises a jour fréquentes, notamment étant
sur Plasma 5 et en voyant la quantité de mises a jour et de paquets en
rapport avec kde, je me doute bien que je vais passer une journée
entière a les faire sous Calculate! Je me suis posé quand même la
question un petit moment, je reste sur cette calculate pour voir au
moins comment se passe la semaine ou je retourne directe sur ma
opensuse, puis j'ai lancé l'installation de tous mes paquets, un nombre
important de jeux, de logiciels de partage (P2P), de programmes
multimédia, ce qui représentait a peu près 200 paquets (dépendances
comprises), la recherche de dépendances se fait, elle dure, elle dure,
je retourne voir mon film que j'ai mis en route (blaire witch 2016)...
Je reviens devant l'écran du PC après 30 minutes approximativement et je
vois que le téléchargement des paquets est en cours, je retourne voir la
suite de mon film... Je me suis endormi devant la TV et en me
réveillant, je suis retourné voir le PC, toujours en cours 2 heures plus
tard et je me suis décidé a aller me coucher. J'ai vu plus tard (le
lendemain) que l'installation de certains paquets avaient nécessité des
compilations ce qui explique le temps abusé de cette installation qui
dure normalement avec openSUSE entre 5 et 10 minutes. Pour le moment je
me suis remis une leap 42.2,  l'installation et le rajout de mes paquets
a duré moins d'une heure avec la configuration, c'est a dire 9 minute
d'installation (via une clef USB), une première mise a jour de 200
paquets et plus en 10 minutes, rajout des dépôts multimédia dont
/Packman, puis ajout des dépôts /Games /Games:tools et /Emulators avec
mise a jour qui a suivit. C'est ensuite l'installation de tous mes
paquets, comme wine, scummvm, mldonkey, etc... et qui représentent a peu
près 2Go de paquets (+ ou - 200 paquets)en moins de 10 minutes. Pour le
moment je regarde de loin la calculate en cherchant un intérêt plus
important que le simple calculate-console qui me permet de gérer a
distance d'autres calculates puisque de toute façon chez mes parents, il
est hors de question que je la mette en place, vu le temps qu'il me
faudrait pour installer les paquets que mon père me réclame pour ses
besoins... Je cherche un avantage qui pourrait me faire dire oui c'est
la distribution qu'il me faut, mais rien ne me vient a l'esprit!
L'installation est rapide certes mais celle d'opensuse l'est tout
autant, elle est en publication continue, oui c'est vrai que ça change
de ma leap (opensuse), mais si je le veux la tumbleweed (opensuse) est
une distribution a publication continue. Dans les défauts je note
l'installation des paquets et les mises a jour qui durent, durent... A
croire que toutes les gento-likes sont des merdes sans noms dans la
gestion de paquets, ça doit être dû au mixage des paquets binaires et
des paquets a compiler, je sais pas mais c'est pas top! Maintenant, j'ai
été un peu sur IRC et j'ai adoré l’accueil qu'on m'a donné, les gars
la-bas sont sympathiques, voila ça c'est dit! J'en ai fini avec ce test
de distribution, je ne ferme pas totalement la porte a Calculate
contrairement a Sabayon, mais pour le moment je préfère l'avoir sur une
machine virtuelle que sur ma propre machine.
