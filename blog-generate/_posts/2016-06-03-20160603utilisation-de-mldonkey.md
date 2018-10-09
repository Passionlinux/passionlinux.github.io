---
title: Utilisation de MLdonkey
date: 2016-06-03 09:48
layout: post
---

<div class="main">

<div class="chapo surlignable">

Mldonkey est un client P2P multi-plateforme, pour le réseau edonkey2000
mais aussi bittorrent, fasttrack et bien d’autres. Mldonkey est pour moi
le meilleur client donkey sous linux. Bien moins gourmand que amule, il
ne nécessite pas d’interface graphique pour continuer à télécharger, et
il existe de très beaux clients graphique notamment sancho (voir plus
bas).

</div>

<div class="texte surlignable">

### Installer mldonkey {#outil_sommaire_0 .spip}

Installez le paquet **mldonkey-server** (activez auparavant les dépôts
universe et multiverse sous Ubuntu, pour debian il n’y a rien a
faire...) Lors de l’installation une série de questions vous sera posée.
Répondez tout simplement aux questions en utilisant les choix par
défauts. Nous configurerons par la suite le démon de façon manuelle.
NB : En effet lorsque j’ai essayé de configurer mldonkey en utilisant le
script d’installation du paquet, il semble que mes choix n’aient pas été
enregistrés. Je préfère donc vous expliquer comment configurer le démon
manuellement.  

### [ ](http://passiongnulinux.tuxfamily.org/spip/spip.php?article32#outil_sommaire "Sommaire"){.sommaire_ancre}Premier lancement {#outil_sommaire_1 .spip}

Nous venons d’installer mldonkey. Vous ne trouverez pas d’entrée dans le
menu applications concernant mldonkey puisque c’est un démon qui démarre
au boot de votre ordinateur. Ensuite vous utiliserez un client graphique
qui permettra de contrôler ce démon. Pour lancer le démon tapez :
`sudo /etc/init.d/mldonkey-server restart`{.spip_code dir="ltr"}  

### Lancement automatique {#outil_sommaire_2 .spip}

Afin de ne pas à avoir à lancer le démon à chaque démarrage, il vous
faut éditer le fichier */etc/default/mldonkey-server* et mettre le
paramètre **LAUNCH\_AT\_STARTUP** à **true**. Si pour une raison ou pour
une autre vous voulez couper ou rallumer le démon mldonkey faites :
**Sous Feisty (en mode utilisateur) :** Pour le démarrer :
`mlnet > /dev/null 2>&1 &`{.spip_code dir="ltr"} Pour le stopper :
`sudo killall mlnet`{.spip_code dir="ltr"} **En mode démon :** Pour le
démarrer : `sudo /etc/init.d/mldonkey-server start`{.spip_code
dir="ltr"} Pour le stopper : code&gt;sudo /etc/init.d/mldonkey-server
stop  

### Configuration du démon mldonkey {#outil_sommaire_3 .spip}

### Configuration des répertoires {#outil_sommaire_4 .spip}

Comme tout bon logiciel de P2P, mldonkey a besoin de deux répertoires
pour fonctionner : \* Un répertoire **temp** dans lequel il stockera les
fichiers en cours de téléchargement. \* Un répertoire **incoming** dans
lequel il placera les fichiers téléchargés. Par défaut ces deux
répertoires se situent dans */var/lib/mldonkey*, ce qui n’est pas très
pratique. Nous allons donc modifier le démon afin qu’il place ces
répertoires dans votre dossier personnel. Avant de toucher au fichier de
configuration du démon nous devons éteindre celui ci :
`sudo /etc/init.d/mldonkey-server stop`{.spip_code dir="ltr"} Maintenant
nous allons éditer le fichier */var/lib/mldonkey/downloads.ini*  
Il faut trouver la ligne contenant les paramètres
**incoming\_directory** et **temp\_directory**, puis les remplacer par
les répertoires de votre choix : Ce qui donne par exemple :

<div class="spip_code" dir="ltr">

`temp_directory = "/home/mondossierpersonnel/.mldonkey/temp" (* The directory where downloaded files should be moved after commit *) incoming_directory = "/home/mondossierpersonnel/.mldonkey/fini"`

</div>

Bien sûr nous devons créer ces deux répertoires. **Sous Feisty (en mode
utilisateur)** Les dossiers se trouve dans
*/home/mondossierpersonnel/.mldonkey*, le fichier à éditer est alors
*/home/mondossierpersonnel/.mldonkey/downloads.ini  
*  
Trouvez la section pour les fichiers temporaires :
`temp_directory = "/home/mondossierpersonnel/.mldonkey/temp"`{.spip_code
dir="ltr"} Puis la section pour les répertoires de partage et de
classement :

<div class="spip_code" dir="ltr">

` shared_directories = [ {     dirname = "/home/mondossierpersonnel/.mldonkey/shared"    ## dossier partagé strategy = only_directory priority = 0 }; {     dirname = shared strategy = all_files priority = 0 }; {     dirname = "/home/mondossierpersonnel/.mldonkey/incoming"    ## dossier fichiers finis edonkey strategy = incoming_files priority = 0 }; {     dirname = "/home/mondossierpersonnel/.mldonkey/incoming"    ## dossier fichiers finis bittorrent strategy = incoming_directories priority = 0 };] `

</div>

### Configuration des droits {#outil_sommaire_5 .spip}

Pour des raisons de sécurité, le démon *mldonkey* est lancé par
l’utilisateur *mldonkey* appartenant au groupe *mldonkey*. Pour que ce
dernier puisse aller écrire dans nos deux répertoires fraîchement crées,
il faut modifier les droits : On attribue les dossiers de *mldonkey* au
groupe *mldonkey* :
`sudo chgrp -R mldonkey /home/mondossierpersonnel/.mldonkey/*`{.spip_code
dir="ltr"} Enfin on autorise seulement les utilsateurs du groupe
*mldonkey* à lire et modifier ces répertoires :
`sudo chmod 660 -R /home/mondossierpersonnel/.mldonkey/*`{.spip_code
dir="ltr"} Comme l’utilisateur *mldonkey*, appartient également au
groupe *mldonkey* et que le démon est lancé par l’utilisateur
*mldonkey*, ce dernier pourra donc lire et écrire dans les répertoires
définis. **Sous Feisty (en mode utilisateur) cette étape n’est plus
obligatoire.** Une commande se révèle utile pour vérifier le bon
positionnement des droits :
`sudo -u mldonkey /usr/bin/mlnet.`{.spip_code dir="ltr"} Un message
d’erreur explicite *« check rights »* apparaît si les droits ne
permettent pas à mldonkey d’écrire dans son répertoire.  

### Installation d’un client graphique {#outil_sommaire_6 .spip}

Comme je l’ai dis mldonkey n’est que le cœur du système de
téléchargement. Pour pouvoir le piloter facilement il vous faut un
client graphique qui se connectera au démon et lui enverra des
commandes. L’avantage est que vous pouvez fermer le client graphique, le
démon lui, continue à télécharger. Donc vous pouvez fermer votre session
gnome, et continuer à télécharger. Un autre avantage est que vous pouvez
configurer un PC dédié uniquement au téléchargement sur lequel tourne le
démon, et piloter le téléchargement depuis un autre PC, ou même du
bureau. Donc en résumé par exemple, un PC dans le salon qui fait du
bruit et qui télécharge, un pc dans la chambre depuis lequel on lance
les téléchargements et qu’on peut éteindre la nuit. A ce propos,
mldonkey fourni nativement une **interface web** pour piloter le démon.
Elle est accessible par défaut sur le port 4080 (vous pouvez le changer
dans la configuration de mldonkey) de la machine qui héberge le démon
(vous pouvez donc accéder à votre interface web à l’adresse
*<http://localhost:4080/>*). Si vous avez défini un mot de passe à
l’installation, un identifiant/mot de passe vous sera demandé à la
connexion. L’identifiant est **admin** et le mot de passe est celui que
vous avez rentré. Si vous voulez l’utilisez à l’extérieur, vous pouvez
facilement définir un reverse proxy dans apache qui pointera par exemple
sur le dossier *<http://monsite/mldonkey>*. Comme ca, depuis internet,
vous pouvez lancer des téléchargements.  

### mlgui {#outil_sommaire_7 .spip}

Le premier client graphique que je vous présente est le plus simple à
installer.  
Il suffit d’installer le paquet **mldonkey-gui** Puis lancez le client
avec la commande : `mlgui`{.spip_code dir="ltr"}  

### Sancho {#outil_sommaire_8 .spip}

Il existe plusieurs interfaces graphiques, ma préférée est
**[sancho](http://sancho-gui.sourceforge.net/){.spip_out}** Ce dernier
devrait devenir le futur client graphique officiel à mldonkey. C’est une
interface gtk2 avec un icône dans le systray. **Installation** Récupérez
l’archive de **sancho**
[ici](http://sancho-gui.sourceforge.net/download.phtml#linux-gtk){.spip_out}
Choisissez la dernière version, aujourd’hui (27/04/2008) c’est :
**sancho-0.9.4-58-linux-gtk.sh**. Cette version fonctionne sur Hardy
i386 et x86\_64. Nous supposerons que l’archive est téléchargée dans
votre dossier personnel. Créez le répertoire d’installation :
`sudo mkdir /usr/local/sancho`{.spip_code dir="ltr"} Maintenant
exécutons le script d’installation :
`sudo sh ~/sancho-0.9.4-58-linux-gtk.sh`{.spip_code dir="ltr"} Le script
vous demande où le logiciel doit être installé :
`Extract to directory [<sancho-0.9.4-58-linux-gtk>]:`{.spip_code
dir="ltr"} Taper donc */usr/local/sancho* Sancho est installé. Nous
allons lui créer une entrée dans le menu **Applications ? internet.**
Créez le fichier */usr/share/applications/sancho.desktop* et mettez-y
les lignes suivantes :

<div class="spip_code" dir="ltr">

`[Desktop Entry] Name=Sancho Comment=Sancho Exec=/usr/local/sancho/sancho Icon=/usr/local/sancho/distrib/sancho-32.xpm Terminal=false Type=Application StartupNotify=false Categories=Application;Network;`

</div>

Les fichiers de configuration de sancho dans votre dossier personnel
appartiennent à **root** (car vous avez lancé l’installation en tant
qu’administrateur). Nous allons donc remettre le bon propriétaire
(vous !) à ces fichiers :
`sudo chown -R utilisateur:utilsateur ~/.sancho|`{.spip_code dir="ltr"}
(remplacez utilisateur par votre **login** bien sûr) Vous pouvez
maintenant démarrer sancho depuis le menu **applications ? internet.**
**Mettre sancho en français** Récupérer le fichier de traduction
**sancho\_fr\_FR.properties** et copiez ce fichier dans le répertoire
*.sancho/* situé dans votre dossier personnel Si vous êtes sous Feisty,
le fichier est déjà présent après l’installation. Démarrez sancho, allez
dans **Tools ? Preferences**. Dans la section **sancho:main**, dans
l’onglet **General**, là où il y a écrit **« Locale specific
sancho\*.properties file »**, choisissez **fr\_FR** dans le menu
déroulant puis redémarrez l’application. Vous pouvez d’ailleurs
supprimer les autres fichiers de langue que vous n’utilisez pas du
répertoire * /.sancho*  
Les fichiers de langues sont du layout *sancho\_xx\_XX.properties*  
par exemple : *sancho\_pl\_PL.properties* pour le polonais **Dernière
étape : se connecter à un serveur** La dernière étape et de se connecter
à un serveur pour pouvoir lancer une recherche. Cliquez sur l’onglet
**serveur**. En haut a droite cliquez sur la planète avec une croix
verte intitulé **« ajouter un fichier serveur.met »** entrez-y l’adresse
d’un fichier de serveur .met que vous récupèrerez sur des sites comme
*<http://ed2k.2x4u.de>* Il devrait aussi récupérer une liste d’autre
serveurs. **NB** : Il est plus sûr de désactiver les options de
récupération automatique des serveurs afin d’éviter de recevoir des
serveurs espions. Dans ce cas une liste de serveurs sûrs doit être
récupérée en téléchargeant un des fichiers « .met » ci-dessus. Une fois
connecté lancez une recherche. **Lancement du démon avec l’interface
graphique Sancho sous Feisty** Pour lancer le démon automatiquement au
démarrage de Sancho et le couper à la fermeture de Sancho (a la manière
de Amule) :
`mlnet -start_gui true -mldonkey_gui /usr/local/sancho/sancho`{.spip_code
dir="ltr"} Puis vous pouvez simplement lancer **mlnet**, le serveur
lancera toujours Sancho N’oubliez pas d’autorisez Sancho a couper le
serveur mldonkey lorsque vous quittez : **outils / préférences** : \*
optional core executable : mlnet  
\* cocher Kill spawned core when exiting sancho Pour revenir a la
configuration par defaut, éditez le fichier
*/home/mondossierpersonnel/.mldonkey/download.ini* et cherchez la ligne
**mldonkey\_gui** **Filtrage des IP** Pour Feisty : Vous pouvez vous
servir d’un **ipfilter.dat** en le placant dans le dossier* /.mldonkey*
Pour la compatibilité d’un fichier ipfilter.dat : \* récupérer un
fichier :Ipfilter.dat ;  
\* éditez ce fichier et supprimer toutes les lignes (avec les \#) avant
la série de chiffre . Vous pouvez aussi utiliser grep pour filtrer les
lignes commentées (avec les \#) :
`grep -v ^# ipfilter.dat > ipfilter.p2p`{.spip_code dir="ltr"} **Ports
utilisés** Si vous avez installé Sancho, cliquer sur l’onglet console et
rentrer la commande **portinfo**, le résultat donne pour moi :  

<table class="spip">
<tbody>
<tr class="row_odd odd">
<td>
Portinfo
</td>
</tr>
<tr class="row_even even">
<td>
Network
</td>
<td>
Port
</td>
<td>
Type
</td>
</tr>
<tr class="row_odd odd">
<td>
----
</td>
</tr>
<tr class="row_even even">
<td>
BitTorrent
</td>
<td>
6882
</td>
<td>
client\_port TCP
</td>
</tr>
<tr class="row_odd odd">
<td>
BitTorrent
</td>
<td>
6881
</td>
<td>
tracker\_port TCP
</td>
</tr>
<tr class="row_even even">
<td>
Core
</td>
<td>
4080
</td>
<td>
http\_port
</td>
</tr>
<tr class="row_odd odd">
<td>
Core
</td>
<td>
4000
</td>
<td>
telnet\_port
</td>
</tr>
<tr class="row_even even">
<td>
Core
</td>
<td>
4001
</td>
<td>
gui\_port
</td>
</tr>
<tr class="row_odd odd">
<td>
Donkey
</td>
<td>
4662
</td>
<td>
client\_port TCP
</td>
</tr>
<tr class="row_even even">
<td>
Donkey
</td>
<td>
4666
</td>
<td>
client\_port UDP
</td>
</tr>
<tr class="row_odd odd">
<td>
Donkey
</td>
<td>
14934
</td>
<td>
overnet\_port TCP UDP
</td>
</tr>
<tr class="row_even even">
<td>
Donkey
</td>
<td>
4672
</td>
<td>
kademlia\_port UDP
</td>
<td>
</td>
</tr>
</tbody>
</table>
Pour changer les ports sous Feisty : ATTENTION : N’éditer pas ces
fichiers si le démon est lancé. éditez le
fichier* /.mldonkey/nomduprotocole.ini  
*  
avec nomduprotocole : \* Pour Edonkey, Overnet, Kademlia : éditer le
fichier /home/mondossierpersonnel/.mldonkey/donkey.ini. \* Pour
Bittorrent : éditer le fichier
/home/mondossierpersonnel/.mldonkey/bittorent.ini. (?bittorrent.ini)
etc... **Integration à Firefox** L’extension pour la prise en charge
directe est disponible pour le protocole edonkey et bittorrent dans ce
dossier :
*/usr/share/doc/mldonkey-server/distrib/ed2k\_mozilla/mldonkey\_protocol\_handler-1.8.xpi
.*  

### Un système d’analyse anti-virus et d’alerte {#outil_sommaire_9 .spip}

Dernier raffinement, vous pouvez vous créer un script (shell, php, perl,
...) qui sera lancé au démarrage et à la récupération d’un fichier. Cela
permet d’avertir l’utilisateur, de scanner avec un anti-virus le fichier
récupéré, et même de le sortir de l’incoming, pour éviter les problèmes
d’upload. Allez voir dans downloads.ini, jusqu’a la commande
file\_completed. Finalement, bon téléchargements. Mais n’oubliez pas de
ne pas télécharger d’oeuvres soumises au droit d’auteur. Il existe des
millions d’oeuvres libres de droits alors autant en profiter.

</div>

Voir en ligne : [Documentation
UBUNTU.FR](http://doc.ubuntu-fr.org/mldonkey){.spip_out}

</div>

<footer>
<div class="ps surlignable">

P.-S.
-----

Attention : Nous vous rappelons qu’il est interdit d’utiliser ce
logiciel à des fins illégales (piratage, contrefaçon ou toute autre
activité étant considérée hors-la-loi par les lois en vigueur dans votre
pays de résidence).

</div>

</footer>

