---
title: Ce que je fais après l'installation de ma Debian
date: 2016-07-10
layout: post
---

J'aime bien lire les blogs de mes compatriotes, généralement je lis
surtout ce qui touche a linux et le logiciel libre. Je voulais faire ce
billet depuis quelque temps, en faite depuis que [Gilles a posté le sien
sur son
blog](http://www.parigotmanchot.fr/2016/06/07/apres-installation-ubuntu-16-04-lts/).
Il commence par:  

> Comme souvent en ce moment, j’ai installé la dernière version d’Ubuntu
> : la 16.04 LTS (Long Term Support), appelée Xenial Xerus. Comme ma
> dernière liste d’installation date un peu et que j’ai changé
> d’ordinateur, je remets ici pour mémoire ce que j’ai fait après
> l’installation de base.
> </p>

Alors avec debian je n'ai pas autant de raison de réinstaller, en effet
les sorties d'une stable c'est tout les deux ans alors qu'ubuntu c'est
tout les 6mois, a part si on installe que les LTS d'ubuntu et la ça
revient au même qu'une debian. Bref, ça n’empêche pas que le temps fait
que j’oublie certaine pratique, que je dois ensuite regarder sur ce blog
pour trouver les différents penses bête et ensuite les mettre en
pratique. Il est peut être temps que je récapitule dans un seul billet
les principales actions que je fais a chaque nouvelle debian. Pour
l'installation, je ne change pas, je prend normalement une
[net-install](https://www.debian.org/distrib/netinst#smallcd) ou un [DVD
d'installation](https://www.debian.org/CD/torrent-cd/) si je sais que je
dois en installer plusieurs. Normalement je ne prend que le Amd64 mais
j'ai encore deux vieux coucous en i386. Ensuite je [lance
l'installation](http://passiongnulinux.tuxfamily.org/?p=53), je suis les
étapes que je connais par cœur depuis le temps. C'est simple, rapide et
comme Debian nous habitue a ne pas changer pour changer, on est pas
surpris par cette installation.  
<!--more-->  
Au premier démarrage, je change le fichier /etc/apt/source.list avec
[nano](https://fr.wikipedia.org/wiki/GNU_nano) pour rajouter les dépots
nonfree et contrib ainsi que les depots sources de sid, puis surtout je
retire (je commente \#) la ligne du cd/dvd..
`# nano /etc/apt/sources.list` Le fichier d'origine:

    deb cdrom:[Debian GNU/Linux etc... # Debian Jessie, dépôt principal deb http://httpredir.debian.org/debian/ jessie main # Debian Jessie, mises-à-jour de sécurité deb http://security.debian.org/ jessie/updates main # Debian Jessie, mises-à-jour "volatiles" deb http://httpredir.debian.org/debian/ jessie-updates main

après:

    # Debian Jessie, dépôt principal + paquets non libres deb http://httpredir.debian.org/debian/ jessie main contrib non-free # Debian Jessie, mises-à-jour de sécurité + paquets non libres deb http://security.debian.org/ jessie/updates main contrib non-free # Debian Jessie, mises-à-jour "volatiles" + paquets non libres deb http://httpredir.debian.org/debian/ jessie-updates main contrib non-free

je rajoute aussi les *backports*:

    # Debian Jessie, dépôt de rétroportages ("backports") deb http://httpredir.debian.org/debian jessie-backports main contrib non-free

Voir le [billet qui en
parle](http://passiongnulinux.tuxfamily.org/?p=17). J'y reviendrais
dessus car par la suite j'installe deux ou trois paquets venant de
backports. Une fois fait, il faut a tout pris lancer une mise a jour des
dépôts (ils ont changé du coup faut que notre système en soit informé):
`# apt-get update` Suivit d'une mise a jour du système:
`# apt-get upgrade` Bien que dans mon cas j'utilise a tout va
`# apt-get dist-upgrade` Noter qu'on peut tout a fait raccorder les deux
commandes en une seule a condition de mettre entre elle un *&&*:
`# apt-get update && apt-get dist-upgrade` Je fini par accepter les
mises a jour. Une fois cette étape fini, ce n'est que la première, je
rajoute les firmwares non-libre qui me sont obligatoire pour profiter de
mes deux écrans: `# apt-get install firmware-linux-nonfree` Je rajout
aussi un firmware pour mon Ethernet, ce n'est pas obligatoire mais a
chaque mise a jour du kernel j'ai des messages qui me le demande, je
l'installe surtout car j'ai aussi le wifi sur un autre pc qui fonctionne
avec ce driver...: `# apt-get install firmware-realtek` Pour le reste
des firmwares, on peut aller par
[la](http://passiongnulinux.tuxfamily.org/?p=22). Une bonne chose de
faite, je me retrouve en face de mes deux écrans qui me donnent chacun
une bonne résolution. Maintenant, on va s'attaquer au mutiarch, plus
haut j'ai dis que mon pc est en 64, or pour certaines applications comme
wine, il nous faut les libs de i368. Pour ce faire, c'est très simple,
on rajoute a notre système, l'architecture i386, on peut bien sur
ajouter n'importe quelle architecture disponible sous Debian.
`# dpkg --add-architecture i386 && apt-get update` Pour en savoir plus,
c'est par [la](http://passiongnulinux.tuxfamily.org/?p=23). Allez, le
plus gros est passé, maintenant il reste a installer les paquets. Je
commence par installer apt-listbugs, qui sert a prévenir des bugs ou
failles éventuels, des fois je l'installe avant tout chose dès le début,
et parfois seulement après avoir effectué les actions vu précédemment.
`# apt-get install mc apt-listbugs devscripts mldonkey-server kde-full icedove-l10n-fr icedove filezilla`
Alors dans l'ordre,

-   [**mc**](https://fr.wikipedia.org/wiki/Midnight_Commander) est un
    couteau suisse, il fait gestionnaire de fichier, éditeur et plein
    d'autre chose, c'est un utilitaire qui nous permet d'éviter de
    saisir les commandes dans une console.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/e/eb/Midnight_Commander_4.6.1_menu.png/280px-Midnight_Commander_4.6.1_menu.png)

-   [**Devscripts**](https://packages.debian.org/jessie/devscripts) est
    un ensemble de scripts pour faciliter la vie du mainteneur Debian,
    je m'en sers principalement pour me faire des paquets plus récent.
-   [**mldonkey-server**](https://fr.wikipedia.org/wiki/MLDonkey) est
    une application destinée au partage de fichiers en pair à pair
    multiréseaux et libre. Elle fonctionne comme application backend sur
    de nombreuses plates-formes. Elle peut être contrôlée au moyen d'une
    interface utilisateur fournie par un des nombreux frontaux séparés,
    y compris une interface Web, l'interface Telnet et plus d'une
    douzaine de logiciels clients natifs.

![Interface graphique de MLDonkey
2.9.5.](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/Mldonkey.jpg/1280px-Mldonkey.jpg){.mw-mmv-final-image
.jpg .mw-mmv-dialog-is-open width="1207" height="556"}

-   [**kde-full**](https://packages.debian.org/jessie/kde-full) est
    l'ensemble des logiciel contenu dans kde.
-   [**icedove**](https://fr.wikipedia.org/wiki/Renommage_des_applications_de_Mozilla_par_Debian)
    est la version Debian de
    [**Thunderbird**](https://fr.wikipedia.org/wiki/Mozilla_Thunderbird)
    et icedove-l10n-fr est la traduction FR.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/Mozilla_Thunderbird_31.4.0.png/1024px-Mozilla_Thunderbird_31.4.0.png){.transparent}

-   **[FileZilla](https://fr.wikipedia.org/wiki/FileZilla)** est un
    [client](https://fr.wikipedia.org/wiki/Client-serveur "Client-serveur")
    [FTP](https://fr.wikipedia.org/wiki/File_Transfer_Protocol "File Transfer Protocol"),
    [FTPS](https://fr.wikipedia.org/wiki/File_Transfer_Protocol_over_SSL "File Transfer Protocol over SSL"){.mw-redirect}
    et
    [SFTP](https://fr.wikipedia.org/wiki/SSH_file_transfer_protocol "SSH file transfer protocol"){.mw-redirect},
    développé sous la [licence publique générale
    GNU](https://fr.wikipedia.org/wiki/Licence_publique_g%C3%A9n%C3%A9rale_GNU "Licence publique générale GNU").
    Il existe également un logiciel de
    [serveur](https://fr.wikipedia.org/wiki/Client-serveur "Client-serveur")
    FTP du nom de [FileZilla
    Server](https://fr.wikipedia.org/wiki/FileZilla_Server "FileZilla Server").
    Le logiciel est disponible pour Windows, Mac OS X et Linux.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2a/FileZilla-3.0-fr.png/800px-FileZilla-3.0-fr.png){.shrinkToFit
.transparent width="749" height="642"}

Ensuite, je rajoute mes applications venant de backport, bien sur ils
sont aussi dans les dépôts standard mais dans une version un peu
vieillotte...
`# apt-get -t jessie-backports install 0ad minetest wine32`

-   [**0ad** - Empires Ascendant](https://fr.wikipedia.org/wiki/0_A.D.)
    est un jeu vidéo de stratégie en temps réel (RTS) historique en 3D
    développé et édité par Wildfire Games.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3e/0_A.D._Seleucide.jpg/1024px-0_A.D._Seleucide.jpg)

-   [**Minetest**](http://www.minetest.net/) est aussi un jeu, cette
    fois de layout bac à sable en multijoueur, le jeu propose au joueur
    d'incarner un personnage se mouvant dans un univers en trois
    dimensions, représenté par des cubes, la représentation du décor
    utilisant le principe des voxels. Il est possible de récupérer des
    ressources en creusant dans ces cubes, et de créer de nouveaux blocs
    avec les ressources ainsi accumulées.

![](http://www.minetest.net/media/gallery/1.jpg)

-   [**wine**](https://fr.wikipedia.org/wiki/Wine) est un une
    implémentation libre de l'interface de programmation Windows bâtie
    sur X et UNIX (BSD, Linux), c’est-à-dire qu'il permet d'utiliser sur
    Linux ou Mac OS X des programmes conçus pour fonctionner
    sous Windows. Le logiciel n'a donc pas besoin du système
    d'exploitation Windows pour fonctionner.

Je suis bientôt a la fin, on va récapituler notre installation:

-   Installer un *client FTP* : **filezilla**
-   Installer un *logiciel de messagerie instantanée* : **kopete,
    konversation** contenu dans le paquet ***kde-full***
-   Installer un *logiciel de téléchargement torrent* : **ktorrent**
    contenu dans le paquet ***kde-full***
-   Installer *un navigateur alternatif* à Firefox : **konqueror**
-   Installer le support des archives compressées au format *7z* :
    **p7zip-full**
-   Installer *mes jeux favoris :* **0ad** *et* **Minetest**

J'étofferais petit a petit les paquets car d'autres me viennent en tête.
