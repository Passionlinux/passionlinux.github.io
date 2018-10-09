---
title: Utiliser sudo sur Debian
date: 2017-02-21 23:34
layout: post
---

**sudo** s'utilise en ligne de commande, dans un terminal. Il permet de
prendre temporairement les droits root pour exécuter une commande. Ce
qui suit est repris du wiki de Debian-facile. Il est déconseillé
d'utiliser **sudo** inconsidérément sans en remanier la configuration
par défaut.  
<!--more-->  
On installe facilement sudo via Apt:

``` {.code .root}
apt-get update && apt-get install sudo
```

<div class="level2">

Passer *obligatoirement* par la commande **visudo** pour configurer
sudo. L'utilitaire visudo vérifie la syntaxe du fichier `/etc/sudoers`
avant d'enregistrer celui-ci. Taper :
``` {.code .file .root}
visudo
```

</div>

<div class="secedit editbutton_section editbutton_5">

<div class="level3">

### Droits d'exécution à une seule commande: {#droits-d-execution-a-une-seule-commande}

<div class="level3">

Sous la ligne :
``` {.code}
 Defaults env_reset
```

Ajoutez :

``` {.code}
Defaults        timestamp_timeout=0
```

<p>
En mettant le timeout à 0, les droits **root** ne seront plus
utilisables dès que vous aurez validé l'exécution de votre commande.

</div>

### Droits d'exécution à un seul user: {#droits-d-execution-a-un-seul-user}

<div class="level3">

Pour réserver l'utilisation de sudo à mon\_nom seulement, écrivez :
``` {.code}
 Defaults:mon_nom tty_tickets
```

Où mon\_nom est le nom que vous utilisez pour vous connecter à votre
session.

<div class="notetip">

Ainsi, pour un seul *utilisateur*, il n'est pas nécessaire d'intégrer ce
dernier dans le groupe *sudo*

</div>

</div>

### sudo UN SEUL utilisateur AVEC mot de passwd demandé: {#sudo-un-seul-utilisateur-avec-mot-de-passwd-demande}

C'est la configuration préconisée pour tous les utilisateurs de sudo
débutant. Sous la ligne :

``` {.code}
 root    ALL=(ALL:ALL) ALL
```

écrivez :

``` {.code}
 badaboum ALL=(ALL:ALL) ALL
```

(**badaboum** illustrant ici votre nom d'utilisateur **mon\_nom**, par
exemple…) Ainsi, **badaboum** sera le seul *utilisateur* autorisé à se
servir de la commande **sudo** dans un terminal. **Test de la
configuration modifiée :** Tapez une commande root comme celle-ci par
exemple :

``` {.code .file .user}
sudo fdisk -l
```

Le mot de passe de l'*user* sera alors demandé et non plus celui de root
:

``` {.code}
 [sudo] password for badaboum: <//Taper ici le passwd de cet user//>
```

Et la commande s'exécute !

</div>

</div>
