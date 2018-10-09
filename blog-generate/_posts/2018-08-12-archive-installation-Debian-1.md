---
title: "Installation Debian 1"
date: 2017-12-02T20:06:42+01:00
layout: post
---
Ce que je fais après l'installation de ma Debian

J'aime bien lire les blogs de mes compatriotes, généralement je lis 
surtout ce qui touche a linux et le logiciel libre. Je voulais faire ce 
billet depuis quelque temps, en faite depuis que <a href="http://www.parigotmanchot.fr/2016/06/07/apres-installation-ubuntu-16-04-lts/">Gilles a posté le sien sur son blog</a>.

Il commence par:
<blockquote>Comme souvent en ce moment, jai installé la dernière 
version dUbuntu : la 16.04 LTS (Long Term Support), appelée Xenial 
Xerus. Comme ma dernière liste dinstallation date un peu et que jai 
changé dordinateur, je remets ici pour mémoire ce que jai fait après 
linstallation de base.</blockquote>

Alors avec debian je n'ai pas autant de raison de réinstaller, en effet 
les sorties d'une stable c'est tout les deux ans alors qu'ubuntu c'est 
tout les 6mois, a part si on installe que les LTS d'ubuntu et la ça 
revient au même qu'une debian. Bref, ça nempêche pas que le temps fait 
que joublie certaine pratique, que je dois ensuite regarder sur ce blog
 pour trouver les différents penses bête et ensuite les mettre en 
pratique. Il est peut être temps que je récapitule dans un seul billet 
les principales actions que je fais a chaque nouvelle debian.

Pour l'installation, je ne change pas, je prend normalement une <a href="https://www.debian.org/distrib/netinst#smallcd">net-install</a> ou un <a href="https://www.debian.org/CD/torrent-cd/">DVD d'installation</a>
 si je sais que je dois en installer plusieurs. Normalement je ne prend 
que le Amd64 mais j'ai encore deux vieux coucous en i386. Ensuite je <a href="http://passiongnulinux.tuxfamily.org/?p=53">lance l'installation</a>,
 je suis les étapes que je connais par cur depuis le temps. C'est 
simple, rapide et comme Debian nous habitue a ne pas changer pour 
changer, on est pas surpris par cette installation.

<hr>

Au premier démarrage, je change le fichier /etc/apt/source.list avec <a href="https://fr.wikipedia.org/wiki/GNU_nano">nano</a>
 pour rajouter les dépots nonfree et contrib ainsi que les depots 
sources de sid, puis surtout je retire (je commente #) la ligne du 
cd/dvd..

<code># nano /etc/apt/sources.list</code>

Le fichier d'origine:
<pre>deb cdrom:[Debian GNU/Linux etc...
# Debian Jessie, dépôt principal
deb http://httpredir.debian.org/debian/ jessie main
# Debian Jessie, mises-à-jour de sécurité
deb http://security.debian.org/ jessie/updates main
# Debian Jessie, mises-à-jour "volatiles"
deb http://httpredir.debian.org/debian/ jessie-updates main</pre>
après:
<pre># Debian Jessie, dépôt principal + paquets non libres 
deb http://httpredir.debian.org/debian/ jessie main contrib non-free 
# Debian Jessie, mises-à-jour de sécurité + paquets non libres 
deb http://security.debian.org/ jessie/updates main contrib non-free 
# Debian Jessie, mises-à-jour "volatiles" + paquets non libres 
deb http://httpredir.debian.org/debian/ jessie-updates main contrib non-free</pre>
je rajoute aussi les <em>backports</em>:
<pre># Debian Jessie, dépôt de rétroportages ("backports") 
deb http://httpredir.debian.org/debian jessie-backports main contrib non-free</pre>
Voir le <a href="http://passiongnulinux.tuxfamily.org/?p=17">billet qui en parle</a>.

J'y reviendrais dessus car par la suite j'installe deux ou trois paquets
 venant de backports.

Une fois fait, il faut a tout pris lancer une mise a jour des dépôts 
(ils ont changé du coup faut que notre système en soit informé):

<code># apt-get update</code>

Suivit d'une mise a jour du système:

<code># apt-get upgrade</code>

Bien que dans mon cas j'utilise a tout va

<code># apt-get dist-upgrade</code>

Noter qu'on peut tout a fait raccorder les deux commandes en une seule a condition de mettre entre elle un <em>&amp;&amp;</em>:

<code># apt-get update &amp;&amp; apt-get dist-upgrade</code>

Je fini par accepter les mises a jour.

Une fois cette étape fini, ce n'est que la première, je rajoute les 
firmwares non-libre qui me sont obligatoire pour profiter de mes deux 
écrans:

<code># apt-get install firmware-linux-nonfree</code>

Je rajout aussi un firmware pour mon Ethernet, ce n'est pas obligatoire 
mais a chaque mise a jour du kernel j'ai des messages qui me le demande,
 je l'installe surtout car j'ai aussi le wifi sur un autre pc qui 
fonctionne avec ce driver...:

<code># apt-get install firmware-realtek</code>

Pour le reste des firmwares, on peut aller par <a href="http://passiongnulinux.tuxfamily.org/?p=22">la</a>.
 Une bonne chose de faite, je me retrouve en face de mes deux écrans qui
 me donnent chacun une bonne résolution.

Maintenant, on va s'attaquer au mutiarch, plus haut j'ai dis que mon pc 
est en 64, or pour certaines applications comme wine, il nous faut les 
libs de i368. Pour ce faire, c'est très simple, on rajoute a notre 
système, l'architecture i386, on peut bien sur ajouter n'importe quelle 
architecture disponible sous Debian.

<code># dpkg --add-architecture i386 &amp;&amp; apt-get update</code>

Pour en savoir plus, c'est par <a href="http://passiongnulinux.tuxfamily.org/?p=23">la</a>.

Allez, le plus gros est passé, maintenant il reste a installer les 
paquets. Je commence par installer apt-listbugs, qui sert a prévenir des
 bugs ou failles éventuels, des fois je l'installe avant tout chose dès 
le début, et parfois seulement après avoir effectué les actions vu 
précédemment.

<code># apt-get install mc apt-listbugs devscripts mldonkey-server kde-full icedove-l10n-fr icedove filezilla</code>

Alors dans l'ordre,
<ul><li><a href="https://fr.wikipedia.org/wiki/Midnight_Commander"><strong>mc</strong></a>
 est un couteau suisse, il fait gestionnaire de fichier, éditeur et 
plein d'autre chose, c'est un utilitaire qui nous permet d'éviter de 
saisir les commandes dans une console.</li></ul>


<ul><li><a href="https://packages.debian.org/jessie/devscripts"><strong>Devscripts</strong></a>
 est un ensemble de scripts pour faciliter la vie du mainteneur Debian, 
je m'en sers principalement pour me faire des paquets plus récent.</li><li><a href="https://fr.wikipedia.org/wiki/MLDonkey"><strong>mldonkey-server</strong></a>
 est une application destinée au partage de fichiers en pair à pair 
multiréseaux et libre. Elle fonctionne comme application backend sur de 
nombreuses plates-formes. Elle peut être contrôlée au moyen d'une 
interface utilisateur fournie par un des nombreux frontaux séparés, y 
compris une interface Web, l'interface Telnet et plus d'une douzaine de 
logiciels clients natifs.</li></ul>


<ul><li><a href="https://packages.debian.org/jessie/kde-full"><strong>kde-full</strong></a> est l'ensemble des logiciel contenu dans kde.</li><li><a href="https://fr.wikipedia.org/wiki/Renommage_des_applications_de_Mozilla_par_Debian"><strong>icedove</strong></a> est la version Debian de <a href="https://fr.wikipedia.org/wiki/Mozilla_Thunderbird"><strong>Thunderbird</strong></a> et icedove-l10n-fr est la traduction FR.</li></ul>


<ul><li><b><a href="https://fr.wikipedia.org/wiki/FileZilla">FileZilla</a> </b>est un <a title="Client-serveur" href="https://fr.wikipedia.org/wiki/Client-serveur">client</a> <a title="File Transfer Protocol" href="https://fr.wikipedia.org/wiki/File_Transfer_Protocol">FTP</a>, <a class="mw-redirect" title="File Transfer Protocol over SSL" href="https://fr.wikipedia.org/wiki/File_Transfer_Protocol_over_SSL">FTPS</a> et <a class="mw-redirect" title="SSH file transfer protocol" href="https://fr.wikipedia.org/wiki/SSH_file_transfer_protocol">SFTP</a>, développé sous la <a title="Licence publique générale GNU" href="https://fr.wikipedia.org/wiki/Licence_publique_g%C3%A9n%C3%A9rale_GNU">licence publique générale GNU</a>. Il existe également un logiciel de <a title="Client-serveur" href="https://fr.wikipedia.org/wiki/Client-serveur">serveur</a> FTP du nom de <a title="FileZilla Server" href="https://fr.wikipedia.org/wiki/FileZilla_Server">FileZilla Server</a>. Le logiciel est disponible pour Windows, Mac OS X et Linux.</li></ul>

Ensuite, je rajoute mes applications venant de backport, bien sur ils 
sont aussi dans les dépôts standard mais dans une version un peu 
vieillotte...

<code># apt-get -t jessie-backports install 0ad minetest wine32</code>
<ul><li><a href="https://fr.wikipedia.org/wiki/0_A.D."><strong>0ad</strong> - Empires Ascendant</a> est un jeu vidéo de stratégie en temps réel (RTS) historique en 3D développé et édité par Wildfire Games.</li></ul>


<ul><li><a href="http://www.minetest.net/"><strong>Minetest</strong></a> 
est aussi un jeu, cette fois de layout bac à sable en multijoueur, le jeu 
propose au joueur d'incarner un personnage se mouvant dans un univers en
 trois dimensions, représenté par des cubes, la représentation du décor 
utilisant le principe des voxels. Il est possible de récupérer des 
ressources en creusant dans ces cubes, et de créer de nouveaux blocs 
avec les ressources ainsi accumulées.</li></ul>


<ul><li><a href="https://fr.wikipedia.org/wiki/Wine"><strong>wine</strong></a>
 est un une implémentation libre de l'interface de programmation Windows
 bâtie sur X et UNIX (BSD, Linux), cest-à-dire qu'il permet d'utiliser 
sur Linux ou Mac OS X des programmes conçus pour fonctionner sous 
Windows. Le logiciel n'a donc pas besoin du système d'exploitation 
Windows pour fonctionner.</li></ul>
Je suis bientôt a la fin, on va récapituler notre installation:
<ul><li>Installer un <em>client FTP</em> : <strong>filezilla</strong></li><li>Installer un <em>logiciel de messagerie instantanée</em> : <strong>kopete, konversation </strong>contenu dans le paquet <strong><em>kde-full</em></strong></li><li>Installer un <em>logiciel de téléchargement torrent</em> : <strong>ktorrent </strong>contenu dans le paquet <strong><em>kde-full</em></strong></li><li>Installer <em>un navigateur alternatif</em> à Firefox : <strong>konqueror</strong></li><li>Installer le support des archives compressées au format <em>7z</em> : <strong>p7zip-full</strong></li><li>Installer <em>mes jeux favoris : </em><strong>0ad</strong><em> et </em><strong>Minetest</strong></li></ul>
J'étofferais petit a petit les paquets car d'autres me viennent en tête.
