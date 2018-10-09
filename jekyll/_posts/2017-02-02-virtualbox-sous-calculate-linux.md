---
title: VirtualBox sous Calculate Linux
date: 2017-02-02 11:06
layout: post
---

Je reprend ici [la méthode pour installer l'émulateur
VirtualBox](http://www.linuxtricks.fr/wiki/installer-virtualbox-sous-gentoo-calculate-linux),
vu le nombre de paquets disponible sous Gentoo/Calculate, on peut vite
se tromper. Je pars du principe que la machine est a jour et/ou qu'on a
au moins synchroniser notre système avec les dépôts en ligne, dans le
cas contraire:

    # cl-update

ou

    # eix-sync

Cela étant fait, nous allons installer virtualbox avec les extensions
d'Oracle, et les modules pour le kernel :

<div class="code">

``` {.bash}
# emerge -avq app-emulation/virtualbox app-emulation/virtualbox-extpack-oracle app-emulation/virtualbox-modules app-emulation/virtualbox-additions
```

<p>
On va charger les modules nécessaires a VirtualBox pour fonctionner avec
la commande **modprobe:**

</div>

<div class="code">

``` {.bash}
modprobe vboxdrv modprobe vboxnetflt modprobe vboxnetadp
```

On peut aussi redémarrer la machine au lieu de lancer modprobe. Emerge
nous préviens pendant l'installation que l'utilisateur courant doit etre
ajouté au groupe vboxusers, on se rajoute donc en faisant:

</div>

<div class="code">

``` {.bash}
usermod -G vboxusers -a nom_d'_utilisateur
```

</div>

On vérifie l'ajout de notre user dans le groupe via la commande :

``` {.bash}
grep vboxusers /etc/group vboxusers:x:989:nom_d'_utilisateur
```

C'est bon, on est bien dedans. On relance la session pour que le
changement soit bien pris en compte puis on lance virtualbox.
![](http://download.tuxfamily.org/passionlinux//2017/02/Screenshot_20170202_110126-1024x545.png){.aligncenter
.size-large .wp-image-1048 width="525" height="279"}
