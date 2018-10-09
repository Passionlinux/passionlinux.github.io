---
title: Minidlna, le serveur multimedia.
date: 2016-06-03 08:29
layout: post
---

<div id="content" class="content primary">

<article>
<div class="main">

<div class="texte surlignable">

    En Janvier je parlais déjà de minidlna comme remplaçant du vieux
mediatomb : [minidlna-un-autre-serveur-multimedia](http://passiongnulinux.tuxfamily.org/?p=87)
Depuis Un excellent tuto a été mis en place sur
[debian-facile](https://debian-facile.org/doc:reseau:minidlna)  
Introduction
------------

<div>

L’accès aux contenus multimédias sur un réseau local est relativement
simple lorsque le client est compatible avec le protocole Samba, mais
depuis l’arrivée des smartphones, tablettes, et autres TV connectées, il
serait dommage de se priver d’un autre protocole : l’**UPNP**
**minidlna** est un logiciel serveur UPNP vraiment simple d’utilisation
entièrement compatible avec les clients DLNA / UPnP. Le démon
**minidlna** sert des fichiers multimédias (musiques, photos et vidéos)
à des clients sur un réseau.

</div>

<!--more-->

Installation du paquet
----------------------

<div>

Pour debian/ubuntu :
    apt-get update && apt-get install minidlna

</div>

<div>

<div>

Pour opensuse :

</div>

    zypper install minidlna

Pour mageia :

    urpmi minidlna

</div>

Configuration
-------------

<div>

Sous opensuse utiliser yast pour la configuration, pour mageia et
debian, voici le fichier de configuration
`/etc/minidlna.conf`{.spip_code dir="ltr"} par défaut :
[/etc/minidlna.conf](https://debian-facile.org/_export/code/doc:reseau:minidlna?codeblock=1 "Télécharger un extrait"){.mediafile
.mf_conf}
``` {.code .file .config}
# port for HTTP (descriptions, SOAP, media transfer) traffic port=8200   # network interfaces to serve, comma delimited #network_interface=eth0   # specify the user account name or uid to run as #user=jmaggard   # set this to the directory you want scanned. # * if you want multiple directories, you can have multiple media_dir= lines # * if you want to restrict a media_dir to specific content layouts, you #   can prepend the layouts, followed by a comma, to the directory: #   + "A" for audio  (eg. media_dir=A,/home/jmaggard/Music) #   + "V" for video  (eg. media_dir=V,/home/jmaggard/Videos) #   + "P" for images (eg. media_dir=P,/home/jmaggard/Pictures) #   + "PV" for pictures and video (eg. media_dir=PV,/home/jmaggard/digital_camera) media_dir=/opt   # set this to merge all media_dir base contents into the root container # note: the default is no #merge_media_dirs=no   # set this if you want to customize the name that shows up on your clients #friendly_name=My DLNA Server   # set this if you would like to specify the directory where you want MiniDLNA to store its database and album art cache #db_dir=/var/cache/minidlna   # set this if you would like to specify the directory where you want MiniDLNA to store its log file #log_dir=/var/log   # set this to change the verbosity of the information that is logged # each section can use a different level: off, fatal, error, warn, info, or debug #log_level=general,artwork,database,inotify,scanner,metadata,http,ssdp,tivo=warn   # this should be a list of file names to check for when searching for album art # note: names should be delimited with a forward slash ("/") album_art_names=Cover.jpg/cover.jpg/AlbumArtSmall.jpg/albumartsmall.jpg/AlbumArt.jpg/albumart.jpg/Album.jpg/album.jpg/Folder.jpg/folder.jpg/Thumb.jpg/thumb.jpg   # set this to no to disable inotify monitoring to automatically discover new files # note: the default is yes inotify=yes   # set this to yes to enable support for streaming .jpg and .mp3 files to a TiVo supporting HMO enable_tivo=no   # set this to strictly adhere to DLNA standards. # * This will allow server-side downscaling of very large JPEG images, #   which may hurt JPEG serving performance on (at least) Sony DLNA products. strict_dlna=no   # default presentation url is http address on port 80 #presentation_url=http://www.mylan/index.php   # notify interval in seconds. default is 895 seconds. notify_interval=900   # serial and model number the daemon will report to clients # in its XML description serial=12345678 model_number=1   # specify the path to the MiniSSDPd socket #minissdpdsocket=/var/run/minissdpd.sock   # use different container as root of the tree # possible values: #   + "." - use standard container (this is the default) #   + "B" - "Browse Directory" #   + "M" - "Music" #   + "V" - "Video" #   + "P" - "Pictures" #   + Or, you can specify the ObjectID of your desired root container (eg. 1$F for Music/Playlists) # if you specify "B" and client device is audio-only then "Music/Folders" will be used as root #root_container=.   # always force SortCriteria to this value, regardless of the SortCriteria passed by the client #force_sort_criteria=+upnp:class,+upnp:originalTrackNumber,+dc:title   # maximum number of simultaneous connections # note: many clients open several simultaneous connections while streaming #max_connections=50
```

Maintenant configurons le serveur pour qu’il partage efficacement nos
fichiers en modifiant le fichier `minidlna.conf`{.spip_code dir="ltr"}
avec
[nano](https://debian-facile.org/doc:editeurs:nano "doc:editeurs:nano"){.wikilink1} :

     nano /etc/minidlna.conf

Le fichier, bien qu’en anglais, est relativement simple à comprendre.

<div>

De nombreuses lignes d’options sont commentées, c’est à dire qu’il y a
un \#[2)](https://debian-facile.org/doc:reseau:minidlna#fn__2){#fnt__2
.fn_top} devant afin que le serveur ne prenne pas ces options en compte.
Nous avons donc le choix :
1.  <div>

    soit d’enlever ce \# devant la ligne afin que l’option soit prise en
    compte,

    </div>

2.  <div>

    soit d’ajouter une ligne équivalente sans ce symbole, cela nous
    permet de garder à vue la configuration initiale.

    </div>

</div>

<div>

Afin que les changements soient pris en compte, chaque modification du
fichier de configuration doit être suivie de la commande suivante :
     service minidlna restart

</div>

</div>

### Port

<div>

Modifions la valeur par défaut du port et mettre
     port=49200

</div>

### Network interface

<div>

Spécifions notre interface de réseau, généralement `etho`{.spip_code
dir="ltr"} ou `eth1`{.spip_code dir="ltr"} suivant votre carte réseau.
La commande :
     ifconfig

nous donnera rapidement la réponse. Par câble ethernet

     network_interface=eth0

Par WI-FI

     network_interface=wlan0

Par câble ethernet et par WI-FI dans le cas de plusieurs réseaux il faut
prendre garde à bien séparer par des virgules les interfaces réseau
ainsi :

     network_interface=eth0,wlan0

</div>

### Partage des dossiers

<div>

Une autre option importante à configurer, c’est de mettre en place les
partages. **minidlna** permet de trier nos fichiers par layout de média,
il suffit de lui préciser si ce sont des vidéos, des images, ou des
fichiers audios. Chacun de ces layouts est désigné par une lettre :
-   <div>

    V pour les vidéos

    </div>

-   <div>

    P pour les images

    </div>

-   <div>

    A pour les fichiers audios.

    </div>

Par exemple, pour partager les fichiers vidéos situés dans un répertoire
`/medias/films/`{.spip_code dir="ltr"}, voici la ligne à entrer :

     media_dir=V,/medias/films

<div>

Notez que le layout de média n’a pas besoin d’être précisé si tous nos
médias sont situés dans le répertoire /home/utilisateur, la ligne
media\_dir=/home/utilisateur suffira.Pour nous simplifier la navigation
plusieurs partages peuvent être ajoutés. Nous pouvons par exemple
choisir de séparer nos vidéos par layout en mettant d’un coté les films et
d’un autre les vidéos de famille. Par exemple :
media\_dir=/home/utilisateur/film
media\_dir=/home/utilisateur/videos\_famille

</div>

</div>

### Nom interface

<div>

Modifions le nom qui apparaîtra sur l’interface des clients ou celui qui
apparaîtra sur l’interface du client DLNA (télévisions, smartphones,
tablettes…) De base, le nom n’est pas très explicite, et il sera
sûrement plus agréable de lire à la place par exemple : « Serveur DLNA
Debian ».
![:-)](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L15xH15/icon_smilegib868-a29d9.gif?1464919716){.icon
width="15" height="15"} Dans ce cas l’option à modifier est
« friendly\_name= » Ce qui nous donnera pour cet exemple :
     friendly_name=Serveur DLNA Debian

</div>

### Répertoire du cache

<div>

Ajoutons cette ligne :
     db_dir=/var/cache/minidlna

</div>

### Recherche nouveaux fichiers

<div>

Pour ne pas être obligé de lancer un scan des fichiers à chaque fois que
nous en ajoutons, vérifions que la ligne « inotify= » est bien réglée
sur « yes » :
     inotify=yes

</div>

### notify interval

<div>

Si le serveur n’apparaît pas sur le client, nous pouvons baisser le
notify interval par exemple à 60, c’est a dire qu’il va attendre 60
secondes pour lancer une recherche de media ajouté.
     notify_interval=60

</div>

### Augmenter le nombre d’entrées

<div>

Il arrive parfois (lorsqu’il y a un grand nombre de fichiers) que la
base de données ne veuille plus se mettre à jour. Il faut alors demander
au noyau d’augmenter le nombre d’entrées qu’inotify peut créer, avec la
commande suivante :
     sysctl fs.inotify.max_user_watches=100000

Si nous voulons que la modification soit permanente, il faut plutôt
choisir de modifier le fichier : `/etc/sysctl.conf`{.spip_code
dir="ltr"}, en y ajoutant *fs.inotify.max\_user\_watches = 100000* à la
fin :

     nano /etc/sysctl.conf

     fs.inotify.max_user_watches = 100000

</div>

### Enregistrement des configurations

<div>

Une fois toutes les modifications faites enregistrons-les via les
touches <kbd>F3</kbd> ou <kbd>Ctrl</kbd>+<kbd>O</kbd> puis validons par
<kbd>? Entrée</kbd>. Nous pouvons enfin quitter
[nano](https://debian-facile.org/doc:editeurs:nano "doc:editeurs:nano"){.wikilink1}
via les touches <kbd>F2</kbd> ou <kbd>Ctrl</kbd>+<kbd>X</kbd>

</div>

### Lancement de minidlna et scan

<div>

Une fois que nous avons terminé de configurer le programme, lançons
minidlna ainsi :
     service minidlna start

Puis, il faut demander à minidlna de scanner une première fois nos
médias afin de les rendre disponibles :

     service minidlna force-reload

<p>
C’est tout !
![:-)](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L15xH15/icon_smilegib868-a29d9.gif?1464919716){.icon
width="15" height="15"} Maintenant nos médias qui se trouvent sur notre
OS préféré seront détectés par les autres périphériques dotés du
protocole DLNA / UPnP.

</div>

<div>

<div>

</div>

</div>

Fichier configuration simplifié
-------------------------------

<div>

Voici un exemple de fichier de configuration très simplifié et sans les
commentaires.
<div>

Dans les sections media\_dir ne pas oublier de changer “utilisateur” par
notre nom d’utilisateur

</div>

``` {.code}
port=49200 network_interface=eth0,wlan0 #user=jmaggard media_dir=V,/home/utilisateur/Video media_dir=P,/home/utilisateur/Images media_dir=A,/home/utilisateur/Musique #merge_media_dirs=no friendly_name=Serveur DLNA Debian db_dir=/var/cache/minidlna #log_dir=/var/log #log_level=general,artwork,database,inotify,scanner,metadata,http,ssdp,tivo=warn album_art_names=Cover.jpg/cover.jpg/AlbumArtSmall.jpg/albumartsmall.jpg/AlbumArt.jpg/albumart.jpg/Album.jpg/album.jpg/Folder.jpg/folder.jpg/Thumb.jpg/thumb.jpg inotify=yes enable_tivo=no strict_dlna=no notify_interval=60 serial=12345678 model_number=1 #root_container=. #max_connections=50
```

</div>

<div>

<div>

</div>

</div>

Liste de commandes utiles
-------------------------

<div>

***Lancer minidlna***
     service minidlna start

***Reancer minidlna***

     service minidlna restart

***Arrêter minidlna***

     service minidlna stop

***Connaître le status***

     /service minidlna status

***Scanner / reconstruire la base de données***

     service minidlna force-reload

Pour plus d’info sur minidlna consultez le manuel :
![;-)](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L15xH15/icon_winkgif67d1-c3ffb.gif?1464919716){.icon
width="15" height="15"}

     man minidlna

</div>

</div>

</div>

</article>

</div>
