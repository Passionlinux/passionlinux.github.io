---
title: Gel du système, la ligne de commande peut vous sauver.
date: 2016-06-03 10:17
layout: post
---

<p>
<div class="chapo surlignable">

Dans de tres rare cas, comme un environnement de bureau beta par
exemple, on arrive a des cas de dysfonctionnement du systeme, soit la
souris et le clavier sont bloqués, soit ils sont lents (tout est au
ralenti). Il s’agit là d’un gel du systéme ou freeze.

Pour revenir a un état normal, on va utiliser l’un des terminaux
virtuels appelé aussi « tty »(en principe 6 car le 7 est le graphique),
via les combinaisons de touches :

\[Alt\]+\[Ctrl\]+\[F1\]

on remplace \[F1\] par celui que l’on veut entre \[F1\] et \[F6\].

On se retrouve devant un écran de terminal noir (tout votre écran), on
rentre notre login puis notre passe (le mot de passe n’apparait pas
comme dans un terminal graphique).

On est maintenant connecté et un mot de bievenu nous acceuille, on peut
maintenant rentrer des commandes. A tout moment pour revenir à
l’interface graphique on fait :

\[Alt\]+\[Ctrl\]+\[F7\].

</div>

<div class="texte surlignable">

Voici une liste de commandes qui peut nous etre utile :  

    ps aux

affiche  
tout les processus en cours sur notre machine en fournissant le PID, le  
pourcentage de mémoire utilisée, le nom du propriétaire, le temps
d’execution,... Ce qui nous permet d’identifier les processuus qui
occupent trop de ressources et qui sont peut etre coupable de ralentir
le système.

    ps aux | more

puisque la liste des processus peut etre tres longue, on utilise cette
commande pour la parcourir et on tape sur \[entrée\] du clavier pour
avancer.

    ps aux | grep nom_du_programme

affiche les informations concernant le programme (\[nom\_du\_programme\]
par exemple firefox). il est très utile quand on a un soupçon sur le
programme pouvant causser le gel du système.

    top

fournit en temps réel la liste des activités du processeur. Il affiche
le nombre de processus divisés par l’état, l’utilisation du processeur,
la mémoire physique et virtuelle utilisée et la liste des taches
gourmandes de cpu, le tout dans une interface intéractive permettant de
manipuler les processus. Pour trier les processus selon plusieurs
critères, P classe par utilisation du processeur  
(%CPU),c’est le trie par défaut, M par utilisation de la mémoire  
(%MEM)et les lettres N,A et T sont moins utile. Grâce a cette commande  
on verra le processus qui consomme de trop les ressources, pour
l’arreter  
en le forçant a se terminer (le tuer), on tape sur \[k\] puis \[9\], on  
entre son PID et on appuie sur \[Entrée\], on valide la demande de  
confirmation en appuyant sur \[Entrée\]. Pour quitter la liste top, on
tappe sur la touche \[q\].

    kill 

suivi du PID envoie le signal kill au processus spécifié, il sert a
terminer un processus qu’on connait l’identifiant avec l’une des
commandes précédentes.

    pkill nom_processus 

équivalente à la précédente mais avec le nom du programme (firefox par
exemple).

Ces deux dernieres  
commandes envoient le signal 15 par défaut, elle termine le processus  
de façon normale. Certains programme peuvent ignore le signal 15 et ne  
se termine pas. Dans ce cas, on utilise le signal 9 avec :

    kill -9 PID 

ou

    pkill -9 nom_processus

Une fois fini, et pour revenir à l’interface graphique faites

\[Alt\]+\[Ctrl\]+\[F7\].

Pour arrêter un programme graphique qui a bogué (planté) sous Linux,
vous pouvez si vous êtes sous l’environnement graphique utilisez xkill.  
Pour cela ouvrez un terminal, taper

    xkill

une petite tête de mort va apparaitre, dirigez là à l’aide de la souris
sur l’application graphique qui a planté et tuer cette dernière d’un
simple clic. Vous pouvez faire CTRL+C à l’aide du clavier pour fermer la
xkill sans tuer d’application.(1)

Si malgrés tout, on arrive pas à retrouver un état normal, avec les
commandes précédentes, on tentera :

    pkill X

ou

    pkill -9 X

pour forcer l’arrét du serveur X (l’interface graphique).

    reboot

pour redémarrer le système.

\(1) Merci à
[anatolem](http://passiongnulinux.lescigales.org/lapassiondulibre/core/admin/comments.php?a=0037&page=1#c1382871974-1)
pour son gentil rappel à
l’ordre![wink](http://passiongnulinux.lescigales.org/lapassiondulibre/plugins/ckeditor/ckeditor/plugins/smiley/images/wink_smile.gif "wink").

</div>

<p>
</p>

