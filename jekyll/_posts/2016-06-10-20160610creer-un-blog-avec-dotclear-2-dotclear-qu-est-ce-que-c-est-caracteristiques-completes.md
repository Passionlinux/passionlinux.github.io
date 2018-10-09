---
title: Créer un blog avec Dotclear 2; Dotclear, qu'est ce que c'est? Caractéristiques complètes
date: 2016-06-10 23:10
layout: post
---

Dotclear est un logiciel libre de publication web publié en 2003 par
Olivier Meunier. Fruit du travail d'une seule personne à l'origine, le
projet s'est rapidement doté d'une équipe constituée de personnalités
diverses et d'horizons variés.

L'objectif du projet est de fournir un outil simple d'emploi permettant
à tout un chacun de publier sur le web et ce, quel que soit son niveau
de connaissances techniques.

Dotclear est un logiciel libre conçu avant tout pour ses utilisateurs et
recevant des contributions régulières de ceux-ci. N'importe qui peut
l'utiliser et le modifier selon les termes de la [licence
d'utilisation](https://fr.dotclear.org/license).

<!--more-->

<div id="part-features" class="multi-part loaded active"
style="display: block;" title="">

Comment ça marche ? {#comment-ca-marche .sectionedit1}
===================

<div class="level1">

 

</div>

En deux mots... {#en-deux-mots .sectionedit2}
---------------

<div class="level2">

A chaque fois que vous créez ou modifiez un billet, une catégorie, un
utilisateur, etc., Dotclear déclenche l'enregistrement de ces
informations dans une [base de
données](https://fr.dotclear.org/documentation/glossary#base_de_donnees "glossary"){.wikilink1}
et les met en relation les unes avec les autres (tel billet est lié à
telle catégorie par exemple).

A chaque fois qu'un visiteur réclame l'affichage d'une page de votre
blog^[1)](https://fr.dotclear.org/documentation/2.0/overview/how-does-it#fn__1){#fnt__1
.fn_top}^, Dotclear va chercher les informations dans la base, les
traite, les met en forme puis les affiche (ou les fournit).

Le langage utilisé par Dotclear pour mener à bien les opérations de
traitement s'appelle
[PHP](https://fr.dotclear.org/documentation/glossary#php "glossary"){.wikilink1}.
Pour l'affichage/fourniture Dotclear utilise le
[XHTML](https://fr.dotclear.org/documentation/glossary#xhtml "glossary"){.wikilink1}
(ou XML), les
[CSS](https://fr.dotclear.org/documentation/glossary#css "glossary"){.wikilink1}
et une touche de
[Javascript](https://fr.dotclear.org/documentation/glossary#javascript "glossary"){.wikilink1}.
Les fichiers servant au traitement et à l'affichage sont ceux que vous
avez téléchargé dans votre espace web.

<div class="wikinote noteimportant">

**Important :**

<p>
C’est pourquoi [sauvegarder son
blog](https://fr.dotclear.org/documentation/2.0/admin/backup "2.0:admin:backup"){.wikilink1}
ne consiste pas à simplement récupérer les fichiers personnalisés
(thèmes, plugins) depuis le
<abbr title="File Transfer Protocol">FTP</abbr>, mais aussi à faire une
sauvegarde régulière de la base de données.

</div>

</div>

Ou en trois .... {#ou-en-trois .sectionedit3}
----------------

<div class="level2">

Dotclear utilise notamment pour fonctionner
[PHP](https://fr.dotclear.org/documentation/glossary#php "glossary"){.wikilink1}
(version 5) et une [base de
données](https://fr.dotclear.org/documentation/glossary#base-de-donnees "glossary"){.wikilink1}
(PostgreSQL, MySQL ou SQLite).

Le PHP est un langage dit « dynamique » de génération de pages web côté
[serveur](https://fr.dotclear.org/documentation/glossary#serveur "glossary"){.wikilink1}
(et avec ça vous êtes bien avancés :op). En fait, cela signifie que
lorsque vous demandez l’affichage d’une page dans votre navigateur, le «
serveur » (l’ordinateur, à l’autre bout du fil, sur lequel sont stockées
les pages) va « calculer » le contenu de la page pour envoyer, sur votre
écran, une page internet au format
[XHTML](https://fr.dotclear.org/documentation/glossary#xhtml "glossary"){.wikilink1}.
Ce qui tombe plutôt bien car le navigateur, lui, ne comprend pas le PHP
mais parfaitement (en théorie, en tout cas) le XHTML.

Ce que vous allez placer sur votre serveur, à travers votre accès
[FTP](https://fr.dotclear.org/documentation/glossary#ftp "glossary"){.wikilink1},
contient tout ce qui concerne la mise en forme du blog : **où** se
placent dans votre page les articles, commentaires et liens divers et
**comment** tout cela s’affiche dans le navigateur.

Il s’agit donc de fichiers utilisant les technologies PHP et XHTML, bien
sûr, mais aussi
[CSS](https://fr.dotclear.org/documentation/glossary#css "glossary"){.wikilink1},
pour la mise en page graphique et
[JavaScript](https://fr.dotclear.org/documentation/glossary#javascript "glossary"){.wikilink1},
pour des comportements dynamiques dans la page web.

Avec tout cela, notre contenu est donc prêt à être bien mis en valeur,
mais le contenu lui-même – billets, commentaires, organisation des
informations… – comme la vérité, est ailleurs. Notre ami PHP, en fait,
va « l’appeler » dans la page depuis la base de données. C’est aussi son
travail : envoyer des informations à stocker (lorsque vous créez un
billet, par exemple, ou qu’un visiteur dépose un commentaire) et les y
récupérer afin qu’elles s’affichent dans la page.

Lors de l’installation du blog, le logiciel va donc créer
automatiquement des
[tables](https://fr.dotclear.org/documentation/glossary#table "glossary"){.wikilink1}
dans une base (existante ou créée pour l’occasion, suivant votre
hébergement). Les tables en question (au nombre de 16 à l'installation
initiale, et dont les noms commencent par défaut par dc\_) contiendront
les informations relatives aux différents blogs de votre installation
et, bien sûr, l’ensemble des billets et commentaires.

<div class="wikinote noteimportant">

**Important :**

<p>
C’est pourquoi [sauvegarder son
blog](https://fr.dotclear.org/documentation/2.0/admin/backup "2.0:admin:backup"){.wikilink1}
ne consiste pas à simplement récupérer les fichiers personnalisés
(thèmes, plugins) depuis le
<abbr title="File Transfer Protocol">FTP</abbr>, mais aussi à faire une
sauvegarde régulière de la base de données.

</div>

</div>

Caractéristiques
----------------

Dotclear dispose d'une richesse fonctionnelle faisant de lui un outil de
publication de grande qualité, égalant et parfois allant plus loin que
d'autres outils du même ordre. Au-delà des fonctionnalités, Dotclear est
conçu pour apporter le maximum de confort à l'utilisateur.

<div class="two-cols">

<div class="col">

-   **Edition simple des billets** - La rédaction des billets est
    accompagnée d'un éditeur permettant d'appliquer des règles de
    formatage à votre contenu. Un éditeur visuel optionnel complète la
    panoplie d'une édition facilitée vous permettant de vous concentrer
    sur ce que vous écrivez avant toute chose.
-   **Un thème complètement configurable** - Vous n'avez aucune
    connaissance en HTML ou en CSS ? Pas de panique, le thème par défaut
    est totalement configurable en ligne (couleurs, polices de
    caractères, image du haut...) sans avoir besoin de toucher une ligne
    de code. Personnaliser son site n'a jamais été aussi simple.
-   **Administration intuitive** - Vous devez pouvoir écrire un billet
    rapidement sans avoir à passer par de nombreuses étapes. Sans
    sacrifice sur les fonctionnalités, l'interface d'administration est
    simple à utiliser et se met au service de l'utilisateur, quel que
    soit son niveau.
-   **Système de templates flexible** -Inutile de connaître PHP pour
    modifier l'organisation de votre site, un langage de template assez
    simple permet d'appliquer les modifications que vous souhaitez à
    votre site, très facilement. Cependant, si vous le souhaitez, vous
    pouvez activer l'interprétation du PHP dans vos templates. La
    personnalisation des templates de votre site est facilitée par un
    éditeur accessible directement depuis l'interface d'administration.
-   **Gestion des médias** - Vous pouvez ajouter n'importe quel fichier
    au gestionnaire de médias. Celui-ci vous permettra de retrouver vos
    fichiers pour les utiliser dans un billet. Vous pourrez également
    incorporer des sons et des vidéos provenant de services externes
    (Youtube, Deezer...) tout simplement en utilisant l'URL de la page
    où se trouve le média à ajouter.
-   **Nombreuses méthodes de saisie** - Il est possible de saisir les
    billets en syntaxe Wiki ou en XHTML. Des plugins peuvent ajouter de
    nouvelles méthodes de saisie.
-   **Système de commentaires flexible** - Chaque billet pouvant être
    commenté, Dotclear offre l'option d'empêcher les commentaires billet
    par billet ou sur tout le site sur-le-champ ou au terme d'un délai
    que vous fixerez. Il est bien sûr possible de supprimer ou de
    corriger des commentaires.
-   **Antispam intégré** - Afin de lutter contre le spam de commentaires
    et rétroliens, vous disposez de nombreux filtres en standard et la
    possibilité d'en ajouter de nouveaux par le biais de plugins.
-   **Internationalisation** - Chaque utilisateur peut choisir la langue
    dans laquelle il souhaite voir s'afficher l'interface de gestion
    du site. Chaque site peut également s'afficher dans la langue de
    son choix. Un outil de gestion des langues permet d'installer ou
    mettre à jour très facilement une nouvelle langue sur
    votre installation.
-   **Widgets de présentation** - Les éléments de navigation de votre
    site peuvent être personnalisés grâce aux widgets de présentation,
    vous permettant ainsi de placer ce que vous voulez où vous voulez
    afin d'organiser la navigation sur votre site. Vous pouvez également
    utiliser les widgets pour afficher facilement toutes sortes
    d'informations (Météo, classements divers...).
-   **Thèmes et plugins** - Afin d'étendre les fonctionnalités de votre
    blog, vous pouvez installer des plugins ou en changer l'apparence
    avec un nouveau thème. Vous trouverez toutes ces ressources sur
    [Dotaddict](http://dotaddict.org/).
-   **Pages** - Vous pouvez ajouter des pages en dehors du flux des
    billet afin, par exemple, d'ajouter des informations à votre propos,
    des mentions légales ou n'importe quoi d'autre de plus amusant.
-   **Tags et catégories** - Vous pouvez assigner une catégorie à vos
    billet et un nombre illimité de tags. Vous pouvez ainsi faciliter la
    navigation de vos lecteurs.

</div>

<div class="col">

-   **Installation automatisée** - Il ne vous faudra pas plus de deux
    étapes pour installer Dotclear et pouvoir écrire vos
    premiers billets.
-   **Différents layouts de bases de données** - On peut avoir des
    préférences pour un autre système de gestion de bases de données que
    MySQL, c'est pourquoi Dotclear peut être installé aussi bien avec
    MySQL que PostgreSQL ou SQLite.
-   **Multiblog** - Dotclear permet, sans avoir à recourir à une
    application tierce, de mettre en ligne autant de blogs que vous le
    souhaitez, un, cent, dix-mille...
-   **Multi-utilisateur avec permissions** - Vous ne serez peut-être pas
    seul à gérer votre ou vos blogs. C'est pourquoi vous pouvez ajouter
    autant d'utilisateurs que souhaité et leur assigner des droits à
    l'aide d'un système de permissions fines.
-   **Conforme** - Nous mettons tout en oeuvre pour que Dotclear soit
    conforme non seulement aux normes usuelles (HTML, CSS...) mais
    également à HTTP, ceci afin de garantir une intéropérabilité
    maximale avec les outils actuels ou à venir.
-   **Accessible** - Nous garantissons l'accessibilité du contenu pour
    les visiteurs utilisant des moyens d'accès non conventionnels
    (téléphones mobiles, plages Braille, lecteurs d'écrans,
    PDAs connectés).
-   **Import / export** - Dotclear propose nativement d'importer le
    contenu de votre ancien blog d'une version précédente ou
    d'autres logiciels. Nous ajoutons régulièrement de nouveaux
    modules d'importation. Vous avez également la possibilité d'exporter
    le contenu d'un blog ou de toute votre installation à des fins
    de sauvegarde.
-   **Référencement naturel excellent** - Nous avons conçu les pages
    servies par Dotclear de telle manière que leur référencement soit
    optimal et en accord avec le contenu que vous publiez. Vous disposez
    également d'options permettant d'affiner de quelle manière vous
    souhaitez que le référencement s'effectue, ou de
    complètement l'interdire.
-   **Flux de syndication** - La mise à disposition de fils Atom et RSS
    permet aux utilisateurs d'agrégateurs de contenu de suivre la mise à
    jour du blog depuis leur logiciel favori.
-   **Support complet des trackbacks** - Avec les trackbacks vous pouvez
    réagir à un billet d'un autre blog et l'alerter de manière quasi
    automatique de la publication de votre réaction.
-   **Support complet de l'unicode** - Le support de l'unicode permet de
    publier des textes en utilisant des alphabets différents du
    classique latin. Il est ainsi possible de publier en japonais,
    russe, arabe, etc. ; sans n'avoir rien à régler au préalable.
-   **Support des clients XML/RPC** - Vous pouvez écrire et modifier des
    billets depuis un logiciel supportant les protocoles XML-RPC de
    publication suivants : Blogger, MetaWeblog, MovableType.
-   **Extensible** - Dotclear est conçu afin qu'il soit simple d'y
    ajouter des plugins intervenant au coeur de l'application. Vous
    pouvez ainsi écrire et/ou installer des plugins réalisant tout ce
    dont vous pourriez avoir besoin.
-   **Performant et évolutif** - Dotclear est rapide, et il ne l'est pas
    seulement avec peu de données, il l'est aussi avec des dizaines de
    milliers de sites et des centaines de milliers de commentaires. Nous
    avons eu l'occasion de le tester et de l'optimiser sur des
    plate-formes fortement sollicitées avec un volume de
    données conséquent.
-   **Libre et gratuit** - Dotclear est un logiciel distribué
    gratuitement et libre d'utilisation. [Plus de
    détails](https://fr.dotclear.org/license).

<div id="part-screenshots" class="multi-part loaded active"
style="display: block;" title="">

Captures d'écran
----------------

-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/install_wizard.jpg "Assistant d'installation")](https://fr.dotclear.org/screenshots/2.0-fr/s/install_wizard.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/install_index.jpg "Dernière étape de l'installation")](https://fr.dotclear.org/screenshots/2.0-fr/s/install_index.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/login.jpg "Connexion")](https://fr.dotclear.org/screenshots/2.0-fr/s/login.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/dashboard.jpg "Le tableau de bord")](https://fr.dotclear.org/screenshots/2.0-fr/s/dashboard.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/entries.jpg "La liste des billets")](https://fr.dotclear.org/screenshots/2.0-fr/s/entries.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/comments.jpg "La liste des commentaires")](https://fr.dotclear.org/screenshots/2.0-fr/s/comments.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/new_entry.jpg "Nouveau billet")](https://fr.dotclear.org/screenshots/2.0-fr/s/new_entry.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/wysiwyg.jpg "L'éditeur visuel")](https://fr.dotclear.org/screenshots/2.0-fr/s/wysiwyg.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/media.jpg "Le gestionnaire de médias")](https://fr.dotclear.org/screenshots/2.0-fr/s/media.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/media_item.jpg "Un média tel qu'on peut le voir")](https://fr.dotclear.org/screenshots/2.0-fr/s/media_item.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/widgets.jpg "Les widgets")](https://fr.dotclear.org/screenshots/2.0-fr/s/widgets.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/blogs.jpg "Liste des blogs")](https://fr.dotclear.org/screenshots/2.0-fr/s/blogs.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/users.jpg "Liste des utilisateurs")](https://fr.dotclear.org/screenshots/2.0-fr/s/users.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/permissions.jpg "Permissions pour les utilisateurs")](https://fr.dotclear.org/screenshots/2.0-fr/s/permissions.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/langs.jpg "Gestion des langues")](https://fr.dotclear.org/screenshots/2.0-fr/s/langs.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/themes.jpg "Gestion des thèmes")](https://fr.dotclear.org/screenshots/2.0-fr/s/themes.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/blowup.jpg "Configuration du thème par défaut")](https://fr.dotclear.org/screenshots/2.0-fr/s/blowup.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/public_home.jpg "Affichage du blog avec le thème par défaut")](https://fr.dotclear.org/screenshots/2.0-fr/s/public_home.jpg)
-   [![](https://fr.dotclear.org/screenshots/2.0-fr/t/public_post.jpg "Affichage d'un billet, avec le thème par défaut configuré")](https://fr.dotclear.org/screenshots/2.0-fr/s/public_post.jpg)

[Voir en ligne.](https://fr.dotclear.org/about#features)

</div>

</div>

</div>

</div>
