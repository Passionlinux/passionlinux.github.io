---
title: Trolls, et autres vérités préconçues autour de GNU/Linux; ma réponse 6, Debian Stable forcément obsolète?!
date: 2017-09-17 08:44
layout: post
---

![](http://download.tuxfamily.org/passionlinux//2017/09/openlogo-100.jpg){.aligncenter
.size-full .wp-image-1549 width="100" height="123"} Je survole une
demande que j'ai eu en commentaire, je ferais réellement le billet plus
tard, peut être dans la foulée de celui-ci, on verra selon notre emploi
du temps. Le commentaire en question est celui-ci:  

> Pourrais-tu faire un articles sur les différentes méthodes(backports,
> pinning, etc..) pour avoir certains logiciels à jours(navigateurs web,
> mesa, noyaux linux, etc…) sur une debian stable ? Genre, nous
> rapporter quelles difficultés on peut rencontrer(problèmes des
> bibliothèques peut être ? ou lorsqu’on met à niveau, genre debian 8 à
> debian 9, et qu’on a quelques logiciels qu’on a mis à jour soit même,
> via différentes méthodes, peut-il y avoir un problème ? quelles sont
> alors les solutions a notre disposition ? etc…). Je te dis ça car je
> ne connais pas bien debian mais apprécie sa stabilité et j’aimerais
> tout de même garder certains logiciels à jours.
> </p>

Commentaire du billet "[je me suis fait avoir par la soi-disant
complexité de
Debian](http://passiongnulinux.tuxfamily.org/2017/08/29/je-me-suis-fait-avoir-par-la-soi-disant-complexite-de-debian/)".  
<!--more-->  
Je voudrais revenir avant tout sur le titre, on entend souvent sur
Debian stable qu'elle est inutilisable car obsolète, je le dis ici, tout
ça est bidon et surtout montre à quel point les personnes disant ça ne
connaissent pas la version stable. Tout d'abord Debian se veut universel
et par la même, s'adapte à nos besoins, aux besoins de ses utilisateurs,
il ne faut pas oublier une chose: Debian est faite pour et par ses
utilisateurs... Donc en partant de ce constat ou plutôt de cette vérité
on peut se dire ceci, celui qui veut du récent se dirigera sur Sid,
celui qui veut du récent mais avec une certaine sécurité ira sur testing
(je ne suis pas vraiment d'accord mais bon...) et celui qui veut du
solide, bougeant peu, soit pour du serveur ou du desktop pro ou
simplement comme moi un truc pépère qui me laisse tranquille, ira sur du
stable. On peut vouloir du solide et du pépère, on peut aussi avoir
envie pour certaines choses à du récent, c'est mon cas pour certains
jeux ou logiciels. Je vais dans ce billet survoler les différentes
possibilités, je ne parlerais pas de la méthode pour faire une
[FrankenDebian](https://wiki.debian.org/fr/DontBreakDebian),
c'est-à-dire le
[pinning](https://debian-facile.org/doc:systeme:apt:pinning), je
parlerais seulement des méthodes totalement indolores que sont le
rétro-portage et les dépôts officieusement officiels. Pour commencer je
parle de mon navigateur adoré, celui qui me suit depuis ses versions
Phenix, depuis qu'il fut le remplaçant de mon regretté Mozilla, comme
vous le savez Debian dans sa version stable (je ne parle que de sa
version stable ici, donc quand je dirais Debian, il faudra se dire
stable), préfère la sécurité et prends du coup la ESR qu'elle met à
jours. Pour ceux à qui cela ne suffit pas, on peut se tourner vers les
dépôts officieux de la [team Mozilla chez
Debian.](http://mozilla.debian.net/) En fait après vérification, les
dépôts n'existent plus d’après [cette
page](https://debian-facile.org/doc:systeme:apt:sources.list:depots-tiers#mozilla-firefox)
(partie Mozilla), on peut y lire:  

> Il n'existe plus de dépôt tiers mozilla pour installer la dernière
> version de Firefox. Les utilisateurs de unstable peuvent installer
> Firefox release. Les utilisateurs de Stretch (stable) et Buster
> (testing) peuvent l'installer en modifiant les priorités
> d'installation des paquets
> [pinning](https://debian-facile.org/doc:systeme:apt:pinning "doc:systeme:apt:pinning"){.wikilink1}.
> </p>

Il reste donc la méthode simple que j’emploie depuis des lustres, celle
qui consiste à télécharger le binaire sur le [site de
Mozilla](https://www.mozilla.org/fr/firefox/new/?scene=2), de le
décompresser dans mon cas pour que cette version soit uniquement
disponible pour mon utilisateur, dans un dossier */binaire* de mon
*/home* et de faire un raccourci du fichier Firefox-bin pour le menu ou
le bureau (Xfce/KDE). Si on veut que cela soit disponible à l'ensemble
des utilisateurs, on pourra le mettre avec les bons droits (par exemple
groupe famille) dans le dossier */opt* de la racine (*/*). Pour
Thunderbird et Seamonkey, on se contentera de faire pareil. Il y a un
dépôt peu conseillé car il met un peu le bordel dans nos paquets, c'est
le [deb-multimedia](http://www.deb-multimedia.org/), dépôt semi-officiel
puisque c'est un développeur Debian (Christian Marillat) qui le
maintient pour des questions de licences non compatible avec Debian.
Dépôt qui portait le nom de debian-multimedia mais qui pour [une raison
a dû changer de
nom](https://lists.alioth.debian.org/pipermail/pkg-multimedia-maintainers/2012-May/026678.html)
pour éviter les quiproquos. On y trouve comme son nom l'indique, tout
paquet qui a un rapport avec le multimédia. Quand je dis "met le
bordel..." c'est ce que j'entends ici et là, car chez moi jamais eu de
soucis, c'est plutôt que les gars allaient se plaindre d'un bug des
paquets venant de chez C.Marillat(deb-multimedia) directement dans le
BTS de Debian. Il y a aussi le fait que les paquets venant de
deb-multimedia font doublons pour certains avec ceux de Debian. Mais
bon, en regardant le lien donné plus haut sur le pourquoi du changement
de nom, on comprend l'histoire. Pour l'utiliser, on ajoute les lignes
suivantes dans son
[sources.list](https://debian-facile.org/doc:systeme:apt:sources.list):
**deb http://www.deb-multimedia.org stretch main non-free** ou **deb
ftp://ftp.deb-multimedia.org stretch main non-free** ou **deb
http://www.deb-multimedia.org stable main non-free** ou **deb
ftp://ftp.deb-multimedia.org stable main non-free** Puis

    apt update && apt-get --allow-unauthenticated install deb-multimedia-keyring

On vérifie l'intégrité avec:

    sha256sum deb-multimedia-keyring_2016.8.1_all.deb 9faa6f6cba80aeb69c9bac139b74a3d61596d4486e2458c2c65efe9e21ff3c7d deb-multimedia-keyring_2016.8.1_all.deb

On aura ensuite le plaisir d'avoir Avidemux ou DVDrip. Comme je l'ai
souvent dit ici sur [ce
blog](http://passiongnulinux.tuxfamily.org/2016/07/10/20160710ce-que-je-fais-apres-linstallation-de-ma-debian/),
j'utilise
[Backports](http://passiongnulinux.tuxfamily.org/2016/06/03/20160603les-retroportages-depot-backports/),
ce qui me permet par exemple d'avoir un Wine plus récent, Virtualbox
plus récent (le cas pour Jessie), 0ad ou Minetest dans leurs dernières
versions, on peut y trouver un kernel ou un LibreOffice plus récent...
Pour ce faire, rien de bien compliqué, on rajoute les Backports:

    # Debian Stretch, dépôt de rétroportages ("backports") deb http://ftp.fr.debian.org/debian stretch-backports main contrib non-free

puis

    apt update

Ensuite on installe un logiciel venant des Backports par un:

    apt-get -t stretch-backports install 0ad minetest wine32

<div class="texte surlignable">

Par la suite, les paquets installés depuis les <span
class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="backports">backports</span> se mettront automatiquement
à jour comme pour les paquets issus de la branche principale, seule la
mise-à-jour initiale vers la version <span class="scayt-misspell-word"
data-scayt-lang="fr_FR" data-scayt-word="rétroportée">rétroportée</span>
nécessite cette déclaration explicite de la branche. Ce système est en
place pour éviter que tous les paquets proposant une version candidate
dans les <span class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="backports">backports</span> soient automatiquement
mis-à-jour dans cette version, ce qui n’est généralement pas le
comportement souhaité par l’utilisateur. Vous pourrez en apprendre plus
sur le fonctionnement de ce système (et sur les possibilités de modifier
ce comportement) dans l’article du <span class="scayt-misspell-word"
data-scayt-lang="fr_FR" data-scayt-word="wiki">wiki</span> dédié aux
priorités et aux [fichiers apt\_<span class="scayt-misspell-word"
data-scayt-lang="fr_FR"
data-scayt-word="preferences">preferences</span>](https://debian-facile.org/doc:systeme:apt:pinning "doc:systeme:apt:pinning"){.wikilink1}.
<div>

La forme **-t <span class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="backports">backports</span>** installe sans problème
les dépendances dans leur version **stretch-backports**. la forme
*nom\_paquet/<span class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="jessie-backports">stretch-backports</span>* pose des
problèmes de dépendances <span class="scayt-misspell-word"
data-scayt-lang="fr_FR" data-scayt-word="parce">parce</span> que la
version prioritaire des dépendances n’est plus celle des <span
class="scayt-misspell-word" data-scayt-lang="fr_FR"
data-scayt-word="backports">backports</span> mais celle des autres
sources déclarées.

</div>

</div>

Voir en ligne :
[Debian-facile](http://passiongnulinux.tuxfamily.org/spip/debian-facile.org/doc:systeme:apt:sources.list#les_depots_debian_officiels){.spip_out}

Dans le dernier cas, ceux qui souhaitent assumer plus de risques et de
responsabilités peuvent parfois faire leurs propres rétroportages
(backports) de la dernière version de logiciels Debian. Bien que non
dénué de risques, l'auto-rétroportage est généralement plus sûr que
d'autres approches. Lorsque l'auto-rétroportage échoue, il est probable
que toute autre approche va briser votre système ((avec *make install*
ou un script d'installation, par exemple). <span id="line-105"
class="anchor"></span><span id="line-106" class="anchor"></span>

-   [fr/SimpleBackportCreation](https://wiki.debian.org/fr/SimpleBackportCreation)
    <span id="line-107" class="anchor"></span>

-   [Instructions
    alternatives](http://ircbots.debian.net/factoids/factoid.php?key=simple+sid+backport){.http}
    (en anglais) sont disponibles à partir du [robot IRC de
    Debian](https://wiki.debian.org/IRC/DpkgBot). <span id="line-108"
    class="anchor"></span>

-   Également sur IRC, le robot *judd* fournit la commande
    [checkbackport](http://ircbots.debian.net/judd/#judd-builddep){.http}
    qui offre des indications pour savoir si le rétroportage est
    possible, en interrogeant le
    [UltimateDebianDatabase](https://wiki.debian.org/UltimateDebianDatabase).

J'en ai parlé
[ici](http://passiongnulinux.tuxfamily.org/2016/06/03/20160603creation-de-paquets-deb-methode2-devscripts/)
, il est question que je fasse un billet plus propre et complet que le
précédent. 1/ Pour commencer, nous faisons un dossier avec le nom du
paquet, par exemple pour playonlinux:
`$ mkdir /home/sebastien/packaging/playonlinux $ cd /home/sebastien/packaging/playonlinux`
2/ On télécharge les sources debian du paquet:
`$ apt-get source playonlinux` 3/ On télécharge en ROOT, les paquets
nécessaires pour construire ce paquet: `# apt-get build-dep playonlinux`
4/ On se remet en simple utilisateur, puis on rentre dans le dossier des
sources debian:
`$ cd '/home/sebastien/packaging/playonlinux/playonlinux-4.2.6'` 5/ On
va dans voir le fichier /debian/watch qui permet, si bien fait, de faire
tout automatiquement avec la commande uscan. Les sources mises à jour
seront automatiquement recherchées, téléchargées, et la commande uupdate
sera exécutée. `$ uscan` Si la commande uscan télécharge les sources
mises à jour mais n’exécute pas la commande uupdate, vous devriez
corriger le fichier debian/watch pour avoir debian uupdate après l’URL.
6/ Normalement tout a été fait si le fichier watch est bien fait, du
coup reste plus qu’à fabriquer le deb:
`$ cd '/home/sebastien/packaging/playonlinux/playonlinux-4.2.8' $ debuild`
On aura de jolis paquets deb, et pour finir un coup de `debuild clean`.
Voila les différentes approches que j'utilise pour profiter de ma Stable
avec quelques paquets plus récents.
