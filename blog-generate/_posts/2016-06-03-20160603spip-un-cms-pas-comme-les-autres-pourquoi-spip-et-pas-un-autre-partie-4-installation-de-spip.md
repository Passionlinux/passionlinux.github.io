---
title: SPIP, un cms pas comme les autres... Pourquoi SPIP et pas un autre ? 4, Installation de SPIP
date: 2016-06-03 11:44
layout: post
---

<div class="main">

<div class="chapo surlignable">

L’installation de SPIP est très simple : il n’y a pas, en particulier,
de fichier à modifier « à la main » avec des variables ésotériques. Vous
trouverez ci-après les deux méthodes d’installation.

</div>

<div class="texte surlignable">

<div id="outil_sommaire" class="cs_sommaire cs_sommaire_avec_fond">

<div class="cs_sommaire_inner">

<div class="cs_sommaire_titre_avec_fond cs_done">

</div>

</div>

</div>

### Configuration nécessaire {#outil_sommaire_0 .spip}

Aucune configuration spéciale n’est nécessaire sur votre ordinateur
personnel, SPIP se gère entièrement sur le Web. Tout ce dont vous avez
besoin, c’est d’un **navigateur Web** (n’importe lequel) et d’un **accès
FTP** pour installer les fichiers sur votre espace d’hébergement, que ce
soit via une interface en ligne ou avec un logiciel de transfert FTP
installé sur votre ordinateur<span
class="spip_note_ref"> \[[1](http://passiongnulinux.tuxfamily.org/spip/spip.php?article213#nb1 "Dans les environnements Linux (Gnome ou KDE) ou dans Mac OS X, un client (...)"){#nh1
.spip_note}\]</span>. Pour installer un site SPIP, il vous faudra un
espace d’hébergement Web ordinaire pourvu d’une base de données SQL et
capable d’exécuter du PHP. Mais soyez rassuré-e : aucune connaissance de
PHP ou de SQL n’est nécessaire pour administrer un site SPIP ! Il vous
faudra juste vérifier que votre hébergeur le propose. Voir :
[« Hébergeurs acceptant
SPIP »](http://www.spip.net/fr_article885.html){.spip_out}. Pour
démarrer avec SPIP, vous pouvez aussi l’installer simplement sur votre
ordinateur, sans nécessiter d’hébergeur. Pour ce faire, reportez vous au
guide [Utiliser SPIP « en
local »](http://www.spip.net/fr_article1970.html){.spip_out}.
**Munissez-vous de vos accès, identifiants et mots de passe FTP et
SQL**. Ces éléments sont indispensables : si vous ne les connaissez pas,
contactez votre hébergeur et demandez-lui de vous les rappeler. Avant
l’installation de SPIP, vous devez aussi avoir une base
[SQL](http://fr.wikipedia.org/wiki/SQL){.spip_out} disponible. Sur de
très nombreux hébergements, il faut soit demander l’activation d’une
base SQL à l’administrateur, soit suivre une procédure automatique en
ligne (dans tous les cas, l’activation de la base SQL n’a rien à voir
avec SPIP ; si vous avez des difficultés, seul votre hébergeur peut vous
fournir vos identifiants personnels et vous expliquer comment atteindre
votre base). Vous devez connaître les données de votre connexion SQL
(fournies par l’hébergeur) :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **l’adresse du serveur SQL** : par exemple
sql.free.fr, ou localhost, ou vide ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **votre login SQL** : souvent le même login que
votre compte Web ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **votre mot de passe SQL** : souvent le même que
le compte Web ; Lors de l’installation, une fois ces informations
indiquées, il faudra aussi préciser :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} **le nom de la base de données** : souvent le
même login que votre compte Web - il est possible que le serveur vous
offre la possibilité de créer vous même cette base, ou à l’inverse il
est possible que SPIP arrive à deviner le nom de la base que l’hébergeur
vous a octroyée, et dans ce cas il ne sera pas nécessaire de l’indiquer.
**Versions logicielles requises sur le serveur**

-   Serveur **Apache** ou compatible (versions supérieures à la 1.2x)
-   Environnement **PHP 4** (et versions supérieures)
-   Serveur de base de données **SQL** (en fonction du choix à
    l’installation) :
    -   **MySQL** 4.1 et suivantes (la version 3 est suffisante pour
        SPIP 1.9)
    -   (ou bien) **PostGreSQL** 8.2 et suivantes
    -   (ou bien) **SQLite** 2 et 3  
       <!--more-->

### Installation automatique (« spip\_loader ») {#outil_sommaire_1 .spip}

La procédure la plus facile et la plus rapide est l’installation
automatique avec « spip\_loader ». Ce petit fichier va télécharger SPIP
et l’installer lui-même chez votre hébergeur. Attention : cette
procédure ne fonctionne pas sur tous les serveurs. Si elle ne fonctionne
pas (vous vous en rendrez compte immédiatement), passez directement à
l’autre méthode.

![](http://www.spip.net/local/cache-vignettes/L500xH500/InstallationAutoSPIP500-5c922.png)

1.  [Récupérez le fichier
    spip\_loader.php](http://www.spip.net/fr_article2670.html#spip_loader){.spip_out}
    (ou copiez juste son contenu),
2.  **Déposez ce fichier dans votre espace d’hébergement** (par FTP ou
    par tout autre moyen que vous propose votre hébergeur).
3.  **Visitez votre site** avec votre navigateur habituel et affichez-y
    le fichier que vous venez de déposer, en vous rendant à l’adresse du
    style : <http://www.monsite.fr/spip_loader.php> et suivez
    les indications.

### Installation manuelle {#outil_sommaire_2 .spip}

Selon la configuration de votre hébergement, il peut arriver que
l’installation automatique ne soit pas possible. Il vous faudra alors
procéder à une installation manuelle, qui est à peine plus compliquée.

![](http://www.spip.net/local/cache-vignettes/L400xH400/art402-1-f0990.gif)

1.  [Récupérez le fichier de
    SPIP](http://www.spip.net/fr_article2670.html){.spip_out} et
    décompactez-le sur votre ordinateur personnel. Vous obtenez un
    dossier « SPIP... » contenant l’ensemble des fichiers du
    système SPIP.
2.  **Placez le contenu de ce dossier (tous les fichiers et
    les sous-répertoires) sur votre site** (par FTP ou par tout autre
    moyen que vous propose votre hébergeur), à l’endroit où vous voulez
    que le site géré par le système soit accessible au public : le plus
    souvent à la racine de votre site, mais ce n’est pas impératif.
3.  **Connectez-vous avec votre navigateur sur votre site**, dans un
    dossier intitulé **« ecrire »**, où SPIP vous proposera une
    interface graphique vous permettant de configurer le système. Une
    fois ces quelques informations de configuration fournies, SPIP sera
    totalement installé et vous pourrez commencer à travailler sur
    votre site.

### Terminer l’installation {#outil_sommaire_3 .spip}

Désormais tout se déroule en ligne. Il vous suffit d’aller « visiter »
avec votre navigateur l’espace privé du site, dont l’adresse est celle
de votre site suivi de « /ecrire » : <http://www.monsite.fr/ecrire>.

![](http://www.spip.net/local/cache-vignettes/L294xH332/install1-e3060.png)

Lors de la première connection à cette adresse, une procédure
d’installation pas-à-pas démarre. L’interface est très simple, il suffit
d’entrer les informations demandées (essentiellement les informations
concernant la base de données SQL indiquées au début). Une fois que
c’est terminé, le système vous demande l’identification que vous avez
fournie et vous pouvez commencer à gérer votre site. Par la suite, c’est
toujours dans cet espace privé que vous irez travailler, muni de vos
codes d’identification. À chaque étape de la procédure d’installation,
vous trouverez un lien vers l’aide, qui provoque l’affichage d’une
[L’aide en ligne](http://www.spip.net/fr_article891.html){.spip_out}
expliquant chaque détail de l’utilisation de SPIP. (La seule opération
un peu complexe apparaît sur certains serveurs : il vous faudra
peut-être modifier les « droits d’accès » de certains dossiers ;
l’opération n’est pas bien méchante, et l’aide en ligne vous fournit
tous les détails nécessaires.) Si tout s’est bien déroulé jusqu’ici, la
procédure d’installation est terminée, et vous pouvez créer et gérer
votre site sans aucune autre manipulation ésotérique...  

> En cas de grosse erreur (du genre : vous avez oublié votre propre
> accès au site — fréquent au début...), pour « relancer » cette
> procédure d’installation, il faut utiliser votre logiciel FTP et
> effacer les fichiers suivants :
>
> -   <span style="color: #800080;">/config/connect.php</span> (ou
>     /ecrire/inc-connect.php ou php3 dans d’anciennes versions)
> -   <span style="color: #800080;">.htacces</span>, s’il existe (ou
>     /ecrire/.htaccess dans d’anciennes versions)
>
> La connexion suivante dans l’espace privé relancera alors la procédure
> de configuration (en réalité, c’est l’absence de fichier
> « connect.php » qui provoque le lancement de cette procédure).

Les répertoires <span style="color: #800080;">/config</span> et <span
style="color: #800080;">/tmp</span> ne doivent pas être accessibles aux
navigateurs, c’est pourquoi SPIP y installe un fichier <span
style="color: #800080;">.htacces</span> de contenu <span
style="color: #800080;">deny from all</span>. Si la confidentialité de
vos données est très importante pour vous, assurez-vous auprès de votre
hébergeur que ces fichiers sont bien pris en compte ; à défaut lisez
l’article [Mutualisation du noyau
SPIP](http://www.spip.net/fr_article3514.html){.spip_out} qui vous
aidera à déménager ces répertoires en dehors de ceux accessibles aux
navigateurs.  

### Migration depuis une précédente version de SPIP {#outil_sommaire_4 .spip}

A coté des nouveaux utilisateurs de SPIP, il peut vous prendre l’envie
de migrer un « vieux » SPIP vers la nouvelle version. Deux cas :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} vous avez une version 1.9 et postérieures : [une
simple mise à jour
suffira](http://www.spip.net/fr_article1318.html){.spip_out}
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} votre SPIP est en version inférieure à la 1.9 :
[une migration est
nécessaire](http://www.spip.net/fr_article3370.html){.spip_out}  

### Votre témoignage {#outil_sommaire_5 .spip}

<p>
Afin de nous aider à améliorer cette procédure d’installation, merci de
faire part de votre expérience dans le [forum
« installation »](http://forum.spip.org/fr_article2014.html){.spip_out},
ou en écrivant à spip@rezo.net (attention : dans les deux cas vos
réponses seront publiées sur notre site, soit sur le forum, soit dans
les archives de notre liste de discussion). Si vous effectuez
l’installation vous-même, veuillez indiquer :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} le nom de votre hébergeur (important, ça, qu’on
ait une idée des différents hébergeurs compatibles, notamment les
gratuits) ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} les éventuelles difficultés rencontrées (y
compris les difficultés d’interface et de compréhension du processus
d’intallation, histoire qu’on puisse améliorer l’interface ou la
documentation) ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} même si votre installation s’est déroulée sans
aucune difficulté, merci de l’indiquer (c’est une info intéressante).

</div>

Voir en ligne : [spip.net](http://www.spip.net/){.spip_out}

</div>

<footer>
<div class="ps surlignable">

</div>

<div class="notes">

Notes
-----

<div id="nb1">

<span
class="spip_note_ref">\[[1](http://passiongnulinux.tuxfamily.org/spip/spip.php?article213#nh1 "Notes 1"){.spip_note}\] </span>Dans
les environnements Linux (Gnome ou KDE) ou dans Mac OS X, un client FTP
est intégré au bureau. Pour Windows, vous pouvez utiliser le logiciel
libre FileZilla.

</div>

</div>

</footer>

