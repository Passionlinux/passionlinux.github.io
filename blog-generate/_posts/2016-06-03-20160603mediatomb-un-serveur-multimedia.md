---
title: Mediatomb, un serveur multimedia.
date: 2016-06-03 10:15
layout: post
---

<div class="main">

<div class="chapo surlignable">

Nous avons tous de superbes TV a ecran plat avec des tonnes de fonctions
integrées et des ordinateurs a recycler. Du coup ce qui va suivre va
certainement vous interesser ! Qui n’a jamais eu la flemme de se lever
pour changer de dvd ? Qui n’a jamais dit « il n’y a rien ce soir a la
télé » ? Et qui n’a jamais dit a quoi bon payer la redevance télé ?
Maintenant imaginez un peu ce qui suit(tiré de fait réél), vous etes
chez vous, vous venez de raccompagner vos amis, il est tard et il n’y a
rien a la tv mais aucune envie d’aller vous coucher. Vous avez une
collection impressionnante de divx(seulement des copies légale de vos
dvd)sur le pc du 1^er^ etage mais aucune envie d’aller la haut, vous
préféré regarder sur votre canapé devant la belle tv led branché a un
ordinateur relié au reseau par wifi. Et si je vous disais que c’est
possible et tres simplement ? Mediatomb est le logiciel qui permet de
realiser ce reve.

</div>

<div class="texte surlignable">

<div id="outil_sommaire" class="cs_sommaire cs_sommaire_avec_fond">

<div class="cs_sommaire_inner">

<div class="cs_sommaire_titre_avec_fond cs_done">

</div>

</div>

</div>

<div>

### Pré-requis {#outil_sommaire_0}

La on va faire avec les moyens du bord, c’est a dire votre pc principale
relié au reseau locale et a internet bien entendu et qui va faire office
de serveur multimedia et donc heberger mediatomb, d’un deuxieme pc qui
peut etre un ordi de récuperation trouvé dans une benne ou simplement le
vieu pc qui n’en peut plus de windows ou encore(c’est mon cas) d’une
console de jeu comme la PS3 qui permet de lire des medias sur le reseau
via dlna. Biensur il faudra de perference des distributions linux, de
préférence debian/ubuntu. Donc si on résume, on a besoin de :

-   d’un pc « serveur » avec mediatomb et votre collection de divx(votre
    pc principale)
-   d’un pc « client » (le vieu pc fera l’affaire) ou d’une console PS3
-   d’une connexion internet

### Installation {#outil_sommaire_1}

Mediatomb est un serveur multimédia UPnP avec une belle interface web.
Il vous permet de diffuser des fichiers multimédia sur votre réseau
domestique, et de les écouter ou regarder sur différents appareils
compatibles UPnP.  
Il permet aussi de transcoder a la volée des films pour les rendre  
compatible avec votre tv/ps3/pc client(mais on y reviendra plus loin..).
Pour l’installer , c’est tres simple, sous debian un simple

    aptitude install mediatomb vlc ffmpeg

suffira pour installer le serveur et les outils nécessaires pour
transcoder de la video.  

### Configuration de la base de données {#outil_sommaire_2}

Mediatomb a besoin d’une bas de données, sqlite3 ou MySQL, beaucoup
préféront le second mais moi dans l’optique d’etre le plus simple et le
plus rapide, je reste sur du sqlite3, surtout que cette base supporte
mes nombreux films. Par defaut c’est de toute façon du sqlite3 qui est
choisi. Pour ceux qui veulent du MySQL, il vous faudra vous tourner
vers[ubuntu-fr 5.3 Usage MySQL](http://doc.ubuntu-fr.org/mediatomb).  

### Configuration du serveur {#outil_sommaire_3}

Mediatomb peut etre lancé comme un service, c’est a dire au demarrage du
pc comme le serveur de mail exim, ou un serveur ftp, ou ssh. Ou il peut
etre lancé par l’utilisateur au debut de sa session. Dans mon cas j’ai
préféré la seconde solution et grace a mon bureau kde je peu lancer des
applications au demarrage automatiquement. Tout les réglages de
mediatomb se font dans un seul unique fichier :
/home/mon-utilisateur/.mediatomb/config.xml Activation Interface
Mediatomb Mediatomb possede une interface web plutot sympa et simple,
mais par defaut elle n’est pas activé, pour l’avoir il suffit de changer
la valeur ligne 7

    <ui enabled=« no » show-tooltips=« yes »>

par

    <ui enabled=« yes » show-tooltips=« yes »>

Gestion PS3 Pour que la PS3 puisse voir le serveur mediatomb, il faut
modifier la ligne 23 ou 26, changez « no » par « yes » :

    <protocolInfo extend=« yes »/>

et la ligne 65 ou 77, enlevez les commentaires afin de n’avoir sur cette
ligne que ce code :

    <map from=« avi » to=« video/divx »/>

on peut aussi ajouter la ligne

    <map from=« m2ts » to=« video/mpeg »/>

pour lire les fichiers HD M2TS avec la PS3. Sécuriser le
serveur(directement pompé d’ubuntu-fr 5.4 Sécuriser le serveur) Le
serveur a intégré un gestionnaire de fichier au-travers du navigateur
internet. Configuré par défaut, il permet à n’importe qui de naviguer
dans votre système de fichier et ainsi de télécharger n’importe quelle
donnée. Dans un environnement non sécurisé, il est nécessaire de
désactiver l’interface graphique : ligne 4, paramétrer l’attribut
enabled à no :

    <ui enabled=« no » />

Dans le contexte d’un environnement LAN, vous pouvez laisser l’interface
graphique activée, tout en paramétrant la gestion de compte : ligne 4,
laissez l’attribut enabled à yes. ligne 5, paramétrer l’attribut enabled
à yes :

    <accounts enabled=« yes » session-timeout=« 30 »>

ligne 6, paramétrer les attributs **user** et **password** … **La
protection par gestion de compte user/password  
n’est pas assez sécurisé pour un environnement non sécurisé. La  
documentation officielle précise de ne pas l’utiliser hors du contexte  
LAN.** Type de média Il existe un nombre toujours plus important chaque
jour de medias, et seule la méthode d’encodage diffère. Par exemple,
entre un divx et un mkv ou entre un mp3 et un ogg, c’est le codec
utilisé qui fera le media. Faudra donc le préciser a mediatomb en
éditant le fichier config.xml et en modifiant la section
&lt;extension-mimelayout&gt;. On peut trouver une bonne base dans
[ubuntu-fr.org 5.2Gestion des TV
SAMSUNG](http://doc.ubuntu-fr.org/mediatomb)

    <extension-mimelayout ignore-unknown=« no »> <map from=« mp3 » to=« audio/mpeg »/> <map from=« ogg » to=« application/ogg »/> <map from=« asf » to=« video/x-ms-asf »/> <map from=« asx » to=« video/x-ms-asf »/> <map from=« wma » to=« audio/x-ms-wma »/> <map from=« wax » to=« audio/x-ms-wax »/> <map from=« wmv » to=« video/x-ms-wmv »/> <map from=« wvx » to=« video/x-ms-wvx »/> <map from=« wm » to=« video/x-ms-wm »/> <map from=« wmx » to=« video/x-ms-wmx »/> <map from=« m3u » to=« audio/x-mpegurl »/> <map from=« pls » to=« audio/x-scpls »/> <map from=« flv » to=« video/x-flv »/> <map from=« mkv » to=« video/x-matroska »/> <map from=« mka » to=« audio/x-matroska »/> </extension-mimelayout> <mimelayout-upnpclass> <map from=« audio/* » to=« object.item.audioItem.musicTrack »/> <map from=« video/* » to=« object.item.videoItem »/> <map from=« image/* » to=« object.item.imageItem »/> <map from=« application/ogg » to=« object.item.audioItem.musicTrack »/> </mimelayout-upnpclass>

Cette section sert a attribuer un layout mime selon l’extension comme
`&amp;lt;map from="mp3" to="audio/mpeg"/&amp;gt;`{.spip_code dir="ltr"}
qui attribue les fichiers ayant comme extension .mp3 dans le layout
audio/mpeg mais il est possible de traiter un layout mime comme une
extension connue, c’est la section &lt;mimelayout-contentlayout&gt;, par
exemple
`&amp;lt;treat mimelayout="image/jpeg" as="jpg"/&amp;gt;`{.spip_code
dir="ltr"}.

    <mimelayout-contentlayout> <treat mimelayout=« audio/mpeg » as=« mp3 »/> <treat mimelayout=« application/ogg » as=« ogg »/> <treat mimelayout=« audio/x-flac » as=« flac »/> <treat mimelayout=« image/jpeg » as=« jpg »/> <treat mimelayout=« audio/x-mpegurl » as=« playlist »/> <treat mimelayout=« audio/x-scpls » as=« playlist »/> <treat mimelayout=« audio/x-wav » as=« pcm »/> <treat mimelayout=« audio/L16 » as=« pcm »/> <treat mimelayout=« video/x-msvideo » as=« avi »/> <treat mimelayout=« video/mp4 » as=« mp4 »/> <treat mimelayout=« audio/mp4 » as=« mp4 »/> <treat mimelayout=« application/x-iso9660 » as=« dvd »/> <treat mimelayout=« application/x-iso9660-image » as=« dvd »/> <treat mimelayout=« video/x-matroska » as=« mkv »/> <treat mimelayout=« audio/x-matroska » as=« mka »/> </mimelayout-contentlayout>

Les mime-layouts sont des formats de données, ce qui permet a mediatomb de
trier et pour transcoder.  

### Transcodage {#outil_sommaire_4}

Le transcodage comme son nom l’indique va permettre de transcoder la
video en un format reconnu par le « client » : Imaginons que comme moi
votre tv est relié a votre PS3 qui servira de client pour acceder au pc
« serveur »(celui qui fait tourner mediatomb) et vous permettra de lire
vos media, mais voila la PS3 a la facheuse tendance a ne pas lire
certains formats de vidéo comme par exemplele format .mkv. Mediatomb
permet de transcoder à la volée vos contenus vidéo pour les rendre
compatible avec votre client(ici la PS3), grace au transcodeur vlcmpeg
et a des scripts que nous allons ecrire. D’abord commençons par activer
le transcodage : pour cela on remplace « no » par « yes » a la ligne

     <transcoding enabled=« yes »>

du  
fichier config.xml. Nous indiquons maintenant ce qu’il faut  
transcoder(pour cela nous utilisons le layout mime vu plus haut), on  
rajoute si ce n’est deja fait dans la section
&lt;mimelayout-profile-mappings&gt; les lignes suivantes :

    <mimelayout-profile-mappings> <transcode mimelayout=« video/x-flv » using=« vlcmpeg »/> <transcode mimelayout=« application/ogg » using=« vlcmpeg »/> <transcode mimelayout=« application/ogg » using=« oggflac2raw »/> <transcode mimelayout=« audio/x-flac » using=« oggflac2raw »/> <transcode mimelayout=« video/x-matroska » using=« video-common »/> <transcode mimelayout=« application/ogg » using=« video-common »/> </mimelayout-profile-mappings>

Mediatomb comporte des « profils » de transcodage contenant la commande
qui permettra de convertir les videos dans un format connu par le
« client ». Toujours dans config.xml, on regarde la section
&lt;profils&gt; et on rajoute :

    <profile name=« video-common » enabled=« yes » layout=« external »> <avi-fourcc-list mode=« ignore »> <fourcc>DX50</fourcc> <fourcc>DM4V</fourcc> <fourcc>M4S2</fourcc> </avi-fourcc-list> <mimelayout>video/mpeg</mimelayout> <accept-url>yes</accept-url> <first-resource>yes</first-resource> <hide-original-resource>yes</hide-original-resource> <accept-ogg-theora>yes</accept-ogg-theora> <agent command=« /usr/bin/mediatomb-transcode-video » arguments=« %in %out »/> <buffer size=« 1048576 » chunk-size=« 26214 » fill-size=« 52428 »/> </profile>

en plus de ceux qui doivent deja s’y trouver :

    <profiles> <profile name=« oggflac2raw » enabled=« yes » layout=« external »> <mimelayout>audio/L16</mimelayout> <accept-url>no</accept-url> <first-resource>yes</first-resource> <accept-ogg-theora>no</accept-ogg-theora> <agent command=« ogg123 » arguments=« -d raw -o byteorder:big -f %out %in »/> <buffer size=« 1048576 » chunk-size=« 131072 » fill-size=« 262144 »/> </profile> <profile name=« vlcmpeg » enabled=« yes » layout=« external »> <mimelayout>video/mpeg</mimelayout> <accept-url>yes</accept-url> <first-resource>yes</first-resource> <accept-ogg-theora>yes</accept-ogg-theora> <agent command=« vlc » arguments=« -I dummy %in sout #transcodevenc=ffmpeg,vcodec=mp2v,vb=4096,fps=25,aenc=ffmpeg,acodec=mpga,ab=192,samplerate=44100,channels=2:standardaccess=file,mux=ps,dst=%out vlc:quit »/> <buffer size=« 14400000 » chunk-size=« 512000 » fill-size=« 120000 »/> </profile>

C’est bon, nous en avons fini avec la configuration de transcodage, il
reste seulement a creer le script mediatomb-transcode-video. On va creer
le fichier mediatomb-transcode-video dans /usr/bin/ :

    nano /usr/bin/mediatomb-transcode-video

et on le remplie :

    # !/bin/bash FFMPEG_PATH=« /usr/bin/ffmpeg » INPUT=« $1 » OUTPUT=« $2 » VIDEO_CODEC=« mpeg2video » VIDEO_BITRATE=« 4096k » VIDEO_FRAMERATE=« 25 » AUDIO_CODEC=« copy » FORMAT=« mpegts » exec « $FFMPEG_PATH » -i « $INPUT » -vcodec $VIDEO_CODEC -b $VIDEO_BITRATE  r $VIDEO_FRAMERATE -acodec $AUDIO_CODEC -f $FORMAT - > « $OUTPUT »

Donner les droits d’exécutions au script

    chmod +x /usr/bin/mediatomb-transcode-video

Le script fais appel à ffmpeg, d’ou son installation au début de
l’article. On n’a plus qu’a redemarrer mediatomb, de se préparer de quoi
manger, une petite biere et de se poser sur son canapé pour profiter de
son travail !!! Parefeu Une fois mediatomb installé et configuré, on
pensera a ouvrir les ports dans le pare feu([chez moi
ufw](http://doc.ubuntu-fr.org/ufw)) :

-   49152 en udp et tcp
-   1900 en udp

et aussi dans votre box/routeur(livebox, neufbox, freebox...).  

### Premier usage(pompé d’ubuntu-fr) {#outil_sommaire_5}

Vous pouvez le voir aussi en ouvrant votre navigateur internet favori,
et en tapant l’une ou l’autre des deux URL suivantes :
<http://localhost:49152> (<http://localhost:49152> avec ubuntu 10.04 et
10.10) <http://adresse_ip:49152> (<http://adresse_ip:49152> avec ubuntu
10.04 et 10.10) Si cela ne marche pas, alors essayer le port 49153 en
tapant l’une ou l’autre des deux URL suivantes :
<http://localhost:49153> (<http://localhost:49153> avec ubuntu 13.04)
<http://adresse_ip:49153> (<http://adresse_ip:49153> avec ubuntu 13.04)
Pour finir, il est possible d’y avoir accès aussi, en ouvrant votre
gestionnaire de fichiers, de vous diriger dans votre répertoire
personnel, puis vers .mediatomb, et de lancer mediatomb.html.
![](http://passiongnulinux.lescigales.org/data/images/images/logiciels/mediatomb1.png)
Cette interface web vous permettra de choisir quels fichiers vous
mettrez en partage. Pour mettre en partage des fichiers sur le serveur,
il faut aller sur le menu Filesystem puis naviguer dans l’arborescence
et cliquer sur le signe Plus (+) en haut à droite pour chaque dossier ou
fichier que vous souhaitez partager. Dans Database apparaîtra tous les
dossiers (et donc tous les fichiers « média » à l’intérieur) et fichiers
partager via le serveur mediatomb. Ceux ci apparaîtront au fur et à
mesure du scan des dossiers, plus ou moins rapidement selon qu’il y a
beaucoup de fichiers à l’intérieur. Pour plus d’explications sur
l’utilisation de l’interface web, je vous renvoie vers [la documentation
officielle … dans l’immédiat.](http://mediatomb.cc/pages/userinterface)
Vous ne verrez correctement la page web que si le serveur est bien
configuré et lancé … [voir la section activer
l’interface](http://doc.ubuntu-fr.org/mediatomb#activation_interface_mediatomb) !
Les sources de l’article :

-   <http://www.robertain.com/post/2011/03/17/transcodage-film-hd-mediatomb/>
-   <http://www.guillaume-leduc.fr/serveur-mediatomb-configuration.html>
-   <http://soowei.com/2008/11/27/streaming-mkv-in-mediatomb-to-ps3/>
-   <http://doc.ubuntu-fr.org/mediatomb>

<p>
pdf pour une utilisation classique sur une mandriva mais facilement
adaptable pour
debian : [tuto\_ps3.pdf](http://download.tuxfamily.org/passionlinux/documents/tuto_ps3.pdf)

</div>

</div>

</div>
