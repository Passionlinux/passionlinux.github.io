---
title: Debian la bien chiante... Ou l'abandon de celle ci par les developeurs en amont...
date: 2016-06-03 12:06
layout: post
---

<p>
Ce titre ne veut rien dire, c’est juste un coup de gueule.

En gros c’est juste une histoire de paquets pas a jour dans Sid, puisque
debian est encore gelé a l’heure ou j’ecris. Le paquet en question est
xfce en 4.12, disponible dans experimental mais sans ses goodies...
Alors que ubuntu possède des ppa pour la version 4.12 officiels et
maintenu par des développeurs officiels de xfce.

Et debian dans tout ça, on a encore une moitié de version. Et en plus de
cela, on a pas mal de paquets, gstreamer pour ne pas le nommer, qui ne
veut pas s’installer.

Il serait grand temps que debian propose un truc qui se rapproche des
ppa d’ubuntu, et pourquoi pas directement les même ppa, après tout c’est
des paquets  .deb et ça devrait être compatible ? En faite non et ceci
pour une bonne raison, debian donne souvent une version de paquet aux
dépendances. Par exemple, les plugins de xfce ont besoin de panel
=&lt;4.10, alors que certains de ces plugins n’ont même pas évolué...

Un autre truc qui me déplait au plus haut point sous debian, c’est le
changement de nom/logo des produits mozilla. Je comprend le pourquoi,
mais je reste a dire qu’en plus de proposer les versions totalement
libre, il pourrait être sympa de proposer les « vrais » dans la section
nonfree ou du moins un script qui télécharge et installe le binaire du
site mozilla...

La raison de leurs « faux mozilla » est simple, sous debian stable,
aucun paquets ne doit changer de version ou apporter/supprimer des
fonctions, or les « mozilla » en proposent a chaque fois. Et du coté de
mozilla, seuls les versions officiels sans patchs externes peuvent
utiliser les logos et les marques officiels. Donc si debian corrige plus
question d’utiliser la marque et les logos.

Et le choix a été vite fait, entre deux solution :

-   Soit le mainteneur debian migrait les paquets mozilla de free a
    nonfree
-   Soit il changeait de nom et de logos pour ses paquets

Donc pour satisfaire cette exigence que debian n’est pas la seule a
demander, mozilla  
a proposé une version LTS ou plutôt ESR. Mais ce n’est pas suffisant  
pour ce qui est des problèmes de droit de licence/utilisation de la  
marque et logos.

Bon je continu a penser qu’en parallèle des paquets renommer, on
pourrait avoir firefox/thunderbird et seamonkey dans nonfree.

Ce qui me chagrine vraiment c’est que beaucoup de hits n’ont plus que
des ppa ubuntu, et ne se prennent même plus la tete a maintenir un dépôt
debian, pidgin, xfce, et j’en passe... Il serait temps vraiment que
debian se rapproche de sa fille.

Debian reste debian, pour le pire et le meilleur, mais pour moi elle
reste la meilleure...

<p>
</p>

