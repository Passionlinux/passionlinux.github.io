---
title: Pourquoi Dotclear et pas SPIP, PluXml ou Wordpress?
date: 2016-06-09 22:07
layout: post
---

<div class="post-content">

[Dernièrement, je parlais de ce qui me manquerait le plus sous
SPIP](http://localhost/index.php?post/2016/06/03/Bienvenue-sur-Dotclear-%21),
**les liens internes**. Je racontais notamment comment sous **SPIP**,
ces **liens étaient facile a mettre en place**, pour mettre en
application mes dires, je prend le morceau de phrase plus haut:
    [Dernièrement, je parlais de ce qui me manquerait le plus sous SPIP->article218] 

et le liens interne au blog était fait, il suffit juste de connaître le
numéro de l'article!
![SPIP](http://www.spip.net/squelettes/img/spip.png) Si je dois encore
trouver d'autres choses qui vont me manquer en plus de cela, je devrais
parler de la syntaxe propre a SPIP:

-   pour les listes,

<!-- -->

    -* 

-   pour la **mise en gras**,

<!-- -->

    {{texte en gras}} 

-   pour la *mise en italique*,

<!-- -->

    {Texte en italique} 

-   pour les intertitres,

<!-- -->

    {{{intertitres}}} 

-   pour les liens,

<!-- -->

    [Lien hypertexte->http://www.spip.net] 

Bref, SPIP reconvertit automatiquement ce qui est écrit en HTML mais on
peut aussi écrire directement en HTML. On comprend mieux [avec cette
exemple.](http://syntaxe.spip.net/ " Syntaxe SPIP Tester la syntaxe de balisage léger de SPIP")  
<!--more-->  
Pour tout dire j’écrivais mes articles via des éditeurs de texte simple
comme **kwrite** sous kde et **gedit** sous gnome. Je devrais citer
aussi les *Statistiques* qui sont utile, le système de plugins, la
séparation des **thèmes** (look du site) et des **squelettes**
(architecture du site), la gestion du **cache très performante**,
l'utilisation d'**autre base de données** que **MySQL**, comme
**SQLite** et **PostgreSQL**, la gestion des **images distantes** qui
met en cache les images copié de l’extérieur ( qui pour moi est aussi un
défaut), les fameuses **boucles**, ... Alors pourquoi changer le moteur
du site une énième fois alors que j'aime SPIP? Pour ses mauvais cotés,
il y en a pas beaucoup, ou plutôt très peu, mais je citerais le
copie/coller d'un article externe demandait plus de travail, vu que ce
site me sers principalement de pense bête, je copie pas mal (bien qu'il
y a un plugin CKeditor), mais c'est surtout son look, je n'arrive pas a
obtenir un truc simple et cool, c'est faisable mais j'ai pas su trouver,
j'ai bien utiliser le squelette spipr-blog mais c'est pas encore ce que
je veux. Ce qui me dérange le plus c'est sa prise de poids dû au
rapatriement des images copiés depuis un autre site, appelé images
distantes. C'est pourtant une bonne action, c'est pour soulager les
sites dont on copie leurs images sans les stocker nous même, ça permet
aussi que si le site externe en question est en panne, les images ont
une sauvegarde locale et apparaissent normalement et sans latence. De
mon coté la plupart des images que je copie ici, sont stocker dans un
espace offert par Tuxfamily, donc c'est plus de la perte de place pour
mon site, qui monte a 140mo (sur 200mo disponible) voir bien plus (+de
40mo de cache d'images distantes en plus du cache du site qui monte
aussi). Alors trois points négatifs contre une multitude de positifs, et
je délaisse SPIP, c'est pas très sérieux. J'avais dis, il y a deux ou
trois mois, que je retournerais a **PluXml** si je n'arrivais pas a
faire ce que je veux avec SPIP, et me voila sur **Dotclear**, pourquoi?
Je vais tacher de répondre a cette question. Je commencerais par dire
simplement que j'adore PluXml comme j'adore SPIP et Dotclear, il fait
son boulot, il est très léger, très rapide, très simple, portatif sur
clef USB, il permet de faire des pages statiques, un blog, une
mediatheque, et surtout il n'a pas de base de données externe ce qui le
rend plus rapide, fait tout ce qu'on peut s'attendre d'un CMS. On peut
aussi parler de son suivit, sa communauté est très a l’écoute et actif.
Si je dois lui reprocher quelque chose, je ne saurais pas ou chercher.
Alors c'est bien beau mais ça dit pas pourquoi Dotclear et pas PluXml ou
Wordpress! Commençons par le début de ce site, ce site est né sur une
**Mandriva2007** et sur un Dotclear 2.0, je sais plus exactement la
version, c’était en tout cas une première version 2. Il y a eu par la
suite de façon officiel [SPIP](http://www.spip.net/) (mon préféré parmi
les gros), [Joomla](https://www.joomla.fr/) (usine a gaz, simple a
obtenir un truc sympa mais des qu'on veux personnaliser un peu c'est
bordel sans nom, en plus de sa lourdeur),
[Guppy](http://www.freeguppy.org/) (sans base de donnée et [sait tout
faire](https://fr.wikipedia.org/wiki/Guppy_%28portail%29)),
[PluXml](http://www.pluxml.org/), et de façon non-officiel
[Drupal](http://drupalfr.org/) (bien trop compliqué pour mon petit blog)
et le très connu [Wordpress](https://fr.wordpress.org/). De tout ces
CMS, je retient seulement **SPIP, Dotclear et PluXml**, pour leurs
fonctions, simplicité, rapidité, leurs administrations... Oui, mon petit
Seb, on a compris que tu les aimes, mais pourquoi ce retour sur
Dotclear? Peut être auriez vous remarqué que la plupart des CMS cité
plus haut sont **francophones** voir même **français**, sauf Drupal et
Wordpress? Peut être du a mon coté Gaulois et fière de l’être... Peut
être auriez vous remarqué que ceux qui sont gardé sont soit **sans base
de donnée externe** (PluXml), soit avec **sqlite** (Spip et Dotclear),
je ne suis pas fan de la complication, pour moi mysql est une
complication, nécessite une sauvegarde supplémentaire bien que certain
CMS sache le faire, je pense en particulier a SPIP. Peut être auriez
vous remarqué que je ne vois pas l’intérêt d'utiliser un CMS lourd de
fonctions ou lourd par son poids, je vois notamment les différences de
poids/tailles en comparant les dossiers téléchargé des différents CMS
puis en les comparant a nouveau avec quelques images, articles et
fonctions activés identiques. Peut être auriez vous remarqué que la
plupart sont **communautaire** sans grosse boite derrière (SPIP, Joomla,
Dotclear, Guppy, PluXml)... J'ai aussi besoin d'une **administration
simple**, pas besoin d'une usine a gaz qui me complique plus la vie
qu'autre chose et surtout je ne veux pas dépendre de nombreux plugins,
en d'autre terme je préfère que mon CMS contiennent les fonctions que je
veux par défaut que d'aller chercher des plugins plus ou moins suivi
(n'est ce pas Wordpress?).
![PluXml](http://static.pluxml.org/common/img/pluxml-logo-bleu.png) J'ai
expliqué pourquoi Dotclear a la place de SPIP, mais qu'est ce que je
reproche a **PluXml** pour ne pas y retourner? Rien, nada, **il entre
dans les critères cités plus haut.** C'est juste que je veux donner la
priorité au plus vieux, puis aussi peut être pour les **liens internes
inexistant** sous PluXml. Maintenant si je dois parler de **Wordpress**,
c'est tout autre chose, c'est un **CMS dépendant d'une grosse boite
américaine**, il est bien plus **gros que la plupart** cité plus haut a
fonction égale et seul Drupal le dépasse mais en fonction aussi, on est
obligé de se servir de **plugins**, en nombre mais surtout pour la
plupart **pas suivi et peu sécurisé et donc des failles de sécurité a la
pelle**... Il est tourné vers du blog pure (c'est ce que je veux) même
si il peut faire tout autre chose en cherchant un peu et surtout en
ayant recours aux plugins, donc vu sa grosseur en comparaison d'autres
qui sont capable de faire bien plus sans plugins (SPIP, Joomla,
Guppy...), est un problème pour moi.
![Wordpress](http://demo.wordpress-fr.net/wp-content/uploads/2013/05/wordpress-logo-stacked-rgb.png)
Pour ce qui est des **moteurs de blogs**, que ce soit **Dotclear** ou
**PluXml**, on est très loin de la taille d'un **Wordpress** (sans rien)
et encore plus avec des articles et des images stockés et du cache, pour
mettre en pratique mes dires, mon **dotclear fait 9.8mo** après
téléchargement et décompression tandis que **Wordpress fait 23mo** (puis
faut aussi penser que la translation en français va être complété et
téléchargé pendant l'installation, ce qui va encore prendre un peu de
place) alors que **SPIP** qui par défaut peut tout faire ne pèse que
**23.9mo** contre **65.5mo pour Drupal**... Je parle pas de **PluXml**
qui au téléchargement dépasse pas les 353ko et une fois décompressé
donne **1.2mo**. Je peux aussi citer que **Wordpress a besoin
exclusivement de Mysql** et comme je l'ai dit plus haut c'est une
complexité dont je n'ai pas besoin en plus d'un ralentissement sur un
petit site. Cette base de donnée devient intéressante dès que le site a
beaucoup d'entrées et beaucoup d'articles ou autres, ce qui n'est pas du
tout mon cas. Après je peux continuer sur sa **popularité**, il
représente a peu près **75% des sites web**, de mon point de vue c'est
plus **un danger** qu'autre chose, **les attaques et les recherches de
failles sont centré sur lui**, et depuis quand le nombre est
représentatif de la qualité, si je dois me baser sur ce que nous a
appris l'histoire je dirais au contraire, c'est seulement **l'effet des
moutons** qui suivent ce qu'ils entendent le plus, je citerais:

-   windows, est t'il le meilleur, le plus sur, celui qui a le plus de
    fonction par défaut des systèmes d'exploitation? Pourtant il est le
    plus utilisé, notamment XP qui reste encore beaucoup utilisé alors
    qu'il n'est même plus suivit par Microsoft...
-   IE6 a été pendant longtemps le plus populaire et le plus utilisé des
    navigateurs, bref c’était surtout une belle preuve d’écrasement par
    la machine Microsoft de ses softs plus par l’intégration dans le
    système que par ses qualités...
-   Flashplugin, ai je besoin d'en parler?
-   ...

<p>
Je continue sur **les thèmes très personnalisable** par défaut en simple
clics mais qui devient **plus complexe des qu'on veut toucher aux
fichiers.html**. Sur cette partie je ne pourrais pas être sur car j'ai
un doute en moi, je sais plus si c’était possible de le faire depuis la
partie administration ou non. J'ai encore quelques reproches a faire sur
Wordpress, mais je pense que je finirais par sa **partie
administration**, qui est **simple et compliqué** a la fois. Bref c'est
déjà bien trop de défauts pour moi qui me fait fuir ce CMS. J'en ai fini
pour cette article, je vais reparler de Dotclear dans les prochains tout
en continuant ceux de SPIP.
![Dotclear](https://upload.wikimedia.org/wikipedia/fr/d/dc/Dotclear-logo.png)

</div>
