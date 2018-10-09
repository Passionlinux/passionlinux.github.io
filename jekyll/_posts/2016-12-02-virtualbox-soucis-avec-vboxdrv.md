---
title: Virtualbox, soucis avec vboxdrv
date: 2016-12-02 04:56
layout: post
---

Si au démarrage d'un OS émulé sous virtualbox, celui-ci se met a
pestiférer ce genre de message:  

> The VirtualBox Linux kernel driver (vboxdrv) is either not loaded or
> there is a permission problem with /dev/vboxdrv. Please reinstall the
> kernel module by executing '/sbin/vboxconfig' as root. where:
> suplibOsInit what: 3 VERR\_VM\_DRIVER\_NOT\_INSTALLED (-1908) - The
> support driver is not installed. On linux, open returned ENOENT.
> </p>

Un simple modprobe vboxdrv en root suffira pour tout remettre dans
l'ordre, a condition d'avoir installer les paquets kernel-devel.

    #modprobe vboxdrv

Court mais efficace.
