---
title: "Activer le nettoyage automatique de /TMP sur une openSUSE"
date: 2017-11-18T00:40:17+01:00
layout: post
---
Pour activer le nettoyage automatique de */tmp* :

1. Copier */usr/lib/tmpfiles.d/tmp.conf* dans */etc/tmpfiles.d/*
2. Modifier */etc/tmpfiles.d/tmp.conf* pour les dossiers */tmp* et */var/tmp* au niveau des lignes :
    Code :

    	v /tmp 1777 root root 10d
    	v /var/tmp 1777 root root 30d

    (Note : ne pas modifier la première lettre, ce n'est pas forcément *v*,
    ça peut être d par exemple, mais modifier le dernier champ des deux
    lignes : "-" ? "10d" pour activer le nettoyage pour les fichiers de + 10
    jours par exemple)

3. Vérifier que systemd-tmpfiles-clean.timer est bien lancé :
    Code :

    	antoine@antoine-laptop : > systemctl list-timers NEXT                          LEFT     LAST                          PASSED    UNIT                         ACTIVATES lun. 2015-12-07 00:00:00 CET  22h left dim. 2015-12-06 01:39:54 CET  12min ago logrotate.timer              logrotate.service lun. 2015-12-07 01:52:27 CET  23h left dim. 2015-12-06 01:52:27 CET  13s ago   systemd-tmpfiles-clean.timer systemd-tmpfiles-clean.service

    	2 timers listed.
     	Pass all to see loaded but inactive timers, too.
     	antoine@antoine-laptop : >

      

Un grand merci à Antoine sur [Alionet](https://www.alionet.org/showthread.php?32114-Dossier-tmp-plein-dolphin-y-laisse-ses-aper%E7us-et-autres-sans-vider)

Voir en ligne : [alionet](http://www.alionet.org/showthread.php?32114-Dossier-tmp-plein-dolphin-y-laisse-ses-aper%E7us-et-autres-sans-vider)
