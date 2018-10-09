---
title: "Cette Leap m'étonne toujours"
date: 2018-04-29T23:13:37+02:00
layout: post
---

Je n'ai pas fais de billets depuis bientôt deux semaines, c'est pas plus mal ça me permet de ne pas tirer sur certains cas sociaux venant de la communauté de Mageia (MLO bien sur!) et qui n'ont pas aimé que je dise certaines choses sur leurs mentalités de merde d'enfants gâtés à qui on aurait insulté leurs mères. Je me calme en me disant que la disparition de cette distribution se fera dans l'indifférence la plus totale, comme ferait la perte d'un énième fork d'Ubuntu. Passons à autre chose.

En ce dimanche 29 avril, je regardais un peu les nouvelles fraîches, Gimp 2.10 sortie plus tôt dans la semaine est déjà présent dans les dépôts de openSUSE leap 15.0 et Tumbleweed, je me demande si c'est nécessaire que je retro-porte le paquet pour la leap 42.3 qui doit bientôt céder sa place à la 15.0, normalement vers la fin mai, le 25 mai pour être précis. Il est aussi disponible pour Debian SID, peut etre si j'ai le courage je ferais un backport pour la Stable, mais vu que pour le moment je n'ai pas de Debian à la maison... Mais pas encore sous Archlinux, ça fait quelques fois que je note une disponibilité plus rapide de paquets sur openSUSE Tumbleweed que sur Archlinux, si je rajoute sa simplicité d’installation et d'entretien ainsi que son plus grand nombre de paquets (je parle en paquets sources), je pense qu'a terme cette version de la SUSE sera la plus prisé des fanatiques de rollings. Je pense aussi que OBS et la simplicité de contribuer à openSUSE n'y sera pas pour rien.

![Gimp sous Archlinux](https://download.tuxfamily.org/passionlinux/captures/gimp-arch-28042018.png)

![Gimp sous Debian SID](https://download.tuxfamily.org/passionlinux/captures/gimp-debian-28042018.png)

![Gimp sous openSUSE](https://download.tuxfamily.org/passionlinux/captures/gimp-opensuse-28042018.png)


J'ai eu aussi une autre surprise avec la Leap, oui actuellement depuis plus ou moins une semaine, je suis sur une Leap sur toutes mes machines le portable lui est resté dessus depuis déjà un gros mois, je ne pense pas revenir à autre chose, et ma machine principale a elle aussi quitté Debian pour une Leap. Je suis toujours en manque de Debian, c'est pas évident de lâcher quelque chose qu'on connaît vraiment bien et qu'on maîtrise sur le bout des doigts, il me manquait un paquet sous Debian, et bien je le faisais moi-même, je ne compilais pas le programme non, je faisais un paquet Debian propre, je voulais un logiciel dans une version plus récente, comme un jeu par exemple, et bien je le rétro-portais depuis SID ou depuis Ubuntu sur ma Stable. Bref, je fais parti de ceux qui savent se démerder tout seul pour faire ses paquets Deb. Je ne suis pas sûr de ce que je compte faire encore, je reste 100% sur du openSUSE, c'est une possibilité et pour le moment c'est l'option que je choisi, mais dans le cas où je n'arrive pas à me passer de Debian, j'ai deux solutions. Soit je garde la openSUSE sur le portable, ce qui est pas plus mal vu que celui-ci est un peu chiant, nécessite des pilotes non libre, pour le wi-fi notamment, la openSUSE a une excellente détection du matériel et je n'ai rien à faire sauf rentrer ma clé, et pour le fixe, mon principal PC, je remet une Debian. Mais ce n'est pas top, le PC portable est rarement ouvert, la Leap est bien une fixed mais elle a beaucoup de mises-à-jour, elle bouge beaucoup, donc le portable pour le peu que je m'en sers est souvent en train de faire des updates. D'un autre coté si je garde la Leap sur le fixe et retourne sur Debian pour le portable, je n'ai pas ce soucis de mises-à-jour fréquents, par contre je me fais chier une bonne demi heure le temps de modifier le sources.list d'Apt, d'installer une interface de Iptable et d'activer ce pare-feu (Firewalld ou UFW), d'installer les drivers, le linux-nonfree et mes autres drivers, enfin mes applications. 

Bref, c'est faisable de me passer de Debian et de rester sur cette SUSE car c'est vraiment pas mal foutu, je pense notamment à Yast, qu'est ce qu'il me simplifie la vie, la gestion des services est d'une simplicité, j’active et désactive en un clic, là où sur les autres distributions comme Debian, je dois chercher le nom du service avant de savoir son "status" puis de l'activer ou non... Question sécurité aussi c'est pas plus mal, un pare-feu activé dés la fin de l’installation, c'est plutôt rare. Quand je vois Debian mais pas que, Archlinux, et en faite 90% des distributions ont bien un pare-feu, c'est Iptable, mais il est simplement non activé et la première des choses que je fais sur une Debian est d'installer une interface pour humain que je puisse comprendre les règles à transmettre, généralement UFW ou Firewalld depuis peu. Fedora est avec Mageia les seules autres distributions qui ont un module pour gérer le par-feu, activé par défaut, et pour Ubuntu de mémoire, l'interface UFW pour pare-feu est bien là mais pas activé. Bref, quand je vois les tentatives de connexions depuis des adresses venant de Chine, je suis plutôt rassuré d’être avec un tel module d'activé. 

Et puis je dois bien dire que la openSUSE ne manque pas de paquets, j'ai même plus de paquets dont je me sers que sous Debian! Je parle en émulateurs par exemple, j'ai beaucoup plus de possibilité en terme de choix pour émuler les consoles. L'autre atout et celui la est de taille, c'est OBS, quelle simplicité de participer à cette distribution, c'est encore plus simple que des petites distribution layout NuTyX ou Frugalware, et puis merde, quelle ouverture, je peux en plus de faire des paquets pour openSUSE et avoir un dépôts pour en avoir accès, faire de même pour Debian et quelques autres distributions, dont Fedora, Mageia, Archlinux,...

Mais aujourd'hui j'ai eu une surprise, j'ai eu une mise à jour de LibreOffice, je suis donc passé de la version 5.4 à un 6.0. Je suis étonné car je ne pensais pas que Leap étant une fixed allait proposer un saut de version, je pensais bêtement que comme pour le reste des applications, il fallait activer le dépôt de la dite application pour profiter de la nouvelle version. Ce que je fais dans le cas de Plasma, j'active les dépôts de Plasma pour avoir la version 5.12 actuelle. 

![Plasma 5.12 sur leap 42.3](https://download.tuxfamily.org/passionlinux/captures/leap42.3.png)

Étonné surtout puisque d'ici un bon mois, la leap 15.0 sortira, donc oui, je suis positivement et agréablement surpris de la Leap. Surpris aussi de sa robustesse, je fais des choses que je n'aimais pas faire sous Debian ou arch car celles-ci n'aimaient pas le faire, comme passer à une version supérieur d'un programme et puis retourné à sa version précédente. Pas que Debian ou Arch ne savent pas le faire, juste que c'est pas super conseillé, alors que sous openSUSE c'est quelque chose de fréquent, il suffit qu'on ait activé un dépôt, par exemple pour avoir Plasma en 5.12, puis je me décide de ne plus activer ce dépôt, et bien je repasse automatiquement par les paquets venant du dépôt principale et donc je retourne en 5.8 comme si de rien n'était. Vraiment solide ce Zypp.

Après ça reste du RPM et je ne suis pas grand fan ni de RPM ni d'autres formats de paquets autre que Deb. C'est une question d'habitude, personnelle aussi avec des mauvais souvenirs venant de Mandriva. Et puis les paquets Debian, on fait les sources sur une distribution et les paquets seront construit sur n'importe quelle distribution à base de Deb, alors que pour le RPM c'est une autre histoire, j'ai tenté à plusieurs reprises de faire des paquets à partir de SPEC venant de Fedora, j'ai dû y renoncer et partir sur des SPEC propres... Perte de temps car le travail ayant déjà été fait pour une distribution RPM, j'aurais pensé autrement, du reste si les distributions de ce layout veulent passer devant les Debian, il faudrait penser à unir les forces...

Pourquoi je veux me passer de Debian, je peux déjà dire une chose, je trouve chiant la manière de participer à Debian, c'est juste un énorme labyrinthe, bien pénible pour juste donner un coup de main, alors comme la plupart je fais mes paquets et backports dans mon coin et c'est tout... Là où sur openSUSE j'ai déjà fait 5 soumissions de mises à jour en un clic toutes acceptés. Et puis ce coté chez Debian qui m'horripile au plus haut point, ce truc que le mainteneur d'un paquet est Dieu pour lui, il a droit de vie ou de mort pour son paquet je trouve ça con... Par exemple sous Debian, pour juste proposer une mise à jour, il faut déjà en faire la demande à son mainteneur si il est disponible à nous répondre, encore pire, pour backporter un paquet, par exemple 0AD, il faudra en faire une demande par mail à son mainteneur, ainsi qu'au dernier rétroporteur, ensuite faire l'annonce sur une mailing list pour avoir le feu vert!!! Juste ridicule, 0AD n'est même pas descendu depuis sa version 0.22 dans backport, personne ne se lance, la preuve si il en est que le fonctionnement rigide de Debian est trop d'une autre époque. Sous openSUSE, rien, je regarde si le gars est à jour ou non, je fork le travail depuis le dépôt de test, je change le spec et le changelog, je laisse OBS builder (fabriquer) le paquet ou je le fais depuis chez moi localement pour ne pas charger les serveurs de openSUSE pour rien, une fois terminé et ayant le RPM sous les yeux, je propose la dite version en faisant une soumission de mon travail depuis mon home d'OBS, généralement c'est accepté dans les jours qui suivent, si non, la raison est invoqué généralement on nous demande de un changelog plus complet et respectant l'indentation, une fois les modifications faites c'est accepté... Donc avec Debian le mainteneur est Dieu pour son paquet, alors que openSUSE c'est une mentalité de celui qui fait, décide!

En passant, je remercie [Seb d'Actualia](https://www.youtube.com/user/Actualia66) pour sa [vidéo sur openSUSE](https://www.youtube.com/watch?v=d5hgBMr9YAA) , encore quelques réglages à faire pour que tout soit 100% bien pour lui et je l'invite grandement à venir nous voir sur [Alionet](https://alionet.org/)!

<iframe width="560" height="315" src="https://www.youtube.com/embed/d5hgBMr9YAA" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>