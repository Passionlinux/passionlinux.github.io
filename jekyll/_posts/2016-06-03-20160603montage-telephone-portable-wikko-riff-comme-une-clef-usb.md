---
title: Montage téléphone portable wikko riff comme une cléf usb
date: 2016-06-03 12:28
layout: post
---

<p>
![](http://data.wikomobile.com/documents/images/FR/90b48ea6100488ebaf951b7a8226997a.jpg)

   Il faudra commenter la règle correspondant au device Mediatek dans le
fichier **/lib/udev/rules.d/40-usb\_modeswitch.rules** :

<div>

<div style="background:#eee; border:1px solid #ccc; padding:5px 10px">

ATTR*idVendor*=="0e8d", ATTR*idProduct*=="0002", RUN+="usb\_modeswitch
’%b/%k’"

</div>

</div>

Voir ici : [https://bugs.debian.org/cgi-bin/bugrepo …
bug=686840](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=686840)  
Redémarrer, ensuite, ta machine.

<p>
</p>

