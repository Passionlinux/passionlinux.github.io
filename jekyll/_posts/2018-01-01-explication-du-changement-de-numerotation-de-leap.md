---
title: "Explication du changement de numérotation de Leap"
date: 2018-04-06T19:58:19+02:00
layout: post
---

Un semblant de traduction d'un fil https://lists.opensuse.org/opensuse-announce/2017-04/msg00000.html
## openSUSE Leap 15 ##

Comme pour Leap 42.x, des versions mineures sont attendues annuellement pendant au moins 3 années, donc vous pouvez vous attendre à un Leap 15.1 à suivre, puis 15.2 et au-delà.

De toute évidence, il s'agit d'un changement radical par rapport à la version actuelle 42.x, donc je vais expliquer ce qui justifie ce changement dans certains détail ci-dessous.

D'abord, un peu d'histoire. Lorsque nous avons lancé openSUSE Leap, le numéro de version était un problème qui devait être résolu. openSUSE à ce moment-là était à 13.2, mais SUSE Linux Enterprise (SLE) était à 12 et se dirigeait vers 12 SP1.

Comme le principal argument de vente unique de Leap par rapport à tous les autres la distribution est le fait qu'elle est basée sur des sources SLE. Nous voulions refléter cela dans le numéro de version.
Cela était particulièrement important lorsque vous considérez qu'une version majeure dans SLE signifie vraiment quelque chose ("changements architecturaux majeurs de la dernière version est présentée ici ") alors que les versions mineures / service "les packs" ont un message très différent ("facile à mettre à jour, pas de majeur Leap suit une philosophie similaire, donc nous voulions un schéma de version pour refléter les MVS.

Mais openSUSE avait déjà eu des versions commençant par 12, donc nous ne pouvions pas synchroniser avec SLE. C'est de là que vient 42.x. Cela nous a donné la possibilité d'établir une relation avec les versions SLE (Version SLE+ 30 = version Leap), reflètent la nature majeure / mineure des versions Leap, et éviter les conflits avec les numéros de version que nous avions déjà utilisés.
Le choix de 42 a été vu comme un clin d'œil humoristique à la réponse de [la « Grande Question sur la Vie, l'Univers et le Reste » de la série de romans de science-fiction "Le Guide du voyageur galactique" de l'écrivain anglais Douglas Adams (The Hitchhiker's Guide to the Galaxy)](https://fr.wikipedia.org/wiki/OpenSUSE#Les_origines) et les premiers numéros de version de SuSE Linux et YaST (4.2 et 0,42 respectivement).

Le plan était donc pour la prochaine version de Leap être 43 avec sa version alignée avec SLE 13, suivie de Leap 43.1 (avec SLE 13 SP1), puis 43.2 (avec SP2), etc.

Cependant, comme tous les bons plans, les choses changent.

## SUSE a décidé que sa prochaine version de SLE sera 15, pas 13. ##

En apprenant les plans de SUSE, le Board et l'équipe de publication de Leap ont considéré les options possibles. Cela inclus ignorer les changements à SLE et libérer Leap 43 comme prévu, au prix du lien entre les versions SLE et les versions Leap. Leap 45 a été également considéré, comme l'étaient certaines idées franchement hilarantes qui ont été faite. Je m'inquiète pour ma propre santé mentale et celle de mes collègues collaborateurs.

Après avoir examiné les avantages et les inconvénients de toutes les options, la décision a été que Leap 15 sera notre prochaine version.

La décision de SUSE d'ignorer SLE 13 et 14 nous a donné une occasion parfaite de synchroniser avec les versions SLE comme nous avons toujours voulu à l'origine avec Leap. C'est une opportunité que nous ne pourrons pas prendre si facilement à partir de maintenant si nous avions continué avec versions actuelles de Leaps.

Il y a seulement quelques paquets dans notre distribution qui font référence à 42.x, et ils devraient être facilement manipulés dans le cadre d'un zypper `dup`, donc nous ne sommes pas préoccupés par cette décision impactant les utilisateurs.
