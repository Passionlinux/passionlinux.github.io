---
title: Créer un blog avec Dotclear 5; Paramètres du blog
date: 2016-06-13 23:48
layout: post
---

Paramètres du blog {#parametres-du-blog .sectionedit1}
==================

<div class="level1">

Si vos permissions vous y autorisent, le tableau de bord offre deux
onglets : les paramètres du blog et les utilisateurs.

<div class="wikinote notewarning">

**Attention :**

Selon les droits dont vous disposez vous pouvez n'avoir accès qu'à une
partie seulement des paramètres décrits ici.

</div>

</div>

<!--more-->

Informations du blog {#informations-du-blog .sectionedit2}
--------------------

<div class="level2">

 

</div>

### Identifiant du blog {#identifiant-du-blog .sectionedit3}

<div class="level3">

Sert à fournir un identifiant unique pour chaque blog (par défaut pour
le blog principal : default).

<div class="wikinote notewarning">

**Attention :**

Si vous changez l'identifiant de votre blog, vous devez être sûr que le
script répondant à l'adresse de celui-ci soit capable de le gérer. (voir
administration). Si vous n'avez qu'un seul blog, ne changez pas
l'identifiant.

</div>

</div>

### Nom du blog {#nom-du-blog .sectionedit4}

<div class="level3">

Ce champ permet de définir ou modifier le titre du blog. Il est
librement modifiable à tout moment et n'a pas d'impact sur l'adresse du
blog.

</div>

### URL du blog {#url-du-blog .sectionedit5}

<div class="level3">

Adresse complète du blog (donc commençant par "http:"). Selon que la
méthode de lecture de
l'<abbr title="Uniform Resource Locator">URL</abbr> est PATH\_INFO ou
QUERY\_STRING, vous devrez ajouter respectivement un "/" ou un "?" en
fin d'<abbr title="Uniform Resource Locator">URL</abbr>, sauf dans
certains cas très particuliers.

</div>

### Méthode de lecture de l'URL {#methode-de-lecture-de-l-url .sectionedit6}

<div class="level3">

-   <div class="li">

    **PATH\_INFO** : Lecture de
    l'<abbr title="Uniform Resource Locator">URL</abbr> selon la
    variable PATH\_INFO. Permet d'avoir une
    <abbr title="Uniform Resource Locator">URL</abbr> du layout
    **blog/index.php/post/…**

    </div>

-   <div class="li">

    **QUERY\_STRING** : Lecture des informations
    d'<abbr title="Uniform Resource Locator">URL</abbr> dans la chaîne
    QUERY\_STRING, l'<abbr title="Uniform Resource Locator">URL</abbr>
    prend la forme **blog/index.php?post/…**

    </div>

<div class="wikinote noteclassic">

**Note :**

Si vous souhaitez une lecture des
<abbr title="Uniform Resource Locator">URL</abbr> en path\_info,
assurez-vous d'abord que votre hébergeur le supporte. Vous devrez
ensuite indiquer l'url vers le blogue sous la forme
`http://monblog/index.php/` puis décommenter les dernières lignes du
fichier inc/config.php.

Si vous choisissez le format query\_string, indiquez l'url vers le
blogue sous la forme `http://monblog/index.php?` ou `http://monblog?`

</div>

Il est possible de retirer les "index.php" et "?" avec
l'<abbr title="Uniform Resource Locator">URL</abbr> rewriting si elle
est disponible avec les codes suivants:

Pour du query\_string:

``` {.code .apache}
 RewriteEngine on RewriteCond %{REQUEST_FILENAME} !-f RewriteCond %{REQUEST_FILENAME} !-d RewriteRule (.*) index.php?$1
```

Pour du Path\_info:

``` {.code .apache}
 RewriteEngine On RewriteBase / RewriteCond %{REQUEST_FILENAME} !-f RewriteCond %{REQUEST_FILENAME} !-d RewriteRule (.*) index.php/$1 RewriteRule ^index.php$  index.php/
```

(indiquez le répertoire dans lequel dotclear est installé dans
RewriteBase si ce n'est pas "/")

</div>

### État du blog {#etat-du-blog .sectionedit7}

<div class="level3">

Permet de changer l'état du blog :

-   <div class="li">

    **en ligne** : le blog est normalement en ligne.

    </div>

-   <div class="li">

    **hors ligne** : le blog n'est plus accessible au public mais peut
    être normalement géré par ses utilisateurs.

    </div>

-   <div class="li">

    **supprimé** : le blog n'est plus accessible qu'en administration et
    aux super-administrateurs

    </div>

</div>

### Description du blog {#description-du-blog .sectionedit8}

<div class="level3">

La description du blog est prise en compte dans les informations
affichées par les flux RSS et dans votre blog si le code nécessaire à
son affichage a été intégré dans les fichiers du thème.

</div>

Configuration du blog {#configuration-du-blog .sectionedit9}
---------------------

<div class="level2">

 

</div>

### Nom de l'auteur du blog {#nom-de-l-auteur-du-blog .sectionedit10}

<div class="level3">

Ce champ permet d'indiquer le nom de la personne responsable du contenu
du blog. Cette information sera affichée dans les informations du flux
de syndication.

</div>

### Langue par défaut {#langue-par-defaut .sectionedit11}

<div class="level3">

Il s'agit de la langue du blog ainsi que la langue par défaut dans
laquelle sont rédigés vos billets.

Ce paramètre permet de changer la langue de l'interface publique de
votre blog si la traduction existe. Si ce n'est pas le cas, l'interface
sera en anglais.

</div>

### Fuseau horaire du blog {#fuseau-horaire-du-blog .sectionedit12}

<div class="level3">

Ce paramètre s'applique à l'horodatage des billets et des commentaires
du blog.

</div>

### Note de copyright {#note-de-copyright .sectionedit13}

<div class="level3">

Ce champ permet d'afficher une note de copyright dans les flux de
syndication.

</div>

### Format d'URL des nouveaux billets {#format-d-url-des-nouveaux-billets .sectionedit14}

<div class="level3">

Choisissez dans le menu déroulant le layout
d'<abbr title="Uniform Resource Locator">URL</abbr> que vous souhaitez
pour les pages spécifiques des billets.

</div>

### Interface XML/RPC

<div class="level3">

Cochez cette case pour activer l'interface XML/RPC, qui permet de
publier des billets sur votre blog à l'aide d'un outil externe.

</div>

Commentaires et rétroliens {#commentaires-et-retroliens .sectionedit17}
--------------------------

<div class="level2">

 

</div>

### Accepter les commentaires / Accepter les rétroliens {#accepter-les-commentairesaccepter-les-retroliens .sectionedit18}

<div class="level3">

En décochant la case correspondante vous interdirez tout commentaire
et/ou tout rétrolien sur votre blog.

<div class="wikinote noteclassic">

**Note :**

Si vous pouvez interdire les commentaires et/ou les rétroliens sur un
billet précis s'ils sont globalement autorisés ici, l'inverse (interdire
globalement et autoriser en particulier) n'est en revanche pas possible.

</div>

</div>

### Modérer les commentaires / Modérer les rétroliens {#moderer-les-commentairesmoderer-les-retroliens .sectionedit19}

<div class="level3">

En cochant la case correspondante, tout nouveau commentaire ou rétrolien
sera directement soumis à modération, i.e. ils ne seront publiés
qu'après l'approbation du rédacteur.

</div>

### Laisser les commentaires / les rétroliens ouverts {#laisser-les-commentairesles-retroliens-ouverts .sectionedit20}

<div class="level3">

Indiquez ici le délai (en jours) après lequel les commentaires et/ou les
rétroliens seront fermés, à compter de la date de publication du billet.

</div>

### Autoriser la syntaxe wiki pour les commentaires {#autoriser-la-syntaxe-wiki-pour-les-commentaires .sectionedit21}

<div class="level3">

Cochez cette case pour autoriser l'emploi de la syntaxe wiki dans les
commentaires du blog.

</div>

### Relation "no-follow" {#relation-no-follow .sectionedit22}

<div class="level3">

Si vous activez cette option, les robots des moteurs de recherche ne
suivront pas les liens inclus (y compris celui du site de l'auteur) dans
les commentaires et les rétroliens.

</div>

### Prévisualisation des commentaires {#previsualisation-des-commentaires .sectionedit23}

<div class="level3">

Permet d'activer la prévisualisation pour les visiteurs de votre blog
qui voudraient y laisser un commentaire.

</div>

Présentation du blog {#presentation-du-blog .sectionedit24}
--------------------

<div class="level2">

 

</div>

### Format des dates et des heures {#format-des-dates-et-des-heures .sectionedit25}

<div class="level3">

Ce champ vous permet de définir la façon dont les dates et les heures
s'affichent sur votre blog. Pour connaître les différentes abréviations
et leur signification, affichez l'aide de cette page en cliquant sur le
bouton bleu en haut à droite. (Vous pouvez également consulter [la
documentation PHP à ce
propos](http://php.net/manual/fr/function.strftime.php "http://php.net/manual/fr/function.strftime.php"){.urlextern}.)

</div>

### Afficher des émoticones dans les billets et commentaires {#afficher-des-emoticones-dans-les-billets-et-commentaires .sectionedit26}

<div class="level3">

Remplace les « smileys » en mode texte par les imagettes
correspondantes.

</div>

### Nombre de billets par page {#nombre-de-billets-par-page .sectionedit27}

<div class="level3">

Au-delà du nombre maximal de billets par page défini dans ce champ, un
lien permettant d'avoir accès aux autres pages se présentera à la suite
du dernier billet de la page.

</div>

### Flux de syndication {#flux-de-syndication .sectionedit28}

<div class="level3">

Trois options vous permettent d'affiner la distribution de votre flux de
syndication :

-   <div class="li">

    le choix du nombre de billets

    </div>

-   <div class="li">

    le choix du nombre de commentaires

    </div>

-   <div class="li">

    si les billets doivent être tronqués ou non

    </div>

</div>

Médias et images {#medias-et-images .sectionedit29}
----------------

<div class="level2">

 

</div>

### Taille des miniatures générées (en pixels) {#taille-des-miniatures-generees-en-pixels .sectionedit30}

<div class="level3">

Lorsque vous ajoutez une image au gestionnaire de médias, d'autres
tailles sont automatiquement générées. Vous pouvez ajuster ici la
dimension du plus grand côté de chaque layout d'image générée. Rien ou 0
(zéro) indique au gestionnaire de médias de ne pas créer la vignette
correspondante.

</div>

### Titre des images insérées {#titre-des-images-inserees .sectionedit31}

<div class="level3">

Ce champ vous permet de définir le format des titres ajoutés
automatiquement aux balises des images. Le titre est composé à partir
d'éléments des métadonnées de l'image.

</div>

Paramètres d'indexation {#parametres-d-indexation .sectionedit32}
-----------------------

<div class="level2">

Indiquez ici si vous souhaitez ou non que les moteurs de recherche
indexent et/ou archivent vos pages. Choisissez la dernière option si
vous ne voulez pas que l'on trouve votre blog par le biais d'un moteur
de recherche.

</div>

Antispam {#antispam .sectionedit33}
--------

<div class="level2">

Indiquez ici le délai après lequel vous souhaitez que les commentaires
indésirables soient automatiquement supprimés. Un 0 (zéro) signifie
"suppression immédiate", un nombre négatif désactive le mécanisme de
suppression.

</div>

LightBox {#lightbox .sectionedit34}
--------

<div class="level2">

Si cette extension est installée, vous pouvez, grâce à cette option,
l'activer ou la désactiver à l'échelle de ce blog seulement.

</div>

Enregistrer {#enregistrer .sectionedit35}
-----------

<div class="level2">

N'oubliez pas de valider vos modifications en cliquant sur le bouton
**Enregistrer** situé en bas de cette page.

</div>

Configuration avancée {#configuration-avancee .sectionedit36}
---------------------

<div class="level2">

Si vous possédez les droits suffisants, vous pouvez configurer votre
blog encore plus finement depuis
l'[about:config](https://fr.dotclear.org/documentation/2.0/admin/aboutconfig "2.0:admin:aboutconfig"){.wikilink1}

[Voir en
ligne.](https://fr.dotclear.org/documentation/2.0/usage/blog-parameters)

</div>
