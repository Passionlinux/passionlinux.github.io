---
title: Créer un blog avec Dotclear 3; Installation de Dotclear
date: 2016-06-11 23:14
layout: post
---

<div class="level1">

Cette page présente la procédure d’installation standard. Quelques
tutoriels pas à pas propres à chaque hébergeur sont disponibles [sur
cette
page](https://fr.dotclear.org/documentation/2.0/hosting "2.0:hosting"){.wikilink1}.

<span style="color:#800000;">**Attention !**</span> Si vous avez
installé Dotclear chez un hébergeur pour lequel aucun tutoriel pas à pas
n’est disponible, n’hésitez pas à contribuer au projet en envoyant votre
tutoriel sur le modèle des autres à documentation (at) dotclear.net.

</div>

<!--more-->

<div class="level1">

Prérequis {#prerequis .sectionedit2}
---------

<div class="level2">

Avant d’installer Dotclear 2, vous devez vous assurer de disposer des
éléments techniques suivants :

-   <div class="li">

    PHP 5.2 ou supérieur avec le support des extensions suivantes :

    </div>

    -   <div class="li">

        mbstring

        </div>

    -   <div class="li">

        iconv

        </div>

    -   <div class="li">

        le support des fonctions ob\_

        </div>

    -   <div class="li">

        le support utf8 sur les fonctions preg\_

        </div>

    -   <div class="li">

        simplexml et domxml

        </div>

    -   <div class="li">

        SPL

        </div>

-   <div class="li">

    Une base de données supportée (au choix) :

    </div>

    -   <div class="li">

        PostgreSQL 8.0 minimum

        </div>

    -   <div class="li">

        MySQL 4.1 minimum avec InnoDB

        </div>

    -   <div class="li">

        SQLite

        </div>

<div class="wikinote noteclassic">

**Note :**

La base de données doit avoir été créée préalablement à l'installation
de Dotclear.

</div>

Assurez-vous en outre d'avoir le paramétrage php suivant :

-   <div class="li">

    Safe\_Mode positionné à Off

    </div>

-   <div class="li">

    Paramètres magic\_quotes\_gpc et magic\_quotes\_runtime positionnés
    à Off

    </div>

-   <div class="li">

    Extension MySQL, PostgreSQL ou SQLite activée (selon la
    base choisie)

    </div>

<div class="wikinote noteclassic">

**Note :**

La présence de l’extension php GD2 est un plus mais n’est pas
indispensable pour le bon fonctionnement de l’application. Si elle n’est
pas présente, vous ne disposerez pas des aperçus des images dans le
gestionnaire de médias.

</div>

<div class="wikinote notetip">

**Astuce :**

<p>
Un script disponible dans la section
[Hébergeurs](https://fr.dotclear.org/documentation/2.0/hosting#tester-votre-hebergeur "2.0:hosting"){.wikilink1}
vous permet de vérifier que ce dernier permet d’installer Dotclear.

</div>

</div>

Installation automatique {#installation-automatique .sectionedit3}
------------------------

<div class="level2">

L’installation automatique de Dotclear 2 est la méthode la plus simple
et la plus sûre. Elle va se charger de vérifier que PHP 5 est activé et,
éventuellement, l’activer à votre place. Ensuite, seront téléchargés les
fichiers nécessaires à l’installation de Dotclear. Cette étape réalisée,
vous serez conduits vers l’installation classique.

Pour installer Dotclear 2 de cette manière :

-   <div class="li">

    Connectez-vous en <abbr title="File Transfer Protocol">FTP</abbr>
    sur votre serveur.

    </div>

-   <div class="li">

    Téléchargez le fichier
    [dotclear2-loader.php](http://download.dotclear.net/loader/dotclear2-loader.php "http://download.dotclear.net/loader/dotclear2-loader.php"){.urlextern}
    sur votre disque dur puis transférez-le sur votre serveur.

    </div>

-   <div class="li">

    Rendez-vous sur ce fichier avec votre navigateur (par
    exemple www.mon\_site/dotclear2-loader.php).

    </div>

-   <div class="li">

    Vous pouvez changer le dossier de destination ou laisser ce champ
    rempli par défaut si vous ne savez pas ce que c’est.

    </div>

-   <div class="li">

    Cliquez sur le bouton.

    </div>

Si tout se passe bien, vous n’aurez plus qu’à cliquer sur le bouton
suivant pour accéder directement à l’[assistant
d’installation](https://fr.dotclear.org/documentation/2.0/admin/install#assistant-d-installation "2.0:admin:install ?"){.wikilink1}.
Dans le cas contraire, il vous faudra utiliser la méthode « classique »
décrite ci-dessous.

</div>

Installation « classique » {#installation-classique .sectionedit4}
--------------------------

<div class="level2">

<div class="wikinote noteclassic">

**Note :**

<p>
Sautez cette étape si vous avez utilisé l’installation automatique. ?
[Etapes
suivantes](https://fr.dotclear.org/documentation/2.0/admin/install#etapes-suivantes "2.0:admin:install ?"){.wikilink1}

</div>

Il faut télécharger l’archive de Dotclear 2, la décompresser, et envoyer
les fichiers sur votre espace web à l’aide d’un logiciel de
<abbr title="File Transfer Protocol">FTP</abbr>.

<div class="wikinote noteimportant">

**Important :**

<p>
Si vous souhaitez profiter de la mise à jour automatique, paramétrez
votre client <abbr title="File Transfer Protocol">FTP</abbr> afin qu'il
transfère les fichiers en **mode binaire** qui garantit que les fichiers
ne seront pas modifiés lors du transfert.

</div>

Vérifiez ensuite que les permissions sont bien réglées en lecture,
écriture et exécution sur les dossiers et fichiers suivants :

-   <div class="li">

    le répertoire cache/

    </div>

-   <div class="li">

    le répertoire public/

    </div>

<div class="wikinote notetip">

**Astuce :**

Si vous êtes sur un système UNIX, comme Linux ou Mac, vous pouvez
ajuster les droits à 775, soit lecture, écriture et exécution pour
l'utilisateur et le groupe et lecture et exécution pour les autres.

Cette solution fonctionnera mais ne sera peut être pas la meilleure en
matière de sécurité. Si vous voulez améliorer les droits sur vos
dossiers et fichiers, sachez que seuls votre utilisateur et le processus
du serveur web doivent avoir les droits en lecture, écriture et
exécution sur ces dossiers (pour plus d’infos voir cette documentation :
[Droits d’accès sous Linux : gérer les accès aux
fichiers](http://doc.ubuntu-fr.org/droits "http://doc.ubuntu-fr.org/droits"){.urlextern}).

</div>

</div>

Assistant d’installation {#assistant-d-installation .sectionedit5}
------------------------

<div class="level2">

Il suffit de vous rendre sur **http://url-mon-dotclear/admin/install/**.
Un message vous avertit que vous n’avez pas de fichier de configuration
et vous propose de vous rendre sur l’assistant wizard. Cliquez sur le
lien.

Un formulaire apparaît et vous demande certains renseignement de
configuration :

-   <div class="li">

    **Type de base de données**

    </div>

-   <div class="li">

    **Nom d’hôte de la base de données** : nom de l’hôte de la
    base^[1)](https://fr.dotclear.org/documentation/2.0/admin/install#fn__1){#fnt__1
    .fn_top}^

    </div>

-   <div class="li">

    **Nom de la base de données**

    </div>

-   <div class="li">

    **Nom d’utilisateur de la base de données**

    </div>

-   <div class="li">

    **Mot de passe de la base de données**

    </div>

-   <div class="li">

    **Préfixe des tables de la base de données**

    </div>

Validez le formulaire, le programme va vérifier que les conditions
d’installation de Dotclear sont remplies et, le cas échéant, vous amener
directement à la [fin de
l’installation](https://fr.dotclear.org/documentation/2.0/admin/install#fin-de-l-installation "2.0:admin:install ?"){.wikilink1}.

Si pour une raison quelconque l’installation échoue, il faut faire une
mise en place manuelle du fichier config.php.

</div>

Mise en place manuelle du fichier config.php {#mise-en-place-manuelle-du-fichier-configphp .sectionedit6}
--------------------------------------------

<div class="level2">

Faites une copie du fichier **inc/config.php.in** que vous nommerez
**inc/config.php** et renseignez les valeurs des constantes en suivant
les indications suivantes :

-   <div class="li">

    **DC\_DBDRIVER** : layout de base de données ('mysql', 'pgsql'
    ou 'sqlite')

    </div>

-   <div class="li">

    **DC\_DBHOST** : nom de l'hôte de la
    base^[2)](https://fr.dotclear.org/documentation/2.0/admin/install#fn__2){#fnt__2
    .fn_top}^

    </div>

-   <div class="li">

    **DC\_DBUSER** : nom de l’utilisateur de la base

    </div>

-   <div class="li">

    **DC\_DBPASSWORD** : mot de passe pour la base de données

    </div>

-   <div class="li">

    **DC\_DBNAME** : nom de la base de données

    </div>

-   <div class="li">

    **DC\_DBPREFIX** : préfixe de nommage des tables dotclear

    </div>

Dans le cas de SQLite, ne renseignez que la valeur de DC\_DBNAME avec le
chemin vers le fichier de la base SQLite.

-   <div class="li">

    **DC\_MASTER\_KEY** : insérez une chaîne de caractères assez longue
    de votre composition **sans apostrophe**. N’en changez plus jamais.

    </div>

-   <div class="li">

    **DC\_ADMIN\_<abbr title="Uniform Resource Locator">URL</abbr>** :
    <abbr title="Uniform Resource Locator">URL</abbr> complète vers
    l’interface d’administration. Ce n’est pas obligatoire mais il est
    préférable de l’indiquer.

    </div>

-   <div class="li">

    **DC\_ADMIN\_MAILFROM** : indiquez l'email à utiliser comme émetteur
    pour l'envoi des mails de récupération de mot de passe.

    </div>

-   <div class="li">

    **DC\_SESSION\_NAME** : nom du cookie de session pour l’interface
    d’administration

    </div>

-   <div class="li">

    **DC\_PLUGINS\_ROOT** : chemin(s) vers l’emplacement des plugins

    </div>

-   <div class="li">

    **DC\_TPL\_CACHE** : emplacement du répertoire de cache (doit
    absolument être accessible en écriture)

    </div>

Consultez la page concernant le [fichier de
configuration](https://fr.dotclear.org/documentation/2.0/admin/config "2.0:admin:config"){.wikilink1}
pour plus de détails.

</div>

Fin de l’installation {#fin-de-l-installation .sectionedit7}
---------------------

<div class="level2">

Une fois le fichier **inc/config.php** créé, il ne vous reste plus qu’à
vous rendre sur **http://url-mon-dotclear/admin/install/** et répondre
aux quelques questions posées. L’installation se termine et vous pouvez
vous connecter.

<div class="wikinote noteimportant">

**Important :**

Un message peut vous indiquer que le répertoire de cache n’est pas
accessible en écriture. Dans ce cas, changer la valeur de DC\_TPL\_CACHE
dans votre fichier de configuration ou donnez les permissions nécessaire
au répertoire en question.

</div>

<div class="wikinote noteclassic">

**Note :**

<p>
L’installation propre à certains hébergeurs est détaillée dans la
section
[Hébergeurs](https://fr.dotclear.org/documentation/2.0/hosting "2.0:hosting"){.wikilink1}
de ce guide.

</div>

</div>

Étapes suivantes {#etapes-suivantes .sectionedit8}
----------------

<div class="level2">

 

</div>

### Facilitez-vous la mise à jour {#facilitez-vous-la-mise-a-jour .sectionedit9}

<div class="level3">

Il est conseillé de ne pas laisser les fichiers « personnels » (le
répertoire **public**) ou personnalisés (les thèmes et les plugins
additionnels) dans le dossier de Dotclear. En cas de [mise à
jour](https://fr.dotclear.org/documentation/2.0/admin/upgrade "2.0:admin:upgrade"){.wikilink1},
cela permet de ne pas avoir à recopier l’ensemble du contenu (qui peut
être conséquent) de l’ancien au nouveau dossier.

Nous recommandons donc de procéder à une [installation
optimisée](https://fr.dotclear.org/documentation/2.0/admin/clean-install "2.0:admin:clean-install"){.wikilink1}
de vos fichiers personnels, que ce soit dans la perspective d'un blog
unique ou d'un multiblog. Vous y lirez aussi comment avoir votre blog
sur l'<abbr title="Uniform Resource Locator">URL</abbr> racine.

</div>

### Paramètres du blog {#parametres-du-blog .sectionedit10}

<div class="level3">

Après avoir achevé la procédure d’installation, pensez à aller
[configurer les paramètres de votre
blog](https://fr.dotclear.org/documentation/2.0/usage/blog-parameters "2.0:usage:blog-parameters"){.wikilink1}.

</div>

Multiblog {#multiblog .sectionedit11}
---------

<div class="level2">

Si vous souhaitez abriter plusieurs blogs sur cette installation,
consultez la documentation [Installation
optimisée](https://fr.dotclear.org/documentation/2.0/admin/clean-install "2.0:admin:clean-install"){.wikilink1}.

</div>

### Plate-forme de blogs {#plate-forme-de-blogs .sectionedit12}

<div class="level3">

Si avoir plusieurs blogs sur son installation ne pose pas de difficulté
majeure, monter une plate-forme de blogs avec des inscriptions et des
créations de blogs automatiques demande des vraies compétences pour
héberger et sécuriser une telle installation. Aucun support n'est assuré
pour ce layout d'utilisation.

<div class="wikinote noterelated">

**Liens connexes :**

-   <div class="li">

    [Faire
    l'inventaire (ABC)](http://tips.dotaddict.org/fiche/Faire-linventaire "http://tips.dotaddict.org/fiche/Faire-linventaire"){.urlextern}

    </div>

-   <div class="li">

    [Ce dont vous aurez besoin avant de télécharger Dotclear
    (Tips DotAddict)](http://tips.dotaddict.org/fiche/Ce-dont-vous-aurez-besoin-avant-de-telecharger-Dotclear "http://tips.dotaddict.org/fiche/Ce-dont-vous-aurez-besoin-avant-de-telecharger-Dotclear"){.urlextern}

    </div>

-   <div class="li">

    [Installer
    Dotclear (ABC)](http://abc.dotaddict.org/post/2009/04/27/7-Installer-Dotclear "http://abc.dotaddict.org/post/2009/04/27/7-Installer-Dotclear"){.urlextern}

    </div>

-   <div class="li">

    [Installer Dotclear
    manuellement (ABC)](http://abc.dotaddict.org/post/2009/04/28/7-bis-Installer-Dotclear-manuellement "http://abc.dotaddict.org/post/2009/04/28/7-bis-Installer-Dotclear-manuellement"){.urlextern}

    </div>

</div>

</div>

<div class="footnotes">

<div class="fn">

^[1)](https://fr.dotclear.org/documentation/2.0/admin/install#fnt__1){#fn__1
.fn_bot}^ ,
^[2)](https://fr.dotclear.org/documentation/2.0/admin/install#fnt__2){#fn__2
.fn_bot}^ Vous pouvez éventuellement le laisser vide si la base est sur
localhost

</div>

<div class="fn">

 

</div>

<div class="fn">

[Voir en
ligne.](https://fr.dotclear.org/documentation/2.0/admin/install)

</div>

</div>

</div>
