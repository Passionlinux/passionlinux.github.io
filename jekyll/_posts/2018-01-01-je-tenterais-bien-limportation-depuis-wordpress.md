---
title: Je tenterais bien l'importation depuis Wordpress.
date: 2018-01-01T18:13:20+01:00
layout: post
---
Je suis toujours hésitant entre les deux générateurs de sites statiques que sont [Hugo](https://gohugo.io/) et [Pelican](https://blog.getpelican.com/) , ce sont deux beaux projets qui font un excellent travail, du reste merci Daniel alias [Devil505](https://devil505.github.io/) pour m'avoir fait connaître ces nouveaux outils du web moderne. Car oui, après un premier temps où on apprends et découvre notre nouvelle manière de "*travailler*", on se demande comment on a pu passer autant de temps à faire autrement... Car oui, encore une fois, c'est juste plaisant, on travail depuis son éditeur et on a aucun désagrément dû à ce qu'on peut s'attendre d'un travail à distance, par exemple pas de latence ni d’errance dans la partie admin de notre *CMS*, je parle surtout de Wordpress qui a quand même des lourdeurs, dans un premier temps coté public/lecteurs où certaines pages mettent du temps à venir, je pense que attendre 3 secondes ou plus à chaque page c'est juste chiant; et dans un deuxième temps l'admin du site qui doit patienter que ses pages se chargent, alors certains *CMS* font des efforts, je pense du côté de Dotclear et SPIP qui sont bien moins chiant mais ça reste plus lourdingue que notre simple éditeur, dans mon cas j'utilise [Remarkable](https://remarkableapp.github.io/) et donc c'est bien moins lourd, chiant, lent,..., d'ouvrir son éditeur que son Firefox.

Tient c'est là que je me dis que je n'ai pas cédé au billet de fin d'année, celui qui évoque ce qu'on a fait ou non, je le ferais plus tard, c'est pas si important que ça.

Alors comme je l'ai dis, j'ai tenté de faire marcher plusieurs générateurs de sites statiques, Hugo, Jekyll et Pelican, le truc c'est que Jekyll, m'a rendu un peu fou, je gagne peu par rapport à Pelican à part un site plus lourd et surtout plus con à faire car nécessite plus de travail, une méthode de nomination des fichiers/billets par date-titre.md ce qui me fait des fichiers avec des titres à rallonge, je n'aime pas aussi la complexité.
Aussi, l'import n'a simplement pas marché avec le paquet de Debian, j'ai voulu installer Jekyll via *GEM* mais j'ai aussi eu des erreurs, ne connaissant pas du tout *Ruby* et *GEM*, j'ai lâché.

Pour Pelican, c'est autre chose, il y a tout qui me plaît, même l'import depuis Wordpress a fonctionné, mes 280 et quelques fichiers/billets sont bien présents, je devrais dire qu'il a bien trop fonctionné car je me retrouve avec des catégories et des auteurs que je ne voulais pas... C'est ça d’être trop fort, va juste falloir que je me plonge dedans pour faire un script qui fasse le boulot dans les 288 fichiers, mais les billets eux sont bien là! Par contre il est plus lent que Hugo, 10 secondes pour 288 billets et 4 pages alors que Hugo le fait en 0.5 secondes... Et j'ai surtout des soucis de markdown, les URL mis dans les billets sont souvent non pris en compte comme des liens, par contre bizarrement quand j'active Disqus alors les même URL sont bien des liens cliquables... Allez comprendre. Au passage la commande pour importer son wordpress est celle-ci:

	$pelican-import --wpfile -m markdown --dir-cat '/home/sebastien/systeme/sauvegarde-site/seb039sblog.wordpress.2018-01-01.xml' -o content

Comme je le disais, Hugo est le plus rapide pour "fabriquer" le site, j'ai multiplié mes billets une certaine quantité de fois, pour 288 billets c'est dans les 0.5 sec, pour 2244 billets c'est 5.3 sec, 4484 c'est en 15 secondes et enfin, car faut bien s’arrêter quelque part, pour 36480 billets représentant en tout 290 Mo de fichiers textes et qui pour moi représenterais un billet par jour pendant 99 ans, on obtient un temps record de 18 minutes pour 1Go de site, je n'ai pas eu le courage de faire la même chose avec Pelican et encore moins avec Jekyll qui aurait nécessité de retoucher au *YAML* de chaque billet/fichier.

	Built site for language en:
	0 of 640 drafts rendered
	0 future content
	0 expired content
	35844 regular pages created
	8 other pages created
	1 non-page files copied
	3584 paginator pages created
	0 tags created
	0 topics created
	total in 1070965 ms

Par contre, aucuns des *GSS* (Générateurs de Sites Statiques) ne fait un truc compatible entre eux, il faut toujours passer par une étape de retouche ou d'importation. 

Avec Hugo, on peut via des *template* ou *archlayout* faire en sorte que ça soit la même chose que sous Pelican ou Jekyll, c'est comme ça que je fais pour partager le même dossier */content* entre ces deux moteurs. Je me suis fais un *template* de la partie "info" de mes billets compatible entre Pelican et Hugo, comme ça chaque billet tapé dans Hugo sera totalement compatible pour Pelican et vice versa. Mon info en "YAML" donne ceci:

	---
	title: {{ replace .TranslationBaseName "-" " " | title }}
	date: {{ .date }}
	draft: true
	tags: []
	banner: ""
	layout: "post"
	---

Du côté de Pelican, l'import depuis Wordpress a été super rapide mais est incompatible avec Hugo, en effet les fichiers/billets commencent par une partie info de ce layout:

	title: Mageia 6 est sortie #2, je dirais enfin, tout ça juste pour ça!
	date: 2017-07-22 18:28
	Author: Sebastien
	Category: Les distributions GNU/Linux
	Slug: 2017-07-22-mageia-6-est-sortie-2-je-dirais-enfin-tout-ca-juste-pour-ca
	layout: post

Ce qui ne va pas, donc va falloir les retoucher, je cherche donc un petit script qui fera le boulot sur 288 fichiers, je vais aller à la pêche aux infos pour en faire un, j'avais à l'époque eu recours à un script qui faisait ça, mais je ne suis plus capable d'en pondre un sans aller voir sur le net.
