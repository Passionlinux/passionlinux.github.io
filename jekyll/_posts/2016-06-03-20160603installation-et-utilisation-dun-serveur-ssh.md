---
title: Installation et utilisation d'un serveur SSH
date: 2016-06-03 08:06
layout: post
---

Il peut être utile de prendre le contrôle a distance d’une machine, par
exemple, la machine de mes parents, faire leurs mises a jour, ou géré
l’installation du programme que mon père réclame, accéder a des fichiers
stocké sur celle-ci, ou tout simplement administrer son serveur.

<div style="text-align: center;">

![](http://download.tuxfamily.org/passionlinux/images/png/logo_openssh323b.png)

</div>

<div style="text-align: left;">

Le client SSH est installé par défaut sur debian/ubuntu et permet de se
connecter a tout serveur SSH et peu importe la plate-forme (Linux, bsd,
windows,..., pour windows on se servira du client putty...).
<div>

Le serveur/client SSH utilisé sous debian/ubuntu est OpenSSH qui nous
vient du monde BSD, pour installer ce couple, il suffit de faire dans un
terminal en root :
     # apt-get install openssh-server openssh-client

ou simplement

     # apt-get install ssh

### Utilisation

Je prends mon cas comme exemple, j’ai un ordinateur équipé de debian et
d’une connexion internet(ça va sans dire...), mes parents ont eux aussi
une connexion internet et une machine équipé d’ubuntu(plus exactement
ubuntu12.04). Chez moi je reçois un appel de mes parents me disant que
telle tache ne peut être fait car il manque telle programme, ou que je
dois faire leurs mises a jour(ils n’en sont pas friand) ou tout
simplement besoin de transférer des dossiers. Pour me connecter a cette
machine, il faudra que la machine de mes parents réponde a une adresse
fixe et du coup configuré la machine avec un serveur dns comme dyndns
qui se chargera de me donner un nom de machine connu sur internet et
reflétant mon adresse ip du style mesparents.ubuntu.org. Ou que mes
parents fasse un whatismyip sur google ce qui pourrait donner
78.55.128.1. Je n’aurais plus qu’a utiliser la commande :

     $ ssh mesparents.ubuntu.org

ou l’adresse ip :

     $ ssh 78.55.128.1

On peut même préciser un port si on a changé le /etc/fail2ban/jail.conf
de cette manière :

     $ ssh 78.55.128.1 -p 48888

Dans ce cas le `-p`{.spip_code dir="ltr"} veut dire port
et `48888`{.spip_code dir="ltr"} est le numéro du port utilisé au lieu
du port 22 par défaut. Dans tout les cas une demande de mot de passe
utilisateur suivra, et une fois rentré j’aurais accès au Shell de leur
machine. Quand j’en aurais fini, je fermerais la session avec la
commande :

     papa@mesparents.ubuntu.org : $ exit

<p>
Pour en savoir un peu plus, je vous conseille l’excellent livre [Debian
Etch cahier de
l’admin](http://passiongnulinux.tuxfamily.org/?p=118 "Debian Etch cahier de l'admin") et
surtout [sa version plus
recente.](http://debian-handbook.info/browse/fr-FR/stable/sect.remote-login.html) On
pourra aussi se fier a la bonne documentation
d’[ubuntu.fr](http://doc.ubuntu-fr.org/ssh) dont la partie
**[3.2](http://doc.ubuntu-fr.org/ssh)**[**Authentification par un
système de clés publique/privée.**](http://doc.ubuntu-fr.org/ssh)

</div>

<p>
Encore une fois je rajouterais une chose, comme tout service activé sur
une machine personnel, il faudra sécuriser l’ensemble, des règles
de pare-feu et notamment l’installation
de [Fail2ban](http://doc.ubuntu-fr.org/fail2ban).   Si vous ouvrez votre
serveur SSH sur Internet, par exemple pour y accéder depuis l’ordinateur
d’un ami(e) ou lui permettre d’accéder à certains de vos fichiers,
n’oubliez JAMAIS qu’Internet est parcouru en permanence par des robots
qui scannent et testent en permanence tous les serveurs (SSH et autres)
et qu’ils vont faire des tentatives pour trouver vos mots de passe de
compte. <span style="color: #800000;">L’usage des clés est donc
fortement recommandé. Sinon utilisez des mots de passe longs et
complexes ou encore utilisez des [systèmes de protection comme fail2ban
qui permet de bannir des adresses
IP.](http://passiongnulinux.tuxfamily.org/?p=84)</span>

</div>
