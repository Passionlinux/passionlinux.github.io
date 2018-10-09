---
title: SPIP, un cms pas comme les autres... Pourquoi SPIP et pas un autre ? C'est quoi SPIP ? par Wikipedia
date: 2016-06-03 10:53
layout: post
---

<div class="main">

<div class="chapo surlignable">

SPIP (Système de publication pour l’Internet) est un logiciel libre
destiné à la production de sites web. Dans l’offre nombreuse et diverse
de systèmes de gestion de contenu, il se distingue par le soin apporté
aux standards de l’édition (respect des règles typographiques,
organisation des rôles des participants). Ce logiciel privilégie la
simplicité d’installation, d’usage et de maintenance, et il est
largement utilisé par des réseaux de personnes, des institutions
publiques ou privées. SPIP est un acronyme signifiant « Système de
publication pour l’Internet » ; le dernier « P » est laissé à la libre
interprétation de chacun et est souvent traduit par « partagé » ou
« participatif », dans la mesure où ce logiciel permet surtout d’éditer
collectivement un site. Sa mascotte est un polatouche (écureuil volant).
![local/cache-vignettes/L461xH293/logo\_spippngb0fb-47f71.png?1464951059](http://download.tuxfamily.org/passionlinux/images/png/logo_spippng33fb.png){.transparent}

</div>

<div class="texte surlignable">

<div id="outil_sommaire" class="cs_sommaire cs_sommaire_avec_fond">

<div class="cs_sommaire_inner">

<div class="cs_sommaire_titre_avec_fond cs_done">

<!--more-->

</div>

</div>

</div>

### Présentation {#outil_sommaire_0 .spip}

SPIP est l’un des logiciels libres de gestion de contenu parmi les plus
utilisés en France1 (environ 40 000 sites). Il est utilisé à la fois par
des sites institutionnels (sites thématiques, de certains services
déconcentrés, ministères ou ambassades de France), des sites de presse
(le webmestre du journal Le Monde diplomatique est un des initiateurs de
SPIP2), des sites associatifs, universitaires ou des particuliers. Son
langage de « squelettes » permet de produire des sites Internet aux
fonctionnalités élaborées, tout en restant simple à manipuler avec un
niveau modeste en informatique. Un utilisateur de SPIP s’appelle un
« spipeur ». Les utilisateurs peuvent s’identifier sur le site public.
Ils disposent alors de droits d’édition différents selon qu’ils ont le
statut d’« administrateurs », de « rédacteurs » ou de « visiteurs ». Les
« administrateurs » et les « rédacteurs » ont accès à l’espace de
rédaction du site. Les « visiteurs » peuvent s’identifier sur le site
public lorsque c’est nécessaire.  

### Technologie {#outil_sommaire_1 .spip}

SPIP est un logiciel écrit en PHP qui s’appuie sur la base de données
MySQL, mais aussi sur SQLite et PostgreSQL (en version expérimentale).
Il peut être utilisé comme « requêteur Web multi-bases » (y compris avec
des bases de données distantes). Les pages du site sont générées « à la
volée » : les contenus sont stockés dans la base de données et sont mis
en forme au moyen de « squelettes » de présentation. Ces squelettes
permettent de produire les fonctionnalités qu’on peut attendre d’un site
Internet moderne grâce à un langage de balisage léger qui mêle le HTML à
un ensemble de « boucles », de « balises » et de « filtres » documentés
dans plusieurs langues sur le site du projet. Enfin, un système de cache
permet à SPIP d’éviter des calculs redondants pour générer les pages :
quand une page est demandée par un client web, SPIP vérifie d’abord si
elle n’est pas déjà dans son cache avant de l’afficher. La durée de vie
d’une page dans le cache est paramétrable dans son squelette de
présentation.  

### Versions {#outil_sommaire_2 .spip}

SPIP est à l’origine créé pour le site uzine.net, puis les créateurs
décidèrent de le livrer sous licence GPL. Dès son lancement en 2001, il
fut également utilisé par Le Monde diplomatique et Vacarme. Le « noyau »
des développeurs est constitué depuis 2001 par :

-   ARNO\* (Arnaud Martin), créateur de SPIP pour le site uZine.
    Initialement webmestre, graphiste, « PAOiste ».
-   Antoine (Antoine Pitrou), informaticien. A rejoint SPIP par intérêt
    pour l’outil et pour uZine.
-   Fil (Philippe Rivière), journaliste et technicien. A adopté SPIP
    pour répondre aux besoins du Monde diplomatique.

SPIP intègre alors un mécanisme de cache, une authentification, un
module d’installation automatique, ainsi qu’une interface
d’administration et de saisie des articles. SPIP a pour caractéristique
principale de permettre la création de pages dynamiques sans
connaissance de PHP, grâce à un mécanisme de templates relativement
simple dit de « squelettes ». Début 2003, la version 1.6 permet de
décliner l’interface privée en plusieurs langues. Un espace des
traducteurs est mis en place afin de multiplier le nombre de versions
disponibles automatiquement. En janvier 2004, la version 1.7 de SPIP
permet également de gérer des sites multilingues, comprend un module de
recherche et d’indexation du contenu, et permet d’incorporer le contenu
d’autres sites via une syndication. En juin, un fork très controversé,
SPIP-Agora, est annoncé sur le site de l’ADULLACT. Il sera
officiellement arrêté en 2008. En avril 2005, l’interface privée de la
version 1.8 a été remaniée afin de prendre en compte l’analyse
ergonomique effectuée par Diala Aschkar dans le cadre de son mastère.
Une modification importante pour les développeurs voit également le jour
avec cette version : le cœur de SPIP est désormais constitué d’un
nouveau compilateur qui, de par sa richesse, ouvre le champ à de
nouvelles perspectives. Il devient alors possible d’élaborer des
squelettes aux fonctionnalités de plus en plus complexes sans aucun
recours à PHP. La version 1.9 (1^er^ juillet 2006), repérable par une
réorganisation complète des fichiers et le passage des extensions de
fichier de .php3 vers .php8, amène de nombreux changements, dont
certains ne seront vraiment finalisés qu’avec les versions 1.9.1 et
1.9.2. En particulier sont introduits un système de plugin, et des
filtres de traitements d’images. Les squelettes livrés par défaut sont
plus homogènes, et suivent les standards du W3C. La version 1.9.1
fournit un système de modèles, à la manière de ceux existant dans la
syntaxe wiki de MediaWiki, et utilise AJAX assez systématiquement dans
l’espace privé. La version 1.9.2 achève la réorganisation des
répertoires, ce qui permet à une même distribution de SPIP de servir à
tous les utilisateurs d’un même hébergeur. Elle s’enrichit de la
bibliothèque JQuery, et intègre un validateur XML original. Un outil
d’aide à la traduction complète cette nouvelle avancée. La version 2.0
se veut à la fois le système de publication habituel et une plate-forme
de développement plus générale. SPIP devient notamment utilisable sur
plusieurs serveurs SQL différents, grâce à une interface unifiée
spécifique. Il introduit un modèle dit CVT (Charger, Vérifier, Traiter)
permettant d’écrire plus facilement des formulaires, éventuellement en
AJAX11. Au même titre que le site affiché au public, l’espace
d’administration du site (espace privé) peut être redéfini et
personnalisé, notamment à l’aide du langage des squelettes de SPIP. La
version 2.1 offre un système d’extensions (plugins non désactivables
depuis l’interface privée) et transfère certaines fonctionnalités du
noyau de SPIP en extensions. La voie est ainsi ouverte pour proposer des
distributions fortement personnalisables du logiciel. La version 3.0 est
sortie le 19 mai 201212, elle achève la découpe du logiciel en plugins
comme SPIP 2 l’avait amorcée. L’ensemble des fonctionnalités proposées
par SPIP 2 repose dorénavant sur un noyau SPIP 3 accompagné de 23
plugins. La découpe complète du noyau a permis de compléter ses API et
points d’entrée pour les développeurs de plugins. L’ensemble de l’espace
privé de SPIP a été recodé en squelettes, sur la base des outils et
fonctions proposés par le langage de squelettes de SPIP. Cette remise à
plat de l’espace privé a été l’occasion de repenser le fonctionnement
des objets éditoriaux et de normaliser leur usage pour le rendre le plus
générique possible. La création de nouveaux objets éditoriaux et la
personnalisation des objets existants deviennent ainsi beaucoup plus
faciles et plus rapides. SPIP 3 introduit une nouvelle boucle DATA qui
permet enfin de boucler sur tout layout de données et plus seulement sur
les tables SQL. La version 3.1 est sortie le 9 janvier 201613. Elle
offre des mises à jour des bibliothèques javascript, des styles css par
défaut, des améliorations de l’espace de rédaction, des nouveaux outils
pour la rédaction des squelettes, de l’amélioration des performances et
de l’écriture du code.  

### Sites d’utilisateurs {#outil_sommaire_3 .spip}

<p>
Parmi les sites utilisateurs les plus connus, on compte plusieurs sites
de la presse alternative, comme [Le Monde
diplomatique](http://www.monde-diplomatique.fr/){.spip_out} et
[Reporterre](http://www.reporterre.net/){.spip_out}.  
Mais aussi bien d’autres listé
[ici](http://www.spip.net/fr_article884.html#signatures){.spip_out}.

</div>

Voir en ligne : [Système de publication pour
l’Internet](https://fr.wikipedia.org/wiki/Syst%C3%A8me_de_publication_pour_l%27Internet){.spip_out}

</div>

<footer>
<div class="ps surlignable">

P.-S.
-----

Plusieurs articles devraient suivre, celui ci est une copie de la page
de wikipedia sur SPIP ...

</div>

</footer>

