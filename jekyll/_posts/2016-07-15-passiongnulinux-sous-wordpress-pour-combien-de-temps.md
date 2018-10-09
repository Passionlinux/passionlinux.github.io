---
title: PassionGNU/Linux sous Wordpress pour combien de temps?
date: 2016-07-15 20:14
layout: post
---

Dans le [billet précédent](http://passiongnulinux.tuxfamily.org/?p=6),
je vous racontais mes déboires avec mon passage sous Wordpress. Je
n'avais pas d'obligation de le faire, j'avais un outils qui me plaisait,
mais je suis du genre a tester a tout va pour me faire mon opinion.
Gilles tente du mieux qu'il peut a me servir de guide, car faut bien
dire que je suis paumé sous Wordpress... C'est bien la première fois que
j'ai besoin de lire une documentation pour un CMS.  
<!--more-->  
Tout d'abord on va rectifier les conneries que j'ai dis hier et que
Gilles a démontré le contraire, "des thèmes a foison mais rébarbatif,
souvent le même style", c'est simplement faux, beaucoup de thèmes se
ressemblent mais d'autre marquent leurs différences, je trouve toujours
pas chaussure a mon pied, on verra bien. La ou j'ai dis une grosse
connerie et je m'en excuse, c'est sur: « – liste des billets avec peu de
possibilité d’actions, on a la possibilité seulement de « modifier » et
« déplacer » dans la corbeille, sous Dotclear depuis la liste des
billets on a plus de possibilités, on peut supprimer, changer de
catégories, renommer, changer le rédacteur, la date : désolé, mais tu
devrais cocher tes articles et choisir « Modifier » dans la liste des
actions, tu serais surpris de voir le résultat. » Si on coche plusieurs
billets, puis on fait modifier, on aura bel et bien toute les actions
que j'avais l'habitude d'avoir sous Dotclear. J'en ai dis une autre, sur
la publication d'un brouillon, je disais: « c’est a nous de donner
l’heure et la date, il n’y a pas de bouton pour mettre l’heure actuelle
(utile quand on a un brouillon qui date et qu’on veut le poster après
des billets qui sont accepté avant) : maintenant que tu le dis, je n’ai
pas testé, mais en regardant là j’ai un doute car j’ai un brouillon du
26 juin et si je clique sur « Publier » il est à la date du jour :p » La
aussi, c’était certainement dû au billet qui venait de Dotclear, celui
ci a été daté et j'ai du changer la date. Bref je viens de refaire un
test avec un billet propre et effectivement c'est daté du jour de la
publication. Il me reste encore un truc qui ne me plaît pas du tout
c'est les révisions, je trouve ça bien mais a conditions que les
anciennes révisions sont effacé petit a petit. J'ai lu la doc en
anglais, il faut que je touche a un fichier, c'est très user friendly...
Bref, je sais pas si les révision pompe beaucoup de place, si ça n'en
prend pas des masses autant les laisser. J’arrête pour de bon avec SPIP,
par contre je ne sais pas si je prends Wordpress ou je garde Dotclear
avec lequel je suis habitué. Le seul truc qui peut désavantager Dotclear
c'est son nombre de développeurs, il doit y en avoir 2 ou 3 mais guère
plus. Vu que je pense sur le long terme, je me dis que dotclear peut
disparaître assez facilement et qu’après faudra bien que je passe a
autre chose donc une migration, vers Wordpress, donc pourquoi pas passer
de suite tant qu'il y a encore un plugin pour le faire. Je pourrais
aussi repartir sur du Pluxml, mais honnêtement a part son poids, il n'y
a rien de terrible, il fait son taf mais sans plus, pas de lien interne,
pas beaucoup de thème, pas de "billet a retenir" ou "mis en valeur" sous
Wordpress, pas même d’éditeur par défaut, il faut a prendre un plugin...
Par contre je reviens sur les liens internes, sous SPIP, il n'y a pas de
sélecteur de billet, il faut simplement connaître le numéro (c'est dur)
et le mettre a la place d'un lien, comme ceci:

    [->203]

et ça nous fera un joli lien avec le nom du billet: [Les conseilleurs ne
sont pas les payeurs.](http://passiongnulinux.tuxfamily.org/?p=6)

    [précédent billet->203]

nous fera un lien vers le billet 203 sur [précédent
billet](http://passiongnulinux.tuxfamily.org/?p=6). Les liens internes
sous SPIP sont du layout:

    spip.php?article203

il ne mette pas l'adresse en entière:

    http://passiongnulinux.tuxfamily.org/spip.php?article203

Ce qui permet, en cas de déménagement de site (changement d’hébergeur)
de ne pas se retrouver avec des liens casser... Sous dotclear, c'est
presque pareil, les liens internes sont fait avec un sélecteur de billet
un peu comme celui de Wordpress, donc pas besoin de retenir l'article ou
le numéro et sont du layout:

    index.php?post/2015/03/02/374-Les-conseilleurs-ne-sont-pas-les-payeurs

Ce qui permet là aussi de garder les liens malgré un changement
d’hébergeur. Sous Wordpress, c'est comme sous Dotclear, il y a un
sélecteur de billets par contre les adresses sont données en entier:

    http://passiongnulinux.tuxfamily.org/?p=6

Du coup si on change d'hébergeur on est dans de sale draps et on se tape
le changement de tous les liens internes. Par contre je viens de voir
que que si on colle directement l'adresse du billet sans le mettre dans
un cadre de code préformaté, on a ceci:
http://passiongnulinux.tuxfamily.org/?p=6 C'est vraiment pas mal!!!
Bref, on a quand même de bons outils dans nos mains, on verra comment
progresse ce site avec ce moteur, voir si il gonfle pas de trop avec le
temps, ect, ...
