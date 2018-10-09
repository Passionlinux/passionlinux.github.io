---
title: Créer un blog avec Dotclear #15 Médias et pièces jointes
date: 2016-06-23 01:13
layout: post
---

<div class="level1">

Le Gestionnaire de médias, accessible depuis le menu latéral
d'administration du blog, permet d'ajouter, de retirer, d'organiser le
classement de tous vos médias (images, sons, séquences vidéo, textes…)
et de les attacher à des billets.

<div class="wikinote noteclassic">

**Note :**

Dans une installation classique, les fichiers gérés par le Gestionnaire
de médias sont placés dans le répertoire &lt;dotclear&gt;/public/ de
votre espace web.

</div>

</div>

<!--more-->

<div class="level1">

Créer un sous-répertoire {#creer-un-sous-repertoire .sectionedit2}
------------------------

<div class="level2">

L'icône
[![\[+\]](https://fr.dotclear.org/documentation/_media/2.0/controls/plus.png "[+]"){.media}](https://fr.dotclear.org/documentation/_detail/2.0/controls/plus.png?id=2.0%3Ausage%3Amedia "2.0:controls:plus.png"){.media}
située à côté de **Nouveau répertoire** permet de créer un
sous-répertoire et de lui attribuer un nom.

Vous pouvez créer des sous-répertoires à n'importe quel niveau de
l'arborescence.

</div>

Ajouter des fichiers {#ajouter-des-fichiers .sectionedit3}
--------------------

<div class="level2">

Naviguez dans les sous-répertoires jusqu'à atteindre celui dans lequel
vous souhaitez ajouter un fichier, puis cliquez sur l'icône
[![\[+\]](https://fr.dotclear.org/documentation/_media/2.0/controls/plus.png "[+]"){.media}](https://fr.dotclear.org/documentation/_detail/2.0/controls/plus.png?id=2.0%3Ausage%3Amedia "2.0:controls:plus.png"){.media}
placée devant **Ajouter des fichiers**.

Les champs qui vous sont proposés permettent :

-   <div class="li">

    de choisir un fichier sur votre disque dur afin de l'ajouter parmi
    vos média.

    </div>

-   <div class="li">

    d'attribuer un titre à ce fichier : par défaut, le gestionnaire
    remplira ce champ avec le nom du fichier mais vous pouvez le
    modifier ici (ou le faire plus tard).

    </div>

-   <div class="li">

    de cocher la case « Privé » si vous souhaitez être le seul rédacteur
    ayant accès à ce fichier depuis l'administration du blog.

    </div>

<div class="wikinote notewarning">

**Attention :**

<p>
Un fichier marqué comme privé reste accessible du moment qu'on en
connaît l'<abbr title="Uniform Resource Locator">URL</abbr>. Il n'est
juste pas visible tant que vous ne le rendez pas public.

</div>

Il est possible d'ajouter plusieurs fichiers de deux manières
différentes :

-   <div class="li">

    Vous pouvez en faire une archive zip, l'ajouter puis la
    décompresser, voir ci-après, section [fichiers
    zip](https://fr.dotclear.org/documentation/2.0/usage/media#fichiers-zip "2.0:usage:media ?"){.wikilink1}.

    </div>

-   <div class="li">

    Vous pouvez utiliser l'interface avancée de dépôt de fichiers (le
    plugin Flash doit être installé pour votre navigateur).

    </div>

</div>

### Interface de dépôt avancée {#interface-de-depot-avancee .sectionedit4}

<div class="level3">

Cette interface vous permet de sélectionner plusieurs fichiers à la fois
et de les déposer en une seule opération. Pour l'activer, cliquez sur le
lien **Activer l'interface avancée**. Elle sera ensuite systématiquement
disponible.

Cliquez sur le bouton **Choisir des fichiers** pour accéder au
répertoire souhaité puis maintenez la touche `Ctrl` enfoncée pour
sélectionner plusieurs fichiers. Une fois la sélection terminée, vous
pouvez retirer des fichiers de la liste en cliquant sur l'icône rouge
correspondante, ou en ajouter d'autres en cliquant à nouveau sur
**Choisir des fichiers**. Lorsque vous êtes prêt, cliquez sur
**Envoyer**. Des barres de progression vous informent du bon déroulement
de l'opération.

</div>

Télécharger une archive zip du dossier courant {#telecharger-une-archive-zip-du-dossier-courant .sectionedit5}
----------------------------------------------

<div class="level2">

Il suffit pour cela de cliquer sur le lien "Télécharger ce répertoire
dans un fichier zip" en bas de la page.

Le gestionnaire de médias va créer un fichier zip contenant les fichiers
présents dans le répertoire (sauf les fichiers précédés d'un ".") et va
vous le proposer en téléchargement. Vous pourrez alors le récupérer en
local comme une sauvegarde.

</div>

Modifier ou compléter les informations d'un fichier {#modifier-ou-completer-les-informations-d-un-fichier .sectionedit6}
---------------------------------------------------

<div class="level2">

Depuis le gestionnaire de médias, naviguez dans l'arborescence jusqu'à
atteindre le fichier puis cliquez sur son icône ou sur le lien de son
titre. Un formulaire offre les champs nécessaires à la modification de
diverses informations.

C'est également depuis ce panneau que vous pouvez déplacer un fichier en
sélectionnant dans le menu déroulant **Nouveau répertoire** le
répertoire où vous souhaitez le transférer.

Vous pourrez enfin, remplacer le fichier par un autre.

Pensez à cliquer sur **Enregistrer** pour valider vos modifications.

</div>

Ajout direct de fichiers {#ajout-direct-de-fichiers .sectionedit7}
------------------------

<div class="level2">

Si vous disposez d'un accès direct à votre répertoire de médias
(<abbr title="File Transfer Protocol">FTP</abbr> par exemple), vous
pouvez y ajouter directement des fichier sans passer par le gestionnaire
de média. Une fois les fichiers déposés, rendez vous, via le
gestionnaire de médias, dans le ou les répertoires où vous avez déposé
vos fichiers, les fichiers seront alors visibles comme s'ils avaient été
ajoutés par l'interface web.

</div>

Types de fichier particuliers {#layouts-de-fichier-particuliers .sectionedit8}
-----------------------------

<div class="level2">

 

</div>

### Images {#images .sectionedit9}

<div class="level3">

Lorsque vous ajoutez une image dans vos médias, plusieurs miniatures
sont créées :

-   <div class="li">

    *square* : Un carré de 48 pixels de côté.

    </div>

-   <div class="li">

    *thumbnail* : Image réduite à 100 pixels sur son plus grand côté.

    </div>

-   <div class="li">

    *small* : Image réduite à 240 pixels sur son plus grand côté.

    </div>

-   <div class="li">

    *medium* : Image réduite à 448 pixels sur son plus grand côté.

    </div>

Si l'image est de layout JPEG et qu'elle possède des informations
[EXIF](https://fr.dotclear.org/documentation/glossary#exif "glossary"){.wikilink1},
[IPTC](https://fr.dotclear.org/documentation/glossary#iptc "glossary"){.wikilink1}
ou
[XMP](https://fr.dotclear.org/documentation/glossary#xmp "glossary"){.wikilink1},
celles-ci seront lues et enregistrées.

<div class="wikinote notetip">

**Astuce :**

-   <div class="li">

    Vous pouvez définir un format de titre dans la page **Paramètres du
    blog** de façon à générer automatiquement un titre à partir des
    métadonnées de l'image (par exemple son titre et la date de prise de
    vue dans le cas d'une photo).

    </div>

<!-- -->

-   <div class="li">

    Vous pouvez modifier la dimension du grand côté des vignettes
    *thumbnail* (miniatures), *small* (petites) et *medium* (moyennes)
    dans les **Paramètres du blog**. L'absence de valeur ou la saisie
    d'un 0 (zéro) signifiera au gestionnaire de médias qu'il n'a pas à
    créer la vignette correspondante.

    </div>

</div>

<div class="wikinote notewarning">

**Attention :**

Suivant la mémoire attribuée à votre hébergement, il se peut que les
miniatures ne soient pas générées si le fichier de base est trop lourd.
Dans ce cas, il est conseillé de réduire le poids de l'image de départ.

</div>

</div>

### Fichiers ZIP {#fichiers-zip .sectionedit10}

<div class="level3">

Les fichiers zip sont reconnus par le gestionnaire de média. Il est
possible d'en lister le contenu ou de les décompresser en cliquant
simplement sur le fichier afin d'obtenir la page de détails du média.

</div>

### Fichiers MP3 {#fichiers-mp3 .sectionedit11}

<div class="level3">

Les fichiers déposés au format MP3 sont immédiatement écoutables depuis
votre interface web grâce à un petit lecteur en Flash (sous réserve que
le plugin soit présent dans votre navigateur)

</div>

### Fichiers FLV {#fichiers-flv .sectionedit12}

<div class="level3">

De même, les fichiers déposés au format FLV sont immédiatement
affichables depuis votre interface web – également par le biais d’un
lecteur en Flash.

</div>

Pièces jointes {#pieces-jointes .sectionedit13}
--------------

<div class="level2">

Vous pouvez attacher des fichiers à n'importe quel billet existant.
Depuis l'[interface d'édition d'un
billet](https://fr.dotclear.org/documentation/2.0/usage/entries#creation-et-edition "2.0:usage:entries"){.wikilink1}
choisissez **Ajouter un fichier au billet** dans le menu latéral. Le
gestionnaire de médias s'ouvre, vous permettant de choisir le fichier à
attacher à votre billet. Durant cette phase, vous pouvez modifier ou
ajouter des fichiers dans vos médias sans aucun problème.

Pour attacher un fichier à votre billet, cliquez simplement sur l'icône
[![\[+\]](https://fr.dotclear.org/documentation/_media/2.0/controls/plus.png "[+]"){.media}](https://fr.dotclear.org/documentation/_detail/2.0/controls/plus.png?id=2.0%3Ausage%3Amedia "2.0:controls:plus.png"){.media}
du fichier.

Pour retirer une pièce jointe, cliquez sur l'icône [![croix
rouge](https://fr.dotclear.org/documentation/_media/2.0/controls/check-off.png "croix rouge"){.media}](https://fr.dotclear.org/documentation/_detail/2.0/controls/check-off.png?id=2.0%3Ausage%3Amedia "2.0:controls:check-off.png"){.media}.
Notez bien que le fichier ne sera pas supprimé de vos media.

<div class="wikinote notetip">

**Astuce :**

N'importe quel fichier attaché à un billet sera vu comme une annexe de
celui-ci dans les [flux de
syndication](https://fr.dotclear.org/documentation/2.0/usage/feeds "2.0:usage:feeds"){.wikilink1}.
Si le fichier est un MP3, vous avez ce qu'on appelle un Podcast.

[Voir en ligne.](https://fr.dotclear.org/documentation/2.0/usage/media)

</div>

</div>

</div>
