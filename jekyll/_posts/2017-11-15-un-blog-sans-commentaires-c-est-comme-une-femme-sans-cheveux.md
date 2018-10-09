---
title: "Un blog sans commentaires, c'est comme une femme sans cheveux..."
date: 2017-11-15T16:06:11+01:00
layout: post
---
![Hugo](https://download.tuxfamily.org/passionlinux/logiciels/hugo.png)
Je m'aperçois que les commentaires sont tout de même important, je parle et c'est bien le but d'un blog, mais sans commentaires c'est un monologue, il n'y peut avoir de débats, c'est comme si je voulais balancer les pires choses et ne pas donner le droit de réponses à celui dont je casse le travail.

Alors c'est sur que le site est rapide, je n'ai jamais vu mieux, mais comment ça se passe avec 200 billets? 2000? ...? C'est pas trop le temps de réponse du site qui me fait peur, c'est surtout comment me retrouver dans ce dédale de billets si je veux en modifier un?

Alors oui, je suis dans le noir, je me pose des questions, comme est-ce que ça vaut le coup de s'emmerder autant pour pondre un billet juste pour gagner des secondes et avoir un site "vert" qui passe aux tests de google? Faut l'admettre, *Markdown* ou la syntaxe *wiki* de SPIP sont pour moi aussi pratique l'un comme l'autre, et je dirais même que l'un comme l'autre peut se taper facilement via mon simple éditeur de textes. 

Comme j'ai dis le soucis des commentaires sont en partie résolus, le truc c'est qu'il faut passer par un truc externe du genre [Disqus](https://fr.wikipedia.org/wiki/Disqus), là faut encore une fois relativiser, d'abord on est en face d'une société qui fait de l'argent, autrement on doit payer pour ce service et si on a une offre gratuite c'est que nous somme la monnaie d'échange, soit par nos données soit par de la pub... Et puis au niveau de la sécurité c'est pas ça... Sinon faut passer par autre chose qui tôt ou tard finira de la même manière.

Donc à part le coté Geek et un peu KISS de la chose, je ne vois pas pour moi d'avantages. Je vais être franc, le truc de: 

> Avec Hugo et vos articles en local, vous pouvez les modifier, en créer de nouveau et les publier plus tard. Avec Wordpress et d’autres CMS, vous devrez toujours être en ligne et parfois, ce n’est juste pas possible.

Est pour moi bidon, avec SPIP je peux très bien éditer mon billet dans Gedit et le balancer plus tard sur le site car la syntaxe de SPIP est plus ou moins similaire à Markdown donc pas besoin d'être devant son site pour travailler, dans mon cas ça m'arrive souvent, je suis chez mes parents, je fais un billet avec l'éditeur Gedit ou directement sur le site, puis une fois fini je le met en ligne directement depuis l'endroit oû je suis. Par contre avec Hugo, j'ai besoin d'être sur la machine qui a le serveur Hugo de lancer pour avoir le modèle de billet, bien que pas obligatoire car on peu le faire par la suite, mais surtout pour obtenir le dossier */Public* qui doit ensuite être déposé sur notre site. Je ne me vois pas accéder au service Hugo, à part en passant par *SSH* pour atteindre mon PC et encore il faut résolver l'histoire de l'IP non fixe. Bref, dans le cas de Hugo, je peux taper le billet n'importe oû, mais le publier via la machine qui à le service qui tourne dessus, chose non nécessaire pour un CMS classique.

Et puis il me faut trouver un truc plus sympa que SSH ou FTP pour balancer mon */Public*, un truc que je pourrais automatiser car là c'est:

* je lance le service Hugo avec un hugo server --theme="darksimplicity" puis prépare le modèle via hugo new post/un-blog-sans-commentaires-c-est-comme-une-femme-sans-cheveux.md
* j'écris le billet via gedit ou autre éditeur et l'enregistre,
* je lance hugo dans le terminal pour qu'il me ponde la partie visible du site, c'est-à-dire le dossier /Public,
* enfin je balance le /Public sur mon site via FTP ou SSH.

Ce qui fait pas mal d'étape. Bon, je pense avoir assez parlé pour aujourd'hui.
