---
title: Quelques soucis d'importation.
date: 2016-07-16 05:08
layout: post
---

Vous l'avez peut être remarqué mais l'importation depuis dotclear n'est
pas sans défaut. Les liens internes sont mort, ce qui est normal et je
dois donc les refaire. Mais aussi la totalité des formules dans les
cadres préformatés. Exemple dans:
http://passiongnulinux.tuxfamily.org/?p=25 Le premier cadre préformaté
est bon: Le fichier d’origine:

    deb cdrom:[Debian GNU/Linux etc... # Debian Jessie, dépôt principal deb http://httpredir.debian.org/debian/ jessie main # Debian Jessie, mises-à-jour de sécurité deb http://security.debian.org/ jessie/updates main # Debian Jessie, mises-à-jour "volatiles" deb http://httpredir.debian.org/debian/ jessie-updates main

Mais les suivant sont HS:

     # Debian Jessie, dépôt principal + paquets non libres deb http://httpredir.debian.org/debian/ jessie main contrib non-free # Debian Jessie, mises-à-jour de sécurité + paquets non libres deb http://security.debian.org/ jessie/updates main contrib non-free # Debian Jessie, mises-à-jour "volatiles" + paquets non libres deb http://httpredir.debian.org/debian/ jessie-updates main contrib non-free

Donc je dois me taper les quelques billets avec du code dans des cadres
et refaire les sauts de ligne. Je m’occupe de cette tache ce week-end.
