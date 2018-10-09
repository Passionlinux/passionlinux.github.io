---
title: Création d'un dépôt personnalisé pour ses paquets Debian
date: 2017-02-21 23:53
layout: post
---

Toujours dans le cadre de faire des paquets, un moment ou un autre, on
aura envie de se faire son petit dépôt pour y placer ses paquets et
profiter de ceux-ci directement via Apt. [Tuto inspiré de celui sur
Debian-facile en partie ou dans sa
totalité.](https://debian-facile.org/doc:mentors:debarchiver:tp-depot-debian-apache2)  
<!--more-->

Installation {#installation .sectionedit3}
------------

<div class="level2">

On commence par installer apache2, de manière basique :
``` {.code .root}
apt-get install apache2
```

Puis on installe debarchiver et dpkg-scanpackages :

``` {.code .root}
apt-get install debarchiver devscripts
```

Configuration {#configuration .sectionedit4}
-------------

<div class="level2">

Ensuite il faut créer les répertoires qui accueilleront les paquets :
``` {.code .root}
mkdir -p /var/www/debian
```

``` {.code .root}
mkdir /var/www/debian/dists/
```

``` {.code .root}
mkdir /var/www/debian/_incoming/
```

Le répertoire dists contiendra l'arborescence du dépôt et \_incoming
sera le répertoire où debarchiver viendra chercher les nouveaux paquets
pour les placer au sein de l'arborescence. Enfin il suffit d'éditer le
fichier /etc/debarchiver.conf et de modifier les paramètres suivants :

[Extrait de debarchiver.conf](https://debian-facile.org/_export/code/doc:mentors:debarchiver:tp-depot-debian-apache2?codeblock=5 "Télécharger un extrait"){.mediafile .mf_conf}

:   ``` {.code .file .config}
    $destdir = "/var/www/debian/dists"; $inputdir = "/var/www/debian/_incoming"; @distributions = ('jessie', 'testing', 'unstable'); @sections = ('main', 'contrib', 'non-free'); %distmapping =  (  'stable' => 'jessie',  'testing' => 'stretch',  'unstable' => 'sid'   ); @architectures = ('i386', 'amd64', 'all');
    ```

Si vous souhaitez recevoir un message lorsqu'un paquet est ajouté
remplissez la section :

[Extrait de debarchiver.conf](https://debian-facile.org/_export/code/doc:mentors:debarchiver:tp-depot-debian-apache2?codeblock=6 "Télécharger un extrait"){.mediafile .mf_conf}

:   ``` {.code .file .config}
    @mailtos = ('Maintainer', The Maintainer field in control file 'Uploaders', The Uploaders field in control file '@bar.com', User id @bar.com that own the changes file 'installer@foo.com', An explicit email address 'Changed-By'); The email in the changelog file
    ```

    Voici mon fichier perso ( j'ai seulement cacher mon mail!)

        $destdir = "/var/www/debian/dists"; $inputdir = "/var/www/debian/_incoming"; @distributions = ('jessie', 'testing', 'unstable'); @sections = ('main', 'contrib', 'non-free'); %distmapping =  (  'stable' => 'jessie',  'testing' => 'stretch',  'unstable' => 'sid'  ); @mailtos = ('Maintainer',  'Uploaders',  '@bar.com',  'utilisateur@adresse.perso',  'Changed-By'); @architectures = ('i386', 'amd64', 'all');

    Initialisation {#initialisation .sectionedit5}
    --------------

    <div class="level2">

    Il faut maintenant créer l'arborescence du dépôt :
    ``` {.code}
    debarchiver
    ```

    Vérifier le résultat :

    ``` {.code .user}
    ls -lR /var/www/debian/dists
    ```

    Un script cron se trouve dans /etc/cron.d/debarchiver. Par défaut
    debarchiver est executé toutes les 5 minutes. Le répertoire
    \_incoming est alors scanné à la recherche de nouveaux paquets à
    ajouter sur le dépôt.  

    Publier le dépôt {#publier-le-depot .sectionedit6}
    ----------------

    <div class="level2">

    L'arborescence peut être rendue publique par HTTP ou
    <abbr title="File Transfer Protocol">FTP</abbr>. Nous prenons ici
    l'exemple d'un serveur apache2. Voici la configuration d'un virtual
    host (debian.votredomaine.com)
    <dl class="file">
    <dd>
    ``` {.code .file .config}
    <VirtualHost *:80> ServerName debian.votredomaine.com ServerAlias debian.votredomaine.com ServerAdmin webmaster@votredomaine.com DocumentRoot /var/www/debian ErrorLog /var/log/apache2/debian-error.log CustomLog /var/log/apache2/debian-access.log combined<br </VirtualHost>
    ```

    </dd>
    </dl>

    [VirtualHost](https://debian-facile.org/_export/code/doc:mentors:debarchiver:tp-depot-debian-apache2?codeblock=9 "Télécharger un extrait"){.mediafile .mf_}

    :   ``` {.code .file .config}
        <Directory> "/data/www/debian" Options Indexes Includes FollowSymLinks MultiViews IndexOptions FancyIndexing SuppressHTMLPreamble NameWidth=* IndexIgnore _incoming _style HeaderName /_style/HEADER.html ReadmeName /_style/README.html </Directory>
        ```

    La commande IndexIgnore permet de cacher le répertoire \_incoming.
    HEADER.html et README.html permettent d'améliorer le rendu visuel de
    l'aborescence.  

    Ajouter un paquet {#ajouter-un-paquet .sectionedit7}
    -----------------

    <div class="level2">

    Placez tous les fichiers générés pendant la création du paquet (pas
    uniquement le .deb) dans le répertoire \_incoming et attendre
    5 minutes. Si vous êtes pressé exécutez directement la commande :
    ``` {.code .root}
    debarchiver -so
    ```

    </div>

    <div class="secedit editbutton_section editbutton_7">

    </div>

    Utiliser le dépôt {#utiliser-le-depot .sectionedit8}
    -----------------

    <div class="level2">

    Ajoutez les dépôts créés:
    ``` {.code .root}
    echo " deb http://@IP_SERVEUR/depots debian main "  >>  /etc/apt/sources.list
    ```

    ``` {.code .root}
    apt-get update
    ```

     

    </div>

    </div>

    </div>

</div>

</div>
