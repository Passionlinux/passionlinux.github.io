---
title: Minidlna, voir ses films du PC directement sur sa TV.
date: 2016-08-07 23:35
layout: post
---

Je me suis aperçus que je n'ai pas mis a jour les tutos sur[Minidlna
1](http://passiongnulinux.tuxfamily.org/2016/06/03/20160603minidlna-un-autre-serveur-multimedia/)
et [Minidlna
2](http://passiongnulinux.tuxfamily.org/2016/06/03/20160603minidlna-le-serveur-multimedia/),
si on peut appeler ça tutos, depuis l'arrivé de Jessie et de son
systemd.  
<!--more-->  
Il y a pas grand chose a faire, seulement le redémarrage du service qui
change, je vous invite donc a relire les deux autres billets.

    systemctl restart minidlna

au lieu d'un

     service minidlna restart

Pour le reste c'est identique. sous ubuntu ou debian :

    apt-get install minidlna

Pour la configuration suffit d’aller sur
[ubuntu](http://doc.ubuntu-fr.org/minidlna), mais en gros on change :
wlan0 pour le wifi ou le nom du reseau comme enp4s0 au lieu de eth0.

    network_interface=eth0

dossier des fichiers.

    media_dir=V,/repertoire/films

le nom qu’on donne au serveur.

    friendly_name=My DLNA Server

le port

    port=49200

<div>

Pour ne pas être obligé de lancer un scan des fichiers à chaque fois que
nous en ajoutons, vérifions que la ligne « inotify= » est bien réglée
sur « yes » :
     inotify=yes

</div>

Si le serveur n’apparaît pas sur le client, nous pouvons baisser le
notify interval par exemple à 60, c’est a dire qu’il va attendre 60
secondes pour lancer une recherche de media ajouté.

     notify_interval=60

et pour le reste c’est pas trop utile… Voici mon fichier minidlna.conf 
une fois modifié:

    # This is the configuration file for the MiniDLNA daemon, a DLNA/UPnP-AV media # server. # # Unless otherwise noted, the commented out options show their default value. # # On Debian, you can also refer to the minidlna.conf(5) man page for # documentation about this file. # Specify the user name or uid to run as. #user=minidlna # Path to the directory you want scanned for media files. # # This option can be specified more than once if you want multiple directories # scanned. # # If you want to restrict a media_dir to a specific content layout, you can # prepend the directory name with a letter representing the layout (A, P or V), # followed by a comma, as so: # * "A" for audio (eg. media_dir=A,/var/lib/minidlna/music) # * "P" for pictures (eg. media_dir=P,/var/lib/minidlna/pictures) # * "V" for video (eg. media_dir=V,/var/lib/minidlna/videos) media_dir=V,/home/sebastien/Vidéos # Path to the directory that should hold the database and album art cache. #db_dir=/var/cache/minidlna # Path to the directory that should hold the log file. #log_dir=/var/log # Type and minimum level of importance of messages to be logged. # # The layouts are "artwork", "database", "general", "http", "inotify", # "metadata", "scanner", "ssdp" and "tivo". # # The levels are "off", "fatal", "error", "warn", "info" or "debug". # "off" turns of logging entirely, "fatal" is the highest level of importance # and "debug" the lowest. # # The layouts are comma-separated, followed by an equal sign ("="), followed by a # level that applies to the preceding layouts. This can be repeated, separating # each of these constructs with a comma. # # The default is to log all layouts of messages at the "warn" level. #log_level=general,artwork,database,inotify,scanner,metadata,http,ssdp,tivo=warn # Use a different container as the root of the directory tree presented to # clients. The possible values are: # * "." - standard container # * "B" - "Browse Directory" # * "M" - "Music" # * "P" - "Pictures" # * "V" - "Video" # If you specify "B" and the client device is audio-only then "Music/Folders" # will be used as root. root_container=V # Network interface(s) to bind to (e.g. eth0), comma delimited. # This option can be specified more than once. #network_interface= # IPv4 address to listen on (e.g. 192.0.2.1/24). # If omitted, the mask defaults to 24. The IPs are added to those determined # from the network_interface option above. # This option can be specified more than once. #listening_ip= # Port number for HTTP traffic (descriptions, SOAP, media transfer). # This option is mandatory (or it must be specified on the command-line using # "-p"). port=49152 # URL presented to clients (e.g. http://example.com:80). #presentation_url=/ # Name that the DLNA server presents to clients. # Defaults to "hostname: username". friendly_name=Debian MiniDLNA Server # Serial number the server reports to clients. # Defaults to 00000000. serial=681019810597110 # Model name the server reports to clients. #model_name=Windows Media Connect compatible (MiniDLNA) # Model number the server reports to clients. # Defaults to the version number of minidlna. #model_number= # Automatic discovery of new files in the media_dir directory. #inotify=yes # List of file names to look for when searching for album art. # Names should be delimited with a forward slash ("/"). # This option can be specified more than once. album_art_names=Cover.jpg/cover.jpg/AlbumArtSmall.jpg/albumartsmall.jpg album_art_names=AlbumArt.jpg/albumart.jpg/Album.jpg/album.jpg album_art_names=Folder.jpg/folder.jpg/Thumb.jpg/thumb.jpg # Strictly adhere to DLNA standards. # This allows server-side downscaling of very large JPEG images, which may # decrease JPEG serving performance on (at least) Sony DLNA products. #strict_dlna=no # Support for streaming .jpg and .mp3 files to a TiVo supporting HMO. #enable_tivo=no # Notify interval, in seconds. notify_interval=10 # Path to the MiniSSDPd socket, for MiniSSDPd support. #minissdpdsocket=/run/minissdpd.sock
