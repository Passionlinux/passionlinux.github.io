---
title: Hugo, Jekyll et Pelican sont testés
date: 2017-12-30T15:02:28+01:00
layout: post
---

Je voulais avant m’arrêter sur un seul, tester les 3 principaux, du moins les plus populaires que sont Jekyll, Hugo et Pelican, pour ce dernier, je ne suis pas sûr qu'il soit parmi les trois plus populaires des générateurs de sites statiques mais il est dans mon top 3 pour sa simplicité...

Jekyll, je l'abandonne directement, il faut des fichiers *md* avec des infos *YAML*, puis nommer ce fichier dans le format *jj/mm/aa-nom-du-billet.md*, moi je n'aime pas quand on m'impose un truc, sinon il faut me donner les moyens d’automatiser la chose comme ce que Hugo propose!

Il reste Hugo et Pelican, les deux sont simples, j'ai tout de même une préférence sur Pelican, plus logique, les fichiers qui sont des billets comme sous n'importe quels générateurs, peuvent être placés dans des dossiers qui seront du coup leurs catégories, plus logique pour moi que Hugo où il faut l'indiquer dans le fichier en question. Hugo est vraiment plus rapide pour "*sortir*" le site et Pelican met presque le double:

	$ hugo
	Started building sites ...
	
	Built site for language en:
	0 of 6 drafts rendered
	0 future content
	0 expired content
	11 regular pages created
	8 other pages created
	2 non-page files copied
	1 paginator pages created
	0 tags created
	0 topics created
	total in 34 ms

et voila avec Pelican:

	$ pelican content -s publishconf.py
	Done: Processed 7 articles, 0 drafts, 4 pages and 0 hidden pages in 0.75 seconds
	
Bon, ce n'est pas essentiel car en faite le temps perdu, je le gagne avec le script qui envoi tout seul le site chez mon hébergeur via *SSH*, *FTP* ou autre. De ce que je vois, Hugo permet facilement de le faire aussi, si j'en crois cette documentation

- https://gohugo.io/getting-started/usage/
- https://gohugo.io/hosting-and-deployment/deployment-with-rsync/

Ce que j'aime avec Pelican et que je ne trouve pas chez Hugo, c'est sa configuration, elle tient principalement dans deux fichiers alors que Hugo est dans un seul qui vient avec la *config.toml* du thème. Peut être aussi que je m'y prends mal, mais je trouve plus simple la manière de faire de Pelican en séparant le tout.

Voila, maintenant parlons des plugins, Hugo en est dépourvu, c'est dû à sa conception et surtout son langage, le [Go](https://fr.wikipedia.org/wiki/Go_(langage)) est un langage de programmation compilé donc pas de dépendances quand on installe Hugo mais par contre pas moyen de l'étendre par la suite contrairement à Pelican et [Python](https://fr.wikipedia.org/wiki/Python_(langage)). Comme je l'ai dit, j'ai pas trop envie de me faire des commentaires via Disqus, à la limite GOOGLE+ mais en même temps je ne me vois pas me faire chier avec les Spams, donc je dois me baser sur un trucs externe (obligation avec le statique) et qui permet de filtrer les commentaires, enfin c'est ce que je suppose, n'ayant jamais utilisé l'un ou l'autre. Pour les plugins de Pelican c'est par [là](https://github.com/getpelican/pelican-plugins). 

J'aime aussi la hiérarchie du site publié, c'est simple, on a des billets directement à la racine du site, là où Hugo fait un dossier */Post* puis autant de sous-dossiers que de billets avec leurs noms, dedans le *index.html* du billet.

Je teste un peu les deux, pour le moment c'est Pelican et on verra par la suite mais de mon coté ça ne change en rien, les fichiers des billets sont compatibles puisque dans le même langage (markdown) sans aucunes manipulations d'importations.
