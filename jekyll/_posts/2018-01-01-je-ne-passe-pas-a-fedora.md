---
title: "Je ne passe pas à Fedora!"
date: 2018-04-13T14:59:33+02:00
layout: post
---

La dernière fois que j'ai parlé de Fedora, c'était le 8 mars de cette année, déjà plus d'un mois, j'avais entre autre remarqué une installation très light de l'environnement Gnome, un LibreOffice venant en anglais et non dans ma langue, seul logiciel de mémoire qui fut sans sa traduction mais en même temps c'est un cas que je n'ai plus vu depuis un baille et seulement sur des rolling ou des versions de développements ou sinon sur des distributions de seconds rangs comme Sabayon. Non mais le pire est à venir, DNF, bien que plus rapide que son prédécesseur, le nommé YUM, plus lent que URPMI(Mandriva/Mageia/openmandriva…) c’est dire... Pourtant bien plus récent que l’ancêtre APT, celui-ci arrive à le surpasser dans la vitesse de mise à jour et d’installation de paquets, mais j'y reviendrais.

Je disais dans mon premier billet sur Fedora que je trouvais Gnome 3.26 bien plus réactif que sous Debian,en fait:

> Allez je commence les bons points, qu’est ce que c’est beau, rapide, simple, bien foutu ce bureau GNOME chez Fedora, merde une claque! Faut dire que chez Debian, je suis en version 3.22 alors forcément on ne profite pas des dernières trouvailles et améliorations. J’ai clairement la sensation que le GNOME Fedora est bien plus vivace que celui de Debian et autre. 

Ce fut plutôt le contraire, peut être l'excitation de la découverte, mais ce n'est pas lié à Fedora mais directement à Gnome qui s'est alourdi, c'est flagrant quand on passe de Debian stable vers Sid, Fedora ou Tumbleweed (3.26 et 3.28 testé), entre la vivacité et la consommation aberrante de ce bureau. Encore plus marquant si on passe de Leap qui vient avec un Gnome 3.20 (donc plus ancien que celui de Debian) à Tumbleweed. C'est simple, au démarrage il me consomme 3 fois ce que plasma 5.8 et 5.12 consomment.

Mais je ne suis pas là pour casser ce bureau que j'ai appris à aimer, non j'écris pour expliquer la raison que je ne serais jamais capable de passer sur du Fedora et que dorénavant je la considère incompatible avec moi. Je disais sur le deuxième billet de cette "série":

> je suis assez content de la bête, en faite c’est surtout avoir un GNOME plus à jour qui me fait aimer la Fedora car sinon je dois dire que c’est limite à chier.
....
La lenteur de DNF est aussi un autre soucis, bon c’est pas au niveau de celle de Emerge mais ça reste long, on ne va pas en faire une pendule mais je pense qu’il y a beaucoup à faire pour améliorer le bestiau.
....
L’installateur Anaconda a clairement des soucis, de lenteur d’une part, de stabilité au moment du partitionnement et puis au moment de l’installation en elle même j’ai eu des gels, soit la barre indiquait très vite 100% et restait comme ça dix minutes ou la barre montait doucement jusqu’à son arrêt en cours de route pendant un certain temps puis en allant sur la vue éclatée de GNOME et en revenant sur Anaconda, la barre se mettait à jour.
....
Dernière chose qui ne me plaît pas des masses, c’est la logithèque de GNOME, je trouve chiant la non possibilité de cocher plusieurs paquets à installer, là dans la conception actuelle, il faut choisir/chercher son logiciel, et aller sur installer, puis sortir du résumé du programme et refaire l’opération pour un autre logiciel.

Je reconnais avoir été loin dans le " c'est limite à chier" mais c'est mon ressenti, je n'aime pas et il m'a fallu deux semaines et encore c'est large pour lâcher l'affaire. Pour reprendre mes plaintes le jour de mon renoncement:

> Comme dit plus haut, je me suis jeté dessus, oui je suis un peu déçus de la Fedora, je reste avec des choses bancales, un DNF qui n’arrête pas de se plaindre sur les dépôts RPMFusion, Logiciel qui me donne des messages d’erreurs ou encore DNFdragora, le truc de Mageia avec un look digne des années 2000, qui souffre d’une lenteur qui me rappel celle de rpmdrake de Mandriva… Une simple recherche prends du temps, plusieurs secondes, bref des choses qui dans le cas de Apt ou Zypper ou encore de leur “GUI”(comme Synaptic et Yast) ne sont pas. On va me dire que c’est moi qui merde, peut être, je dis pas le contraire, mais quand on fait une simple recherche avec dnf search paquet qui nous balance le résultat comme un porc sans information de l’état des paquets (installé ou non) mais en nous séparant par correspondance exacte et ayant pour nom ou description le nom donné, ou avec dnf list paquet qui là aussi nous livre la recherche en séparant en deux les installés et installables, résultat dans les deux cas peu pratique et bien plus long à trouver ce que l’on recherche qu’avec Zypper et son joli tableau ou Apt et sa liste par ordre alphabétique avec statut des paquets. Aussi lenteur aussi bien perçue avec DNF au moment des recherches et des installations que dans dnfdragora qui lui bat des records en prenant du temps rien qu’en changeant le layout de vue des paquets (tous ou groupe) comme à la grande époque de Mandriva. Bref, un billet sur ça est en finition.

On a dit (j'ai vu ici et là) que je ne savais pas utiliser DNF ou encore d'autre choses, entre autre comparer DNF et APT c'était des conneries, et bien non, un gestionnaire de paquets est un gestionnaire de paquets point barre, surtout que je ne compare pas l'incomparable comme faire une comparaison de emerge par rapport à un autre et n'importe lequel des gestionnaires de paquets binaires! Non je n'ai fait que des mises à jour, des suppressions et des installations de paquets, choses des plus classiques pour ce genre de programmes! En l’occurrence, quand APT et Zypper me font une installation très rapide d'un même paquet alors que DNF est à la traîne, c'est pas moi qui invente ou qui ne sais pas utiliser le programme. Et puis j'ai aussi écouté par ci et par là, effectivement DNF est reconnue pour être plus rapide que YUM (en même temps c'était pas dur...) mais reste lent pour des choses basiques. Un [comparatif qui vaut ce qu'il vaut](https://fusion809.github.io/comparison-of-package-managers/) mais à au moins le mérite d'utiliser la commande `time` , je ne suis pas d'accord sur tout, en particulier sur la partie APT puisque la personne faisant le test parle de fonctions manquantes ou dispatcher dans plusieurs sous-commandes, c'est juste oublier l’effort depuis 4 ou 5 ans de tout rassembler dans la nouvelle commande APT (apt-get, apt-cache...). Ce qui m’intéresse en particulier, la partie vitesse dans chaque gestionnaire de paquets qui conforte mon ressenti de lenteur de DNF. Je reprends ici le temps qu'il a trouvé sur sa bécane pour installer un même paquet:

APT: 2.783s
DNF: 16.853s,
11.977s (DNF 2.1.0)
Pacman: 0.464s
YUM: 8.461s
ZYpp: 1.02s

Il trouve très étrange et il est certain qu'il y a un soucis, c'est de voir Yum plus rapide que DNF.
De mon coté, je dirais que dépassé le temps de APT est déjà trop.

Je ne reviens pas sur les fonctions de recherche que je ne trouve pas aussi lisibles qu’avec APT et surtout ZYpp, je ne reviens pas non plus sur les demandes d'info sur un paquet qui sont très bien voir mieux que sous APT, et pareil que sous ZYpp. Par contre je remets une couche sur cette merde d'un autre temps qu'est le DNFdragora, c'est lent, ultra lent, c'est moche, ça manque d'options qu'on Synaptic (le plus vieux) et Yast-suppression-installation-de-paquets, ça plante,... C'est juste le truc de Mandriva/Mageia Drakerpm remis à jour mais restant merdique!

En résumé, le portable est passé à Leap avec un Plasma 5.12. J'ai pour ma part un peu, voir beaucoup de mal à lâcher Debian mais je pense qu'a terme c'est sûr que je quitterais Debian, j’expliquerais mes raisons qui sont essentiellement collaboratifs et participatifs dans le projet, en gros c'est pas facile de participer chez Debian, faut faire tout un tas de trucs alors que sous openSUSE, il n'y a rien à "prouver" juste faire!
