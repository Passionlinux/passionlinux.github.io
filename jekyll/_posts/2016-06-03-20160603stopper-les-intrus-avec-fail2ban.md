---
title: Stopper les intrus avec Fail2ban
date: 2016-06-03 10:10
layout: post
---

<div class="texte surlignable">

D’après [Wikipedia](http://fr.wikipedia.org/wiki/Fail2ban), Fail2ban est
un framework de prévention contre les intrusions, écrit en Python. Il
fonctionne sur les systèmes POSIX possédant une interface de contrôle
des paquets (tel que TCP Wrapper) ou un pare-feux (tel que Netfilter).
Fail2ban  
bloque les adresses IP appartenant à des hôtes qui tentent de casser
la sécurité du système. Il cherche ces adresses en parcourant les
journaux système (par ex. : /var/log/pwdfail, /var/log/auth.log, etc.).
Fail2ban est aussi capable de bloquer les attaques distribuées.  
Installation
------------

Apres avoir installé [un serveur SSH sur mon
pc ](http://passiongnulinux.tuxfamily.org/?p=83), il me faut maintenant
le sécuriser. Comme souvent sur Debian/Ubuntu, l’installation se résume
a :

    sous debian : # aptitude install fail2ban sous mageia : # urpmi fail2ban sous opensuse : # zypper install fail2ban

Ensuite suffit de lancer la commande pour activer fail2ban(je n’ai pas
eu à le faire chez moi) :

    # systemctl start fail2ban.service

Configuration
-------------

J’ai suivi de pres les conseils donné sur ubuntu-fr, j’ai édité le
fichier**/etc/fail2ban/jail.conf** de cette manière :

    [ssh]

    enabled = true
     port = ssh,sftp,2276
     filter = sshd
     logpath = /var/log/auth.log
     maxretry = 6

Il indique, par ordre, l’activation, les ports à bloquer avec les règles
iptables, le nom du filtre (expression régulière) associé, le fichier de
log à lire, le nombre maximal de tentatives. Un certain nombre de
services disposent de tels blocs de configuration, vous pouvez les
activer en passant si besoin false à true.  

> <span style="color: #800000;"> Attention, si vous avez changé le port
> ssh dans la configuration de OpenSSH (comme il est recommandé de le
> faire pour éviter les robots qui testent le port 22 par défaut), il
> semblerait qu’il faille le préciser à fail2ban ! Dans la configuration
> ci dessus, ajoutez à la ligne "port", votre port SSH, par exemple port
> =ssh,sftp,2276 si votre nouveau port ssh est 2276 sans quoi fail2ban
> ne surveillera que le port 22 !</span>
> </p>

j’ai ensuite relancé fail2ban comme demandé avec un :

    # fail2ban-client reload

J’ai vérifié les prisons avec un :

    # fail2ban-client status Status |- Number of jail : 1 `- Jail list : ssh

Enfin on va tenter de se faire passer pour un méchant, pour cela on se
connecte plusieurs fois mais en donnant un pass bidon, au bout de trois
tentatives, on ne pourra plus se connecter car banni... On regarde ce
qui se passe coté serveur via cette commande :

    # fail2ban-client status ssh

qui dans ce cas vous retournera le statut de la prison ’ssh’ (avec le
nombre de tentative échouée et la liste des IP banni) :

    # Status for the jail : ssh |- filter | |- File list : /var/log/auth.log | |- Currently failed : 3 | `- Total failed : 3 `- action |- Currently banned : 1  | `- IP list:192.168.1.18  `- Total banned : 1

Et c’est tout, apres on peut améliorer la bête, mais dans mon cas pas
besoin de plus. à
voir : [http://blog.pastoutafait.fr/billets/Protéger-un-serveur-avec-Fail2ban](http://blog.pastoutafait.fr/billets/Prot%C3%A9ger-un-serveur-avec-Fail2ban)

<div
style="background-image: url('http://passiongnulinux.tuxfamily.org/spip/spip.php?action=cron');">

</div>

</div>

Voir en ligne :
[doc.ubuntu-fr](http://doc.ubuntu-fr.org/fail2ban){.spip_out}
