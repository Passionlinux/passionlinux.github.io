---
title: "Je passe à Fedora 2"
date: 2018-03-05T15:36:55+01:00
layout: post
---
Je suis dans mon troisième jours avec cette Fedora, je suis assez content de la bête, en faite c'est surtout avoir un GNOME plus à jour qui me fait aimer la Fedora car sinon je dois dire que c'est limite à chier. Soit je rate des choses et c'est fort probable vu le peu de maîtrise que j'en ai, entre le RPM, le gestionnaire DNF et la distribution en elle même... Mais si je mets de coté ce genre de choses, j'ai par exemple une installation très minimale de GNOME: pas de Brasero par exemple, ni de Tweak, pas de Gimp,... Et ça ce ne sont que des logiciels qui me viennent à l'esprit. Je pensais à tort que Fedora m'aurait donné la meilleur expérience et la plus complète du bureau GNOME, l'expérience pour le moment je n'ai pas à y redire, maintenant sur la partie GNOME complète, il manque des logiciels qui pour moi sont essentiels.

J'ai donc voulu, bêtement je dois bien l'avouer, installer un "méta-paquet" regroupant tout GNOME ou du moins une grosse partie, comme on peut trouver chez Debian pour les différents bureaux ou bien sur d'autres distributions dont Mageia pour ne citer qu'elle, mais je n'ai pas pu trouver ou n'ai pas su, DNF étant assez pénible pour moi et mon utilisation ou mes habitudes de vieux con de debianeux. En effet, j'ai bien fait des `dnf search gnome` mais dans ce cas, il me sortait une liste sans fin de paquets et je n'ai rien vu de concluant, à noter toutefois que contrairement à Apt, DNF ne précise pas si le paquet dans la liste est déjà installé ou non.

La lenteur de DNF est aussi un autre soucis, bon c'est pas au niveau de celle de Emerge mais ça reste long, on ne va pas en faire une pendule mais je pense qu'il y a beaucoup à faire pour améliorer le bestiau.

L'installateur Anaconda a clairement des soucis, de lenteur d'une part, de stabilité au moment du partitionnement et puis au moment de l'installation en elle même j'ai eu des gels, soit la barre indiquait très vite 100% et restait comme ça dix minutes ou la barre montait doucement jusqu’à son arrêt en cours de route pendant un certain temps puis en allant sur la vue éclatée de GNOME et en revenant sur Anaconda, la barre se mettait à jour.

La partie update s'est quant à elle bien passé, malgré les 730 mises à jour, ce fut un peu lent mais le résultat est là.

Dernière chose qui ne me plaît pas des masses, c'est la logithèque de GNOME, je trouve chiant la non possibilité de cocher plusieurs paquets à installer, là dans la conception actuelle, il faut choisir/chercher son logiciel, et aller sur installer, puis sortir du résumé du programme et refaire l'opération pour un autre logiciel. Ce genre de fonctionnement est peut être viable dans des *CMS* layout **SPIP**, **Wordpress** ou **Dotclear** mais clairement pas dans des OS où il montre ses limites.

Maintenant reste une dernière petite chose, les dépôts externes layout RPM-Fusion, j'aurais aimé m'en passer mais non, je n'ai pas eu le choix pour la vidéo mais c'est très simple à mettre en place. Par contre j'ai toujours certains programmes qui n'apparaissent pas dans la logithèque de GNOME comme VLC, mais ça ce n'est qu'un contre temps puisque j'utilise uniquement le mode console et DNF pour la gestion des paquets. J'ai eu quand même quelque chose de peu normal, enfin c'est ce que je pense, la logithèque de GNOME m'a poussé une gueulante en me parlant de YUM qui ne pouvait pas faire un truc or je pensais naïvement que YUM n'était plus de la partie, laissant intégralement sa place à DNF, j'ai peut être raté un truc.

Donc comme dit dans le dernier billet, je tente de rester jusqu'à la prochaine version Fedora c'est à dire la 28, en espérant que je tienne et supporte les bizarreries de cette distribution.
