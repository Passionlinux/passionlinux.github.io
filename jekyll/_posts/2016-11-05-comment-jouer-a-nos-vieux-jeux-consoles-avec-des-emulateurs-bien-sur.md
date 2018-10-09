---
title: Comment jouer à nos vieux jeux consoles? Avec des émulateurs bien sur!
date: 2016-11-05 00:59
layout: post
---

Cela fait un petit moment que je n’écris pas autant que je le voudrais,
je fais a peine un billet par semaine, on est loin de ce que je voulais
a un moment donné, mais bon c'est comme tout et ça ira mieux par la
suite. Aujourd'hui je parlerais d'émulateurs de consoles, plutôt
ancienne comme la NES, la SNES, la Megadrive, et bien d'autre mais pas
de PSONE et autre assez récente, pour la simple raison que ces consoles
demandent pas mal de bidouilles... Je fais ce billet pour notre ami
[**bruno-legrand**](http://passiongnulinux.tuxfamily.org/2016/07/30/si-on-parlait-de-jeux-2-alien-isolation/#comment-252),
en espérant ne pas trop être approximatif. Je sais pas trop comment
tourner ce billet, je ne suis pas a l'aise. Je pense que si on veut
trouver de quoi faire, il faut aller sur la documentation d'Ubuntu,
c'est peut être la seule qui est vraiment complète et de qualité, peut
être une des raisons que j'ai a vouloir toujours revenir a cette
distribution. Donc je me base sur la page
[emulateurs\_console](http://doc.ubuntu-fr.org/emulateurs_console)pour
écrire ce billet.  
<!--more-->

###### Amstrad CPC:

Je commencerais par ma première console ou du moins la plus vieille,
c'est mon petit [Amstrad
CPC](https://fr.wikipedia.org/wiki/Amstrad_CPC),![amstrad\_cpc\_6128](http://download.tuxfamily.org/passionlinux//Amstrad_CPC_6128-300x227.png){.size-medium
.wp-image-787 .aligncenter width="300" height="227"} a cette époque, il
y en avait de superbes jeux très prenant et qui tenaient sur une petite
disquette, je pense a [FRUITY
FRANK:](http://www.amstradabandonware.com/fr/jeuitems/fruity-frank/4372)
![fruity](http://download.tuxfamily.org/passionlinux//fruity-300x213.png){.size-medium
.wp-image-788 .aligncenter width="300" height="213"} ou a [Bomb
Jack](http://www.cpc-power.com/index.php?page=detail&num=448 "Voir la fiche"):
![bombjack](http://download.tuxfamily.org/passionlinux//bombjack-300x213.png){.size-medium
.wp-image-789 .aligncenter width="300" height="213"} ou a
[Saboteur:](http://www.cpc-power.com/index.php?page=detail&num=1858)
![saboteur](http://download.tuxfamily.org/passionlinux//saboteur-300x213.png){.size-medium
.wp-image-790 .aligncenter width="300" height="213"} Bref, il y a des
hits a la pelle, comme mon petit préféré
[Barbarian:](http://www.cpc-power.com/index.php?page=detail&num=40)
![barbarian](http://download.tuxfamily.org/passionlinux//barbarian-300x213.png){.size-medium
.wp-image-791 .aligncenter width="300" height="213"} Pour y jouer, rien
de très compliqué, on utilise le programme
[Arnold,](https://doc.ubuntu-fr.org/amstrad) c'est un émulateur  de CPC.
Selon votre [architecture
matérielle](https://doc.ubuntu-fr.org/architecture_materielle "architecture_materielle"){.wikilink1}
(32 ou 64 bits), téléchargez l'archive
**arnold-nurgle-x86-2009-03-17.tar.bz2** ou
**arnold-nurgle-x86\_64-2009-03-17.tar.bz2** sur [cette
page](http://sourceforge.net/projects/arnold.berlios/files/ "http://sourceforge.net/projects/arnold.berlios/files/"){.urlextern}
\[SourceForge\].

<div class="level4">

[Décompressez](https://doc.ubuntu-fr.org/archivage "archivage"){.wikilink1}
l'archive et double-cliquez sur l'exécutable **arnold** pour lancer
l'émulateur.

</div>

Le lancement d'Arnold ouvre deux fenêtres : la fenêtre d'émulation
proprement dite et un panel permettant de configurer l'émulateur.

<div class="level4">

Dans la boîte de configuration, vous pouvez choisir l'Amstrad à émuler,
agrandir la fenêtre de l'émulateur (double display), activer un
joystick, choisir votre clavier (azerty, qwerty). Ces configurations ne
sont pas enregistrées et doivent être refaites à chaque lancement de
l'émulateur. Pour charger un jeu, cliquez sur "Drive A" ou "Tape". Si le
jeu comporte deux disquettes, vous pouvez utiliser "Drive B". Tapez
"cat" dans la fenêtre de l'émulateur pour savoir quel fichier lancer,
puis lancez la commande RUN", par exemple : RUN"DISC.
-   <div class="li">

    F1 : Relance la fenêtre d'émulation (pour quitter un jeu sans
    fermer l'émulateur).

    </div>

-   <div class="li">

    F2 : Passer en mode plein écran ou en sortir.

    </div>

-   <div class="li">

    F3 : Basculer entre l'environnement Linux et
    l'environnement Amstrad.

    </div>

-   <div class="li">

    F4 : Quitter l'émulateur.

    </div>

-   <div class="li">

    F5 : Active ou désactive le joystick.

    </div>

Le CPC n’était pas une console mais un ordinateur souvent utilisé pour
jouer. D'autres émulateur existent mais je ne les ai pas testé ni
utilisé. Un paquet RPM existe pour openSUSE dans le dépôt émulateur. On
peut récupérer des jeux sur des sites comme:
http://www.cpc-power.com/index.php?page=accueil
http://www.gametronik.com/site
http://www.amstradabandonware.com/en/home  

###### NES ou Nintendo:

![nes](http://download.tuxfamily.org/passionlinux//nes-300x209.jpg){.size-medium
.wp-image-792 .aligncenter width="300" height="209"} Et oui, qui n'a pas
connu la NES, cette console mythique, solide et fonctionnelle encore de
nos jours? Pour y jouer, on a le choix entre plusieurs émulateurs, je ne
citerais que 2, [Nestiopa](http://nestopia.sourceforge.net/) et
[FCEUX,](https://doc.ubuntu-fr.org/fceultra) mais d'autres sont listé
sur Ubuntu. Les deux sont facilement disponible sur n'importe quelle
distribution, dont Debian/Ubuntu, openSUSE ou Mageia. De mémoire il y a
aussi [Higan](https://byuu.org/emulation/higan/) comme émulateur qui
permet de faire tourner plusieurs consoles de jeu de la marque
[Nintendo](https://fr.wikipedia.org/wiki/Nintendo "Nintendo"), notamment
la [NES](https://fr.wikipedia.org/wiki/NES "NES"){.mw-redirect}, la
[Super
Nintendo](https://fr.wikipedia.org/wiki/Super_Nintendo "Super Nintendo"),
le [Game Boy](https://fr.wikipedia.org/wiki/Game_Boy "Game Boy"), le
[Game Boy
Color](https://fr.wikipedia.org/wiki/Game_Boy_Color "Game Boy Color"),
et la [Game Boy
Advance.](https://fr.wikipedia.org/wiki/Game_Boy_Advance "Game Boy Advance")  

###### SNES ou Super Nintendo:

![snes](http://download.tuxfamily.org/passionlinux//snes-300x252.png){.size-medium
.wp-image-793 .aligncenter width="300" height="252"} Pour cette console,
j'utilise Higan cité plus haut ou
[ZSNES.](http://doc.ubuntu-fr.org/zsnes "zsnes"){.wikilink1}  

###### Game Boy, Game Boy Color, Game Boy Advance:

J'utilise exclusivement
[Gnuboy](http://doc.ubuntu-fr.org/gnuboy "gnuboy"){.wikilink1} ou Higan,
toujours dans les dépôts de Debian et openSUSE.  

###### Nintendo 64: {#nintendo_64 .sectionedit20}

![n64](http://download.tuxfamily.org/passionlinux//n64-300x210.jpg){.size-medium
.wp-image-794 .aligncenter width="300" height="210"} Pour la N64, je
fais confiance a
[mupen64plus](http://doc.ubuntu-fr.org/mupen64 "mupen64"){.wikilink1},
c'est pas compliqué mais faut déjà avoir un pc qui tourne assez bien.  

###### Sega Mega Drive/Genesis, Mega-CD, 32X {#sega_mega_drivegenesis_mega-cd_32x .sectionedit27}

![megadrive](http://download.tuxfamily.org/passionlinux//megadrive-300x154.jpg){.size-medium
.wp-image-795 .aligncenter width="300" height="154"} D’après la
documentation d'Ubuntu, en 2015, l'état de l'émulation de la Mega Drive
est assez décevant. Gens et surtout Fusion sont de bons émulateurs, mais
leur développement est maintenant abandonné. Des mises à jour et des
améliorations ne seraient pas superflues, même si Fusion notamment reste
très bon. On peut noter qu'une version [Gens/GS II est en cours de
développement.](http://www.dusers.drexel.edu/gitweb/gitweb.cgi/%7Ekorth/gens-gs-ii.git "http://www.dusers.drexel.edu/gitweb/gitweb.cgi/~korth/gens-gs-ii.git"){.urlextern}
J'utilise les deux émulateurs suivant:

-   <div class="li">

    [Gens-GS](http://doc.ubuntu-fr.org/gens-gs "gens-gs"){.wikilink1} :
    version modifiée de Gens ; configuration facile de l'affichage, du
    joystick, etc. Fonctionne bien. Site officiel :
    <http://segaretro.org/Gens/GS>

    </div>

-   [dgen](http://doc.ubuntu-fr.org/dgen "dgen"){.wikilink1} (ligne
    de commande)

Pour télécharger des jeux, pardon ROMS, je vais surtout sur ce site,
http://www.planetemu.net/ qui contient une quantité de jeux testés. Je
sais toujours pas si ce billet va servir puisque de mon point de vue, je
n'ai fais que copier des noms d'émulateurs pour des consoles, je pense
que cela aurait été plus constructif de voir les installations de chaque
émulateur et leurs configurations, mais tous sont faciles et intuitifs.
 

</div>
