---
title: Créer un blog avec Dotclear #10 Apparence du blog ou choisir un autre thème
date: 2016-06-18 00:31
layout: post
---

<div class="level1">

On nomme « thème » les éléments déterminant la présentation du blog.

Le paramétrage des thèmes s’effectue à partir du tableau de bord en
cliquant sur le lien **Apparence du blog**.

</div>

<!--more-->

Choisir un thème {#choisir-un-theme .sectionedit2}
----------------

<div class="level2">

Le premier onglet, **Thèmes**, vous permet de choisir un thème parmi
ceux disponibles sur votre installation. Pour choisir un thème, cliquez
sur celui de votre choix dans la galerie de gauche, puis cliquez sur le
bouton **Utiliser ce thème** sous la version agrandie à droite.

</div>

Installer un thème {#installer-un-theme .sectionedit3}
------------------

<div class="level2">

Les thèmes actuellement distribuables pour Dotclear 2 sont à voir et à
télécharger dans cette
[galerie](http://themes.dotaddict.org/galerie-dc2/ "http://themes.dotaddict.org/galerie-dc2/"){.urlextern}.

Il existe plusieurs façons d’installer un thème :

</div>

### Installation via l’interface d’administration du blog {#installation-via-l-interface-d-administration-du-blog .sectionedit4}

<div class="level3">

Ces méthodes exigent d’être connecté en tant que superadministrateur.

<div class="wikinote notewarning">

**Attention :**

<p>
La mise à jour de thèmes par l’administration du blog n’est pas possible
chez Free.fr, qui empêche la purge du dossier de l’ancienne version. Il
faut supprimer le dossier du thème par
<abbr title="File Transfer Protocol">FTP</abbr>, puis procéder à
l’installation de la nouvelle version par la méthode de votre choix.

</div>

</div>

#### En utilisant l’installeur Dotaddict.org {#en-utilisant-l-installeur-dotaddictorg}

<div class="level4">

Pour cela, il faut déjà avoir
[installé](https://fr.dotclear.org/documentation/2.0/admin/plugins#installer-une-extension "2.0:admin:plugins"){.wikilink1}
l’indispensable plugin
[daInstaller](http://plugins.dotaddict.org/dc2/details/daInstaller "http://plugins.dotaddict.org/dc2/details/daInstaller"){.urlextern}.
Ensuite, grâce à l’icône `Installeur Dotaddict.org` du tableau de bord,
on peut directement à partir de l’administration consulter, installer et
mettre à jour tous les thèmes déposés sur DotAddict.org en un seul clic.

</div>

#### En le téléchargeant depuis votre disque dur {#en-le-telechargeant-depuis-votre-disque-dur}

<div class="level4">

Téléchargez le thème de votre choix sur votre disque dur. Rendez vous
ensuite sur le tableau de bord de l’interface d’administration de votre
blog. Cliquez sur l’icône `Apparence du blog`, et choisissez l’onglet
"Mettre à jour ou installer un nouveau thème". Dans la zone
`Déposer un fichier zip` cliquez sur le bouton `Parcourir` et
sélectionnez le fichier .zip que vous venez de télécharger. Entrez votre
mot de passe dans la case prévue, puis validez votre choix en cliquant
sur le bouton `Déposer un thème`.

</div>

#### En indiquant une URL de fichier distant

<div class="level4">

Relevez l’URL du fichier .zip du thème que vous souhaitez installer.
Rendez vous ensuite sur le tableau de bord de l’interface
d’administration de votre blog. Cliquez sur l’icône `Apparence du blog`
et choisissez l’onglet "Mettre à jour ou installer un nouveau thème".
Dans la zone `Télécharger un fichier zip` Inscrivez l’url du .zip dans
le champ `URL du fichier zip du thème : `. Entrez votre mot de passe
dans la case prévue, puis validez votre choix en cliquant sur le bouton
`Télécharger le thème`.

</div>

### Installation manuelle {#installation-manuelle .sectionedit5}

<div class="level3">

Téléchargez puis décompressez le fichier .zip du thème que vous
souhaitez installer. Puis envoyer le répertoire résultant de cette
décompression dans le répertoire /themes/ de votre installation.

</div>

### Activation du thème {#activation-du-theme .sectionedit6}

<div class="level3">

Ce thème sera désormais ajouté à ceux que vous pouvez choisir depuis
l’onglet **Thèmes** du menu **Apparence du blog**.

</div>

Personnaliser un thème {#personnaliser-un-theme .sectionedit7}
----------------------

<div class="level2">

Lorsqu’un thème est actif vous trouvez, sous le grand aperçu à droite,
des boutons permettant de le personnaliser.

</div>

### Le thème Blowup {#le-theme-blowup .sectionedit8}

<div class="level3">

Il s’agit du thème par défaut de Dotclear 2. C’est un thème entièrement
configurable et personnalisable (dans le cadre d'une structure à deux
colonnes) sans avoir besoin d’éditer les fichiers
<abbr title="Cascading Style Sheets">CSS</abbr> ou de fichiers template
<abbr title="HyperText Markup Language">HTML</abbr>.

Son utilisation est détaillée dans [cette
page](/index.php?post/2016/06/15/Cr%C3%A9er-un-blog-avec-Dotclear-7-%3A-Personnalisation%2C-Blowup%2C-le-th%C3%A8me-par-d%C3%A9faut){.ref-post}.

</div>

### Le thème Custom CSS {#le-theme-custom-css .sectionedit9}

<div class="level3">

Initialement conçu pour permettre l’édition d’un thème css sans passer
par le <abbr title="File Transfer Protocol">FTP</abbr>, l’arrivée de
[l’éditeur de
thèmes](https://fr.dotclear.org/documentation/2.0/admin/themes#editeur-de-theme "2.0:admin:themes ?"){.wikilink1},
permettant la modification de n’importe quel thème existant, y compris
en ce qui concerne les templates html, l’a largement supplanté.
Cependant, il peut être tout à fait pratique pour créer rapidement un
thème à partir d’un thème installé par ailleurs.

</div>

#### Modifier un thème existant {#modifier-un-theme-existant}

<div class="level4">

Repérez le nom du répertoire du thème que vous souhaitez utiliser comme
base de personnalisation (par exemple le thème **Blue Silence** se situe
dans le répertoire **/themes/blueSilence**).

<div class="wikinote notetip">

**Astuce :**

<p>
Si vous ne connaissez pas le nom du répertoire de ce thème, cliquez
dessus dans la galerie de gauche, puis sur le lien **Feuille de style**
sous la version agrandie. Vous obtiendrez ainsi l’URL complète de la
feuille de style dont vous voulez vous inspirer.

</div>

Sélectionnez comme indiqué plus haut le thème **Custom Theme** comme
thème actif sur votre blog.

Cliquez ensuite sur **Configuration du thème**, et dans la page qui
s’affiche, représentant le contenu de votre feuille de style, écrivez
une première ligne :

``` {.code}
 @import "../themes/nom-du-repertoire-du-theme-base/style.css";
```

Le thème personnalisé comprend désormais tout le style du thème choisi.
Il ne vous restera plus qu’à y ajouter toutes les règles différentes ou
supplémentaires. La lecture des css donnant la priorité au «
dernier-disant », les règles que vous y inscrirez seront prioritaires
sur les règles du thème de base. Attention toutefois : si des
comportements particuliers sont en œuvre dans les fichiers html du thème
d’origine, ils ne répercuteront pas sur le Custom
<abbr title="Cascading Style Sheets">CSS</abbr>.

</div>

Éditeur de thème {#editeur-de-theme .sectionedit10}
----------------

<div class="level2">

Dotclear vous permet de modifier les fichiers du thème en cours
d’utilisation, directement depuis l’interface d’administration. Pour
accéder à cette fonction, rendez vous sur le **Tableau de bord** et
cliquez sur **Apparence du blog**. Sélectionnez votre thème actuel dans
la galerie puis cliquez sur le bouton **Éditeur de thème**.

La page de l’Éditeur de thème présente une liste des fichiers de thème.
Les fichiers précédés d’une puce jaune sont ceux qui se trouvent
effectivement dans le répertoire du thème, tandis que ceux qui sont
précédés d’une puce noire se trouvent dans le répertoire du thème par
défaut.

Les fichiers proposés sont de trois layouts :

-   <div class="li">

    **Fichiers template** : ces fichiers `html` contiennent les éléments
    de contenu des pages de votre blog. Les fichiers précédés d’un tiret
    bas "\_" sont des éléments inclus dans les fichiers des layouts
    de pages. Vous pouvez être amené à les modifier pour installer un
    plugin, par exemple. Les fichiers template couvrent également les
    fichiers `xml` des flux de syndication.

    </div>

-   <div class="li">

    **Fichiers <abbr title="Cascading Style Sheets">CSS</abbr>** : la ou
    les feuilles de style associées au thème. Les
    <abbr title="Cascading Style Sheets">CSS</abbr> sont les fichiers
    que l’on modifie le plus couramment pour modifier l’affichage
    du blog.

    </div>

-   <div class="li">

    **Fichiers Javascript** : si votre thème comprend des fichiers
    javascript, ils apparaîtront ici et vous pourrez les modifier.

    </div>

Pour éditer un fichier, cliquez sur son nom. S’il ne se trouve pas déjà
dans le répertoire du thème, il y est automatiquement copié pour que
vous puissiez le modifier à votre guise sans endommager le thème par
défaut.

Lorsque vous avez fait les changements nécessaires, cliquez sur le
bouton **Enregistrer**.

<div class="wikinote noterelated">

**Liens connexes :**

-   <div class="li">

    [Installer un thème avec
    daInstaller (ABC)](http://abc.dotaddict.org/fiche/Installer-un-th%C3%A8me-avec-daInstaller "http://abc.dotaddict.org/fiche/Installer-un-th%C3%A8me-avec-daInstaller"){.urlextern}

    </div>

<div class="li">

[Voir en ligne.](https://fr.dotclear.org/documentation/2.0/admin/themes)

</div>

</div>

</div>
