---
title: "Montage téléphone portable wikko riff comme une cléf usb"
date: 2017-11-18T01:14:56+01:00
layout: post
---
Il faudra commenter la règle correspondant au device Mediatek dans le fichier */lib/udev/rules.d/40-usb_modeswitch.rules* :

	ATTRidVendor=="0e8d", ATTRidProduct=="0002", RUN+="usb_modeswitch %b/%k"

Voir ici : https://bugs.debian.org/cgi-bin/bugrepo bug=686840
Redémarrer ensuite la machine.
