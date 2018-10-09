---
title: Créer un blog avec Dotclear #9 Gestion des plugins
date: 2016-06-17 00:23
layout: post
---

<div class="level1">

La liste des plugins installés est disponible via le lien *Gestion des
plugins*.

</div>

<!--more-->

<div class="level1">

<div id="dokuwiki__top" class="page max-innerpage center">

Installer un plugin {#installer-un-plugin .sectionedit2}
-------------------

<div class="level2">

Installer un plugin n’est pas compliqué, plusieurs options s’offrent à
vous.

</div>

### Installation via l'interface d'administration du blog {#installation-via-l-interface-d-administration-du-blog .sectionedit3}

<div class="level3">

Pour pouvoir installer un plugin, il est nécessaire de s'identifier avec
un compte doté des permissions de super-administrateur.

</div>

#### En utilisant le gestionnaire des plugins

<div class="level4">

Le gestionnaire des plugins permet, directement à partir de
l'administration, de consulter, installer et mettre à jour tous les
plugins déposés sur DotAddict.org en un seul clic !

</div>

#### En le téléchargeant depuis votre disque dur {#en-le-telechargeant-depuis-votre-disque-dur}

<div class="level4">

Téléchargez le plugin de votre choix sur votre disque dur. Rendez vous
ensuite sur le tableau de bord de l'interface d'administration de votre
blog. Cliquez sur le lien *Gestion des plugins* (dans la partie
*Système*), et choisissez l'onglet
`Installer ou mettre à jour manuellement`. Dans la zone
`Déposer un fichier zip` cliquez sur le bouton `Parcourir` et
sélectionnez le fichier .zip que vous venez de télécharger. Saisissez
ensuite votre mot de passe dans le champ prévu puis validez votre choix
en cliquant sur le bouton **Déposer l'extension**.

</div>

#### En indiquant une URL de fichier distant

<div class="level4">

Relevez l'<abbr title="Uniform Resource Locator">URL</abbr> du fichier
.zip du plugin que vous souhaitez installer. Rendez vous ensuite sur le
tableau de bord de l'interface d'administration de votre blog. Cliquez
sur le lien *Gestion des plugins* (dans la partie *Système*), et
choisissez l'onglet "Installer ou mettre à jour manuellement". Inscrivez
l'url du .zip dans le champ `URL du fichier zip à télécharger`.
Saisissez ensuite votre mot de passe dans le champ prévu puis validez
votre choix en cliquant sur le bouton **Télécharger l'extension**.

<div class="wikinote notewarning">

**Attention :**

<p>
Les installeurs de plugins au format obsolète `pkg.gz` ne sont plus pris
en charge par le gestionnaire de Dotclear.

</div>

</div>

### Installation manuelle {#installation-manuelle .sectionedit4}

<div class="level3">

Certains hébergeurs ne permettent pas l’installation automatique. Vous
devrez alors télécharger l'archive du plugin (au format `.tar.gz` ou
`.zip`) sur votre disque dur.

Puis décompressez et transférez le répertoire obtenu sur votre serveur
dans le répertoire `plugins` de votre installation Dotclear

Dans l’interface d'administration de votre blog, votre nouvelle
extension doit maintenant figurer dans la liste accessible par le lien
*Gestion des plugins*.

<div class="wikinote notetip">

**Astuce :**

Après avoir installé un nouveau plugin, repassez systématiquement par la
page du tableau de bord. Nombre de plugins ont besoin que cette étape
soit effectuée pour être activés.

</div>

</div>

Configuration des plugins {#configuration-des-plugins .sectionedit5}
-------------------------

<div class="level2">

La gestion des plugins depuis l’administration du blog est très
variable:

-   <div class="li">

    Les plugins les plus paramétrables auront un lien à leur nom dans la
    colonne de gauche, généralement dans la zone du bas, sous le titre
    *Plugins*.

    </div>

<!-- -->

-   <div class="li">

    Certaines ne proposent que quelques options qui sont activables dans
    les *Paramètres du blog*.

    </div>

<!-- -->

-   <div class="li">

    Les plugins du layout widget sont accessibles par le lien *Widgets de
    présentation*, où vous les trouverez parmi les `Widget disponibles`,
    d’où vous pourrez les faire glisser vers l’une ou l’autre partie de
    la barre de navigation et accéder aux éventuels réglages de
    leur affichage.

    </div>

<!-- -->

-   <div class="li">

    D’autres encore peuvent ne posséder ni lien dédié ni widget,
    reportez-vous alors à la documentation (sur le site de l’auteur)
    pour faire fonctionner correctement le plugin.

    </div>

<div class="wikinote notetip">

**Astuce :**

Il peut arriver qu'un plugin réclame l'insertion ou la modification de
code dans certains fichiers du thème (le plus souvent \_head.html). Pour
modifier ces fichiers, vous avez deux possibilités :

-   <div class="li">

    Utilisez un client <abbr title="File Transfer Protocol">FTP</abbr>
    pour télécharger le fichier en question depuis le répertoire `tpl`
    de votre thème actuel (`themes/nomdutheme`). Si le fichier de n'y
    trouve pas, ce qui est très probable, téléchargez celui du thème par
    défaut (situé dans `themes/default`). Puis, modifiez-le et déposez
    cette nouvelle version dans le répertoire `tpl` de *votre* thème.

    </div>

-   <div class="li">

    Accédez à **Apparence du blog** via le Tableau de bord et cliquez
    sur le bouton **Éditeur de thème** après avoir sélectionné votre
    thème actuel dans la galerie. Cliquez sur le nom du fichier à
    modifier, faites les changements nécessaires et cliquez sur
    **Enregistrer**.

    </div>

</div>

</div>

Suppression d'un plugin {#suppression-d-un-plugin .sectionedit6}
-----------------------

<div class="level2">

Pour supprimer définitivement un plugin, enlevez d’abord :

-   <div class="li">

    les modifications éventuelles sur les fichiers du thème ;

    </div>

-   <div class="li">

    les widgets liés au plugin ;

    </div>

-   <div class="li">

    les fichiers créés par l’administration du plugin (s’il possède son
    propre lien dans l’administration du blog).

    </div>

Puis, reportez-vous au lien *Gestion des plugins* de l’administration,
et cliquez sur le bouton **Supprimer** correspondant.

Si cela n’a pas d’effet, votre hébergeur ne permet pas cette opération
automatique (c’est par exemple le cas de Free), ou si vous ne pouvez
plus vous connecter à l'administration de Dotclear, vous serez obligés
d'effectuer une désinstallation manuelle. Vous devrez alors supprimer
par <abbr title="File Transfer Protocol">FTP</abbr> le dossier du plugin
en question dans le dossier `plugins` de votre installation Dotclear
(par défaut les plugins sont installés dans le répertoire
`/dotclear/plugins/`).

</div>

Mettre à jour un plugin {#mettre-a-jour-un-plugin .sectionedit7}
-----------------------

<div class="level2">

 

</div>

#### Via le panel de gestion des plugins

<div class="level4">

Si des plugins peuvent être mis à jour, vous êtes automatiquement
prévenus par le gestionnaire des plugins, et cela se fait en un simple
clic.

<div class="wikinote noteclassic">

**Note :**

<p>
Chez certains hébergeurs (Free par exemple), la mise à jour automatique
n'est pas possible, la suppression n'étant pas permise (voir ci-dessus).
Il faut donc passer par le ftp pour remplacer le dossier du plugin par
la nouvelle version, après avoir décompressé en local le fichier zip la
contenant, dans le dossier `plugins` de votre installation Dotclear
(comme indiqué ci-dessus).

</div>

<div class="wikinote noterelated">

**Liens connexes :**

-   <div class="li">

    [Installer un plugin avec
    daInstaller (ABC)](http://abc.dotaddict.org/fiche/Installer-un-plugin-avec-daInstaller "http://abc.dotaddict.org/fiche/Installer-un-plugin-avec-daInstaller"){.urlextern}

    </div>

</div>

</div>

</div>

<div id="page-actions">

[Voir en
ligne.](https://fr.dotclear.org/documentation/2.0/admin/plugins)

</div>

</div>
