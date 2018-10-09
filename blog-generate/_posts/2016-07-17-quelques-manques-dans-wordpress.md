---
title: Quelques manques dans Wordpress
date: 2016-07-17 17:18
layout: post
---

Comme vous avez pu le voir dans le billet précédent, une sorte de
récapitulatif grosso-modo en images des principales fonctions des CMS,
j'ai noté quelques manques, tous sont facilement mis en place par des
plugins, j'en note ici ceux qui me manque et essayerais de compléter ce
billet par la suite en y mettant les plugins qui pourront être mis en
place pour parer a ces manques.  
<!--more-->

###### 1/Les statistiques:

Le premier manque n'est pas très important, mais me permettait de savoir
la fréquentation du site, sous SPIP il y a les **statistiques**, elle
sont simpliste, mais assez juste en comptant une seul ip pour 24h.
![](http://download.tuxfamily.org/passionlinux/images/jpg/spip.php.jpeg){.overflowing}
On peut voir aussi les visites par catégories, par billets, ect... Bref,
j'ai vu pas mal d'extensions pouvant faire ce rôle sous Wordpress,
maintenant il faut savoir lequel prendre.  

###### 2/Article a retenir:

Je suis surpris de ne pas trouver ce petit plus sous Wordpress, alors il
y a la case "mettre en avant" sous Wordpress mais ce n'est pas du tout
la même chose, avec "article a retenir" on place les articles voulu dans
le bandeau latérale sans toucher a l'ordre des billets de la page
d’accueil alors que "mettre en avant" fait exactement le contraire...
Sous PluXml, [j'avais du toucher au
code](http://passiongnulinux.tuxfamily.org/?p=115) pour le faire car pas
d'autre moyen avec ce simpliste moteur, il cherche a être le plus léger
possible donc on peut pas tout avoir non plus! C'est un manque pour moi
assez important, je me suis habitué a ce truc depuis mes débuts de
blogueur sous Dotclear en 2007. Du reste dans les 4CMS que j'utilise
encore (Dotclear, PluXml, SPIP et Wordpress), il est le seul a le
proposer d'origine et de façon simple, en cochant une case dans
l’édition du billet:
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearbilletaretenir.png){.transparent}
Puis une étoile dans la liste des billets signale qu'il est bien "a
retenir":
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearbilletaretenir2.png){.transparent}
Puis le billet apparaît dans la partie latérale "à retenir":
![](http://download.tuxfamily.org/passionlinux/images/png/dotcleararticlearetenir.png)
SPIP le fait aussi mais c'est bien plus compliqué a mettre en place.  

###### 3/Sites amis:

Avec Dotlear on appel ça du "blogroll", c'est la façon cool pour parler
de "Liste de liens vers d'autres blogs", il suffisait d'aller dans
"Liste des liens"  et de remplir les informations:
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearblogroll.png)
On peut aussi importer des
f<abbr title="Champ obligatoire"></abbr>ichiers OPML ou XBEL. Sous SPIP,
c'est tout aussi simple, pour référencer rapidement un site Web en
indiquant  l’adresse URL désirée, ou l’adresse de son fichier de
syndication. SPIP va récupérer automatiquement les informations
concernant ce site (titre, description…). Ou on rentre les infos une par
une.
![](http://download.tuxfamily.org/passionlinux/images/png/spipblogroll1.png)
![](http://download.tuxfamily.org/passionlinux/images/png/spipblogroll2.png)
Mais je suis étonné de ne pas voir de "blogroll" sous Wordpress, ce
n’était déjà pas le cas sous PluXml. Mais bon en cherchant dans les
plugins de Wordpress on trouve. A priori cette fonction a été retiré
depuis WordPress 3.5  

###### 4/antispam:

Par défaut Dotclear a:

-   un filtre de liste blanche et noir d'IP
-   un controleur d'adresse IP via DNSBL
-   un filtre de mots interdits
-   Askimet

![](http://download.tuxfamily.org/passionlinux/images/png/dotclearfiltre2.png)
La dessus je rajoute juste un captcha assez simpliste. Je suis étonné de
voir Wordpress par défaut n'a rien a part Askimet. Bon c'est comme
toujours dans les plugins que l'on peut trouver sa vie. J'en ai vu un de
pas mal, c'est [**Captcha by
BestWebSoft**](https://wordpress.org/plugins/captcha/)et Gilles m'en a
conseillé un autre, **[Better WordPress
reCAPTCHA](https://wordpress.org/plugins/bwp-recaptcha/).** Mais c'est
un plus de mettre par défaut certaine liste même si elles ne sont pas
automatique.  

###### 5/Importation d'un site:

Oui c'est étonné que j'ai vu qu'on ne pouvait pas importer un site
Wordpress par défaut, peu importe les autres CMS que j'ai eu entre les
doigts, il y avait toujours un "exporter/importer" dans leur menu. Sous
Dotclear on a la possibilité d'importer un fichier,  des flux et même
des sites sous wordpress:
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearimport.png){.transparent}
Sous SPIP aussi, on peut restaurer une sauvegarde:
![](http://download.tuxfamily.org/passionlinux/images/png/spiprestore.png)
Alors avec Wordpress, bien sur que c'est faisable et c'est même prévu
mais il faut déjà installé les plugins:
![](http://download.tuxfamily.org/passionlinux/images/png/wordpressimport.png)
Pourquoi ne pas mettre d'origine la restauration d'un site Wordpress?  

###### 6/Liens internes:

Sous WordPress, c’est comme sous Dotclear, il y a un sélecteur de
billets mais les adresses sont données en entier, du coup si on change
d’hébergeur on est obligé de se taper le changement de tous les liens
internes. Encore une fois le plugin [Velvet Blues Update
URLs](https://wordpress.org/plugins/velvet-blues-update-urls/) permet de
le faire. Mais pourquoi pas trouver un système de liens comme sous SPIP
qui permet de ne pas se soucier des liens interne (ou liens durs) et
mettre ça par défaut?  

###### 7/Les révisions:

Je n'ai pas ce soucis sous Dotclear car par défaut il n'y en a pas! Mais
c'est quand même bien utile cette petite chose, par contre pouvoir gérer
les révisions et permettre d'activer et/ou désactiver au besoin, me
parait important. Bon sous SPIP j'ai pas beaucoup de possibilité par
défaut mais au moins je peux activer/désactiver les révisions:
![](http://download.tuxfamily.org/passionlinux/images/png/spiprevision.png)
Encore une fois sous Wordpress c'est faisable mais faut éditer le
fichier wp-config.php. Pourquoi ne pas permettre de le faire dans les
paramètres de Wordpress? Bref encore un tour dans les plugins et le tour
est joué, enfin je pense car pas recherché... Je pense avoir dit les
quelques faiblesses pour moi de ce Wordpress, je dirais que de sortie de
boite et sans plugins rajoutés, Dotclear me parait plus complet, c'est
avec lui que j'ai le moins besoin de rajouter des plugins. Si j'en
trouve d'autres je compléterais ce billet.
