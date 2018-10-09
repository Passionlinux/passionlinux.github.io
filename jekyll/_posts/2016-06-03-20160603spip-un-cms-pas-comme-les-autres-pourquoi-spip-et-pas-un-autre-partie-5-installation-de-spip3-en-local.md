---
title: SPIP, un cms pas comme les autres... Pourquoi SPIP et pas un autre ? 5, Installation de SPIP3 en local
date: 2016-06-03 11:52
layout: post
---

<div class="main">

<div class="chapo surlignable">

Ce tutoriel commence à partir du moment ou vous avez
[téléchargé](http://www.spip.net/fr_download){.spip_out} le dossier
compressé de spip3 et que vous avez décompressé le contenu à la racine
de votre serveur (le plus souvent un répertoire nommé www ou htdocs).
Dans ce tutoriel, j’ai renommé le répertoire spip ainsi obtenu en
spip3\_test

</div>

<div class="texte surlignable">

<div id="outil_sommaire" class="cs_sommaire cs_sommaire_avec_fond">

<div class="cs_sommaire_inner">

<div class="cs_sommaire_titre_avec_fond cs_done">

</div>

</div>

</div>

### 1. Préparatifs - Les droits d’accès (sous linux) {#outil_sommaire_0 .spip}

![](http://www.spip.net/local/cache-vignettes/L520xH303/31-install_droits-acces-dd7d7.png)

En local, si vous êtes sur linux, vous allez devoir modifier les droits
de 4 répertoires : Pour cela deux possibilités :

-   avec votre gestionnaire de fichier, cliquez sur le répertoire en
    question et modifiez les droits.
-   En ligne de commande, placez vous dans votre répertoires et tapez
    (il faut être en root) :  
   chmod -R 777 local/ tmp/ config/ IMG/ (En fait les droits 777 ne
    sont pas obligatoires. Il faut seulement que le serveur (Apache
    ou autre) puisse y ecrire. Cela dépend donc du groupe et de
    l’utilisateur du fichier. Si c’est le serveur qui est le
    propriétaire de ces répertoires, 755 devrait suffire. Généralement
    apache correspond à www-data)  
   <!--more-->

### 2. C’est parti ! {#outil_sommaire_1 .spip}

-   Ouvrir son navigateur web (ex. Firefox)
-   Entrer l’URL de votre répertoire racine de votre serveur. Si vous
    travaillez en local, tapez : **localhost**, autrement lisez la doc
    de votre hébergeur.

    ![](http://www.spip.net/local/cache-vignettes/L430xH206/11-install_localhost-e30e0.png)

-   Il ne vous reste plus qu’a cliquer sur votre dossier, ici
    spip3\_test/

### 3. A la découverte de SPIP {#outil_sommaire_2 .spip}

Vous allez voir comme c’est très simple. A cette étape de l’installation
il vous suffit de rajouter à l’url : **ecrire**. Vous devez obtenir :
**localhost/spip3\_test/ecrire** (n’oubliez pas de valider)

![](http://www.spip.net/local/cache-vignettes/L497xH164/21-install_en-travaux-05a91.png)

### 4. Installation – étape 1 : choix de la base de données. {#outil_sommaire_3 .spip}

Par défaut SPIP3 utilise sqlite3 comme base de données. Dans la très
grande majorité des cas il est inutile de modifier ce choix.

![](http://www.spip.net/local/cache-vignettes/L520xH374/41-install-connexion-sqlite-da180.png)

### 5. Installation – étape 2 : paramétrage de la BDD {#outil_sommaire_4 .spip}

![](http://www.spip.net/local/cache-vignettes/L520xH627/51-install-connexion-nom-sqlite-0551a.png)

-   Vous pouvez, si vous le souhaitez changer le nom de la base
    de données. C’est le nom du fichier que vous retrouverez dans
    /config/bases/
-   Pour le préfixe des tables, laissé l’option par défaut : spip

### 6. Installation – étape 3 : Informations personnelles {#outil_sommaire_5 .spip}

Attention, le login sera celui du super administrateur, celui qui peut
tout faire y compris tout casser et bloquer le site. Ne le perdez pas.
Bien entendu, vous pourrez le modifier par la suite.  

### 7. j’ai peur. {#outil_sommaire_6 .spip}

![](http://www.spip.net/local/cache-vignettes/L520xH239/71-install-htaccess-e1de7.png)

N’ayez pas peur, si vous êtes en local, ce n’est pas grave. Passez à
l’étape suivante. Pour une réponse plus précise réportez-vous à
l’article Installation de spip 3 sur
[www.spip-contrib.net](http://www.spip-contrib.net){.spip_out}  

### 8. Installation – étape 4 : C’est terminé. {#outil_sommaire_7 .spip}

Bravo ! Votre site SPIP est opérationnel mais vide.

</div>

Voir en ligne : [Installation de
SPIP3](http://www.spip.net/fr_article5521.html){.spip_out}

</div>
