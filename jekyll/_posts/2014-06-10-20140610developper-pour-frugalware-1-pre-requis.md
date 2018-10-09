---
title: Développer pour Frugalware 1, pré-requis
date: 2014-06-10 22:51
layout: post
---
Je rassemble les differentes étapes pour contribuer a frugalware qu'on
peut trouver sur le wiki
[(https://wiki.frugalware.org/index.php/Category:Développer).](https://wiki.frugalware.org/index.php/Category:Développer)
Ceci est la partie 1, vous trouverez la suite, [**Développer pour
Frugalware: 2 création de paquets, entraînons nous avec un exemple
simple**](http://passiongnulinux.tuxfamily.org/?p=32) et [**Développer
pour Frugalware: 3 faire un patch
git**](http://passiongnulinux.tuxfamily.org/?p=33).  

Développer pour Frugalware
--------------------------

Comment devenir un développeur? “Soyez impliqués ! :) Téléchargez le FST
(Arbre des sources de Frugalware) en utilisant la commande **repoman
upd**, qui est disponible avec le paquet pacman-tools. Pour commencer à
jouer avec les scripts Frugalbuilds, pour voir la structure,
referez-vous au répertoire /docs/skel. Essayez de les améliorer, ou
écrivez en un nouveau pour un programme non supporté. Puis ouvrez une
demande “feature request” sur le Système de Suivi des Bugs et attachez
vos correctifs à cette demande. A partir de là, tout viendra
naturellement à vous :)” Que font les développeurs? “En bref, ce qu'ils
veulent, s'ils sont réglo. Il peuvent maintenir des paquets: les
construire si de nouvelles versions sont disponibles et mettre à jour
les scripts FrugalBuild afin qu'ils fonctionnent correctement avec les
nouvelles versions. Ils peuvent contribuer en créant des scripts pour
des paquets jusqu'alors non inclus. Ils peuvent écrire des
documentations, corriger des bugs, fournir du support, ou n'importe quoi
d'autre en rapport avec la communauté Frugalware. Si vous souhaitez nous
aider, mais ne souhaitez pas faire de modifications, vous pouvez
contribuer en traduisant Frugalware dans votre langue ou une autre. Et
évidement, nous acceptons les dons avec joie :)” Qui développe
Frugalware? “Un groupe étonnant de volontaires, qui sont motivés par les
utilisateurs pour faire cela. Ils le font également comme passe-temps,
et ils travaillent toujours à avoir leurs connaissances à jour pour
rendre Frugalware encore meilleur pour vous.”  

<span dir="auto">Création de paquets</span>
===========================================

La création de paquets (ou empaquetage) se fait grâce à des scripts que
l'on appelle des FrugalBuild. Grâce à ces scripts, l'application nommé
[makepkg](https://wiki.frugalware.org/index.php/Makepkg_%28Fran%C3%A7ais%29 "Makepkg (Français)"),
va pouvoir télécharger les sources du logiciel que l'on veut empaqueter
pour les compiler et simuler une installation des binaires obtenus, tout
ça dans un environnement matrice que l'on appelle le chroot. Si tout se
passe bien, makepkg créera l'archive .fpm qui contiendra les fichiers
binaires obtenus après la compilation pour que le logiciel soit installé
grâce à
[pacman-g2](https://wiki.frugalware.org/index.php/Pacman-g2_%28Fran%C3%A7ais%29 "Pacman-g2 (Français)").
Cependant, pour créer un paquet, il faut des pré-requis.  

Pré-requis
----------

### Obtenir sa copie du FST

Installation des logiciels requis Tout d'abord vous aurez au moins
besoin de git et des outils inclus dans pacman-tools

<div style="text-align: left;">

<div style="float: left;">

[![Root terminal
48px.png](https://wiki.frugalware.org/images/c/c3/Root_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:Root_terminal_48px.png){.image}

</div>

<div>

\# pacman-g2 -S pacman-tools git lynx

</div>

</div>

Configuation de Sudo et Makepkg Il est préférable (et plus pratique)
d'utiliser makepkg avec sudo.

<div style="text-align: left;">

<div style="float: left;">

[![Root terminal
48px.png](https://wiki.frugalware.org/images/c/c3/Root_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:Root_terminal_48px.png){.image}

</div>

<div>

\# pacman-g2 -S sudo

</div>

</div>

Editez le fichier /etc/sudoers. Vous pouvez créer un groupe
d'utilisateurs nommé “devels” et y mettre votre compte utilistaeur dans
ce groupe, il suffira alors d'ajouter au fichier sudoers:

      %devels ALL=NOPASSWD:/usr/bin/makepkg

Vous pouvez également donner les droits d'utiliser makepkg avec sudo à
votre utilisateur, dans ce cas ce sera

      nom_d'utilisateur ALL=NOPASSWD:/usr/bin/makepkg

Attention plus de mot de passe vous sera demandé pour éxécuter la
commande makepkg en tant qu'utilisateur. Idéalement, il est bien d'avoir
sa propre copie du FST (Frugalware Source Tree), c'est-à-dire, les
sources du dépôt current. Ca vous permettra de voir les FrugalBuild
qu'il y a et cela vous permettra de vous en inspirer. Mais il y a deux
façons pour avoir sa copie : Copie du FST dans le dossier par défaut
Vous pouvez l'obtenir en tant que root en tapant :

<div style="text-align: left;">

<div style="float: left;">

[![Root terminal
48px.png](https://wiki.frugalware.org/images/c/c3/Root_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:Root_terminal_48px.png){.image}

</div>

<div>

\# repoman upd

</div>

</div>

Ceci va créer la copie du FST dans le dossier par défaut:

      /var/fst

Le dossier par défaut est défini dans le fichier

      /etc/repoman

<small>Vous pouvez changer le dossier par défaut, mais préférez alors la
seconde solution.</small> Copie du FST dans un dossier personnel Vous
pouvez l'obtenir en tant qu'utilisateur en créant le fichier
.repoman.conf dans votre répertoire /home pour lui ajouter cette ligne :

      fst_root=~/git

Comme ça, les sources iront directement dans le répertoire \~/git, ou un
répertoire que vous aurez choisi en tapant :

<div style="text-align: left;">

<div style="float: left;">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ repoman upd

</div>

</div>

A noter que vous pouvez également directement obtenir une copie du dépôt
git avec:

<div style="text-align: left;">

<div style="float: left;">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ git clone
<http://frugalware.org/git/pub/frugalware/frugalware-current> current

</div>

</div>

<span dir="auto">Cloner le dépôt git</span>
===========================================

Cloner le dépôt git de Frugalware
---------------------------------

Nous allons vous montrez comment cloner le depôt git pour avoir une
copie du dépôt en local. Dans notre exemple, nous prendrons le dépôt
**frugalware-current** Il existe d'autres dépôts dont une liste est
disponible ici: <http://git.frugalware.org/gitweb/gitweb.cgi> Créer un
dossier dans votre \$HOME puis placez vous dedans avec le terminal:

<div style="text-align: left;">

<div style="float: left;">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ cd \~/git

</div>

</div>

-   Si vous êtes développeur Frugalware, vous avez donc une un accès à
    genesis, vous pourrer cloner de cette façon

<div style="text-align: left;">

<div style="float: left;">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ git clone
devil505@git.frugalware.org:/home/ftp/pub/frugalware/frugalware-current
current

</div>

</div>

-   Si vous êtes juste contributeur, vous pouvez cloner en tant
    qu'anonyme

<div style="text-align: left;">

<div style="float: left;">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ git clone
<git://git.frugalware.org/pub/frugalware/frugalware-current> current

</div>

</div>

Ensuite on paramètre notre copie du dépôt:

<div style="text-align: left;">

<div style="float: left;">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ cd currentgit config user.name "Pseudo" git config user.email
adresse@email.com git config remote.origin.receivepack "sudo -u repo
git-receive-pack" git config branch.master.rebase true

</div>

</div>

Pour mettre à jour le dépôt:

<div style="text-align: left;">

<div style="float: left;">

[![User terminal
48px.png](https://wiki.frugalware.org/images/4/43/User_terminal_48px.png)](https://wiki.frugalware.org/index.php/File:User_terminal_48px.png){.image}

</div>

<div>

\$ git pull

</div>

</div>

Et ensuite ?
------------

-   Les développeurs retrouveront leur copie locale du dépôt :D

<!-- -->

-   Les contributeurs pourront se servir de cette copie locale pour
    commençer à [faire un patch
    git](https://wiki.frugalware.org/index.php/Faire_un_patch_git "Faire un patch git")
    pour proposer leurs contributions au projet Frugalware.

Ensuite on s'attaque au frugalbuild dans le prochain article.
