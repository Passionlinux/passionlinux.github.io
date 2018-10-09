---
title: Trolls, et autres vérités préconçues autour de GNU/Linux; ma réponse #2 KDE
date: 2017-03-17 18:32
Author: schavaux
layout: post
---

J'ai voulu couper ma réponse pour ne pas en faire un billet fleuve ou à
rallonge. Après avoir dis ma façon de voir les choses sur le rolling et
les distributions dites fixes, je parlerais des problèmes de KDE
rencontrés. Là, je vais me baser sur ce qui est dit par Adrien.D, que je
salue au passage, je le cite:  
<!--more-->

> KDE est un bon environnement de bureau, mais il y a quelques points
> qui m'agacent. 1 - Le chargement interminable de l'environnement de
> bureau. Sur SSD, une fois l'environnement chargé, et le conky lancé,
> je constate un "uptime" de 27 secondes. C'est beaucoup trop long pour
> un démarrage avec un SSD. Avec MATE, je note 10 secondes, sachant que
> je ne possède pas une connexion automatique, je saisis mon mot de
> passe à la main. Cela me rappelle quand j'avais fait un saut sous
> fedora Cinnamon qui avait un uptime de 7 secondes au démarrage. Si
> j'utilise un SSD, c'est pas pour, entre le temps où j'allume la
> machine et le temps où c'est chargé, faire 3 fois le tour du quartier.
> 2 - La gestion médiocre de l'USB et notamment MTP. En effet, il est
> impossible de transférer de manière correcte sur un téléphone Android
> via USB des photos, vidéos, musique, sans avoir un message du style
> "KIO s'est arrêté de manière inattendue". Alors, j'avais trouvé 2
> alternatives : Caja + GVFS sous KDE (mais c'est bof), et KDE Connect.
> KDE Connect offre pas mal d'avantages, mais malheureusement, on doit
> disposer d'une connexion Wi-Fi pour transférer ses données (Wi-Fi qui
> n'est pas activé chez moi, donc je l'avais relancé pour l'occasion).
> Le Wi-Fi par définition n'est pas sécurisé. Une clé est cassable en
> très peu de temps, et puis, moins il y a d'ondes dans la maison, mieux
> on se porte. La lecture d'une image sur le téléphone (ou un partage
> samba) avec KIO, ça fonctionne en 2 temps : téléchargement du fichier,
> puis lancement du fichier. Sous MATE (ou Cinnamon ou GNOME), avec
> gvfs, il sait "streammer" et donc lit en direct. Après, il y a
> d'autres points que je n'aborderai pas sur les dysfonctionnements, car
> ils sont vraiment mineurs, comme le non lancement de l'applet du son
> (1 fois sur 10), qui entraîne un non fonctionnement des touches
> multimédia, ...

Je vais dire ce que j'en pense, car oui je pense que la plupart des
soucis est dû a sa distribution. Le chargement de kde après le login
dans SDDM est long, ça c'est sur et c'est aussi un des trucs qui me
fatigue. Alors perso je m'en fous puisque mon PC reste ouvert par contre
sur le portable que je ferme souvent c'est lourd, pareil chez mes
parents où mon père me la reproché. Peu importe la distribution c'est
partout, il n'y a pas d'amélioration pour le moment, après ça dure sur
un HDD une vingtaine de secondes... Pour le soucis de MTP, je dois dire
que je pense fortement a un soucis de distribution, je n'ai jamais eu ce
message sur openSUSE, par contre j'ai d'autre soucis comme devoir
vérifier au cours d'une copie si mon téléphone est bien et reste
déverrouillé, sinon la copie échoue. Mais c'est le cas aussi sur Mate,
Gnome, Unity et Xfce... Pour KDE Connect, j'ai entendu qu'il y avait un
bug qui faisait que les fichiers copiés du PC vers le Téléphone étaient
mis sur la mémoire interne du téléphone et non sur la carde SD, je dois
encore dire que je n'ai pas eu ce soucis puisque j'ai copié 6 go de
données vers mon téléphone et que ça s'est bien mis dans la carte SD, de
toute façon il n'y avait pas trop le choix étant donné que mon téléphone
ne possédait que 2 GO mémoire disque... Du reste le dossier KDE-Connect
a été fait directement dans la SD carte et nullement dans la mémoire du
téléphone. En faite, il faut aller dans les options de KDE Connect et
cocher "Customize destination directory", puis cliquer sur "destination
directory" et lui dire de mettre dans la carte SD. Ce qui est fait, je
pense sur openSUSE et Debian puisque je n'ai rien eu a faire et j'ai
même un sous dossier avec le nom de la machine qui m'a envoyé le
fichier... Par contre, j'ai bien le soucis des images sur le téléphone,
impossible de les visualiser a partir du téléphone ou d'un appareil
photo sans les avoir rapatrié sur le PC. Chose que je n'ai pas sur Xfce,
Unity, Mate et Gnome. Pour ce qui est du non lancement du son, 1 fois
sur 10, je dois dire que je n'ai vu ça que sur Calculate linux, du reste
c'est Kmix qui doit être lancé alors que sur openSUSE c'est bien un
applet de son. Mais j'ai remarqué d'autre soucis venant de cette
distribution que je n'ai pas sur openSUSE, tout d'abord dans Gwenview,
les modules externes sont vide par défaut, il faut utiliser le flags
"kipi : Support for the KDE Image Plugin Interface" pour les avoir, ce
n'est pas un soucis c'est juste une manière de faire par contre
impossible de changer la qualité d'impression dans les logiciels KDE
quand on veut imprimer, et ça c'est seulement sur Calculate que j'ai ça.
Alors j'ai pesté au début sur Plasma5, puis j'ai vu que openSUSE
permettait de changer la qualité d'impression, j'ai alors regardé dans
Calculate au même emplacement et il manque bien l'option...
![](http://download.tuxfamily.org/passionlinux//2017/03/Screenshot_20170317_171201.png){.aligncenter
.size-full .wp-image-1139 width="524" height="545"}
![](http://download.tuxfamily.org/passionlinux//2017/03/Screenshot_20170317_171214.png){.aligncenter
.size-large .wp-image-1140 width="524" height="545"}
![](http://download.tuxfamily.org/passionlinux//2017/03/Screenshot_20170317_171225.png){.aligncenter
.size-large .wp-image-1141 width="524" height="545"}
![](http://download.tuxfamily.org/passionlinux//2017/03/Screenshot_20170317_171235.png){.aligncenter
.size-large .wp-image-1142 width="499" height="723"}
![](http://download.tuxfamily.org/passionlinux//2017/03/Screenshot_20170317_171249.png){.aligncenter
.size-large .wp-image-1143 width="499" height="723"} Je pense donc que
c'est belle et bien sa distribution qui merde quelque part, un peu comme
son soucis avec [Mate et
SDDM](https://www.youtube.com/watch?v=gUJSSCYSpAs), il a résolu en
[remplaçant SDDM par
Ligthdm](https://www.youtube.com/watch?v=wy-hjTZ4Iek), mais encore une
fois, je n'ai pas de soucis sur ma machine avec SDDM d'openSUSE et Mate
ou sur Debian. Voila pour ma deuxième partie de réponse.
