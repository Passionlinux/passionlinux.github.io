---
title: Développer pour Frugalware 3, faire un patch git
date: 2014-06-11 22:58
layout: post
---

Faire un patch git
------------------

Préparation
-----------

Consulter la page sur comment [Cloner le dépôt
git](https://wiki.frugalware.org/index.php/Cloner_le_d%C3%A9p%C3%B4t_git "Cloner le dépôt git")

Par defaut, pour la suite des évènement, c'est Vim qui est considéré
comme l'éditeur de texte par défaut. Pour passer à nano (plus simple
d'emploi) il faut faire :

<div style="text-align:left">

<div style="float:left">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ nano \~/.gitconfig

</div>

</div>

et ajouter

      [core]  editor = nano 

Réalisation du patch
--------------------

1.Naviguez dans l'arborescence de votre git (/home/&lt;nom
utilisateur&gt;/git/current/source/dossier groups= de votre
FrugalBuild)  
2.Nouveau dossier du nom de votre programme  
3.Insérez dans ce dossier votre FrugalBuild  
4.Ouvrez un terminal dans celui ci puis :

<div style="text-align:left">

<div style="float:left">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ fblint -v

</div>

</div>

pour voir s'il n'y a pas d'erreur.

<div style="text-align:left">

<div style="float:left">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ git add FrugalBuild

</div>

</div>

<div style="text-align:left">

<div style="float:left">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ repoman rec

</div>

</div>

On vérifie le nom du paquet et on rajoute

      * new package 

[![Gitpatch-capture.png](https://wiki.frugalware.org/images/9/98/Gitpatch-capture.png)](https://wiki.frugalware.org/index.php/File:Gitpatch-capture.png){.image}

<div style="text-align:left">

<div style="float:left">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ git log

</div>

</div>

pour avoir le hash au-dessus de \* new package

<div style="text-align:left">

<div style="float:left">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ git format-patch &lt;hash&gt;

</div>

</div>

On obtient un fichier de la forme :

      0001-NomDuPaquet-VersionDuPaquet-Architecture.patch 

et c'est ce fichier qu'il faut adresser sur la Mailing-List
-devel ![smile](inc/img/smileys/smile.gif "smile")

Il est possible, également, d'obtenir le hash de votre commit via la
commande suivante :

<div style="text-align:left">

<div style="float:left">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ git format-patch HEAD\~1

</div>

</div>

et vous obtiendrez également le fichier .patch comme mentionné plus
haut.
