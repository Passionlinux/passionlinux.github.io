---
title: De Dotclear a Wordpress, en passant par PluXml et SPIP, en image.
date: 2016-07-17 00:55
layout: post
---

Wordpress est le CMS le plus utilisé actuellement, mais d'autres
existent comme Dotclear, PluXml pour les moteurs de blog, et SPIP pour
faire un blog ou plus. Nous allons voir ensemble quelques images de la
partie administration et public de chacun. Pour SPIP, j'utilise le
squelette [sarka](http://www.sarka-spip.net/), qui change la fenêtre de
connexion.  

##### La connexion:

Ici rien de spéciale, chacun a une fenêtre de connexion, sous SPIP, la
fenêtre dépend du squelette utilisé.  

###### Dotclear:

![](http://download.tuxfamily.org/passionlinux/images/png/dotclearconnexion.png){.transparent}  

###### PluXml:

![](http://download.tuxfamily.org/passionlinux/images/png/pluxmlconnexion.png){.shrinkToFit
.transparent width="1344" height="642"}  

###### SPIP par défaut:

![](http://download.tuxfamily.org/passionlinux/images/png/spipconnexion2.png)  

###### SPIP avec sarka:

![](http://download.tuxfamily.org/passionlinux/images/png/spipconnexion1.png){.shrinkToFit
width="1348" height="642"}  

###### Wordpress:

![](http://download.tuxfamily.org/passionlinux/images/png/wordpressconnexion.png)  
<!--more-->

##### L'accueil:

Cette page permet de tout savoir en un seul coup d'oeil, le nombre
d'articles, commentaire, mise a jour, news... Seul PluXml n'a pas cette
page d'accueil.  

###### Dotclear:

![](http://download.tuxfamily.org/passionlinux/images/png/dotclearaccueil.png)  

###### PluXml n'en a pas, c'est sur la liste d'article que l'on arrive:

![](http://download.tuxfamily.org/passionlinux/images/png/pluxmllistearticle.png){.shrinkToFit
width="1344" height="642"}  

###### SPIP:

![](http://download.tuxfamily.org/passionlinux/images/png/spipaccueil.png){.shrinkToFit
width="1348" height="642"}  

###### Wordpress:

![](http://download.tuxfamily.org/passionlinux/images/png/wordpressaccueil.png)  

##### Liste des billets et écriture du billet:

Pas beaucoup de différence, a noter tout de même que PluXml ne permet
pas d'action en mode liste, sauf supprimer, que SPIP est légèrement
mieux ici car il permet de changer l’état du billet par une case couleur
(blanc = en cours d’écriture, orange = en attente de validation, vert =
publié, rouge = refusé et blanc-noir = mettre a la corbeille), tandis
que Dotclear et Wordpress permettent de changer l'état du billet,
l'auteur, la catégorie, de supprimer le billet et d'ajouter ou supprimer
des mots clés (étiquettes pour Wordpress).  

###### Dotclear:

![](http://download.tuxfamily.org/passionlinux/images/png/dotcleararticles1.png)
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearlistarticleaction.png){.overflowing}
L’écriture du billet se fait au choix via un l’éditeur wiki un peu a la
SPIP et qui facilite l’écriture via des une syntaxe plus simple que le
html, ou via celui de [Ckeditor](http://ckeditor.com/). Pour ce dernier,
on a le choix entre l’ancien éditeur
dclegacy[Ckeditor](http://ckeditor.com/) et le nouveau
dc[Ckeditor](http://ckeditor.com/).
![](http://download.tuxfamily.org/passionlinux/images/png/dotcleararticles2.png)
Il y a possibilité de faire des liens internes avec un sélecteur de
billet un peu comme celui de Wordpress qui, si déménagement du site,
sont viable car ne prend pas la partie de l'adresse situé avant le
"index.php?". Exemple:

    index.php?post/2015/03/02/374-Les-conseilleurs-ne-sont-pas-les-payeurs

![](http://download.tuxfamily.org/passionlinux/images/png/dotclearliensbillets.png)  

###### PluXml:

![](http://download.tuxfamily.org/passionlinux/images/png/pluxmllistearticle.png){.shrinkToFit
width="1344" height="642"}
![](http://download.tuxfamily.org/passionlinux/images/png/pluxmllistarticleaction.png){.shrinkToFit
width="1348" height="642"} Par défaut, PluXml n'a pas d’éditeur, c'est
en HTML que l'on doit écrire. Par contre plusieurs plugins ajoute des
éditeurs du layout **WYSIWYG** dont le populaire
[Ckeditor](http://ckeditor.com/), comme ici:
![](http://download.tuxfamily.org/passionlinux/images/png/pluxmlarticle.png){.shrinkToFit
width="1344" height="642"} Pas de liens interne, donc au moindre
changement d’hébergeur, ils sont tous a refaire.  

###### SPIP:

![](http://download.tuxfamily.org/passionlinux/images/png/spiparticleliste.png)
![](http://download.tuxfamily.org/passionlinux/images/png/spiplistarticleaction1.png){.shrinkToFit
width="1348" height="642"} Sous SPIP, par défaut, et comme son copain
PluXml, il n'y a pas d’éditeur **WYSIWYG**, on a un éditeur de layout wiki
comme Dotclear, avec une syntaxe pratique et bien pensé, faite pour
écrire de long chapitre. Il y a bien sur des plugins et notamment un,
qui permet d'avoir l'éditeur **WYSIWYG
[Ckeditor](http://contrib.spip.net/CKeditor-3-0),** tout en gardant une
compatibilité avec la typographie de SPIP.
![](http://download.tuxfamily.org/passionlinux/images/png/spiparticlevu.png){.transparent}
![](http://download.tuxfamily.org/passionlinux/images/png/spiparticlemodifi%c3%a91.png)
![](http://download.tuxfamily.org/passionlinux/images/png/spiparticlemodifi%c3%a92.png)
![](http://download.tuxfamily.org/passionlinux/images/png/spiparticlemodifi%c3%a93.png)
Les liens internes sont identiques et se font de la même manière que les
liens externes, il n'y a pas de sélecteur de billets, il faut simplement
connaître le numéro (c'est dur) et le mettre a la place d'un lien, comme
ceci:

    [->203]

et ça nous fera un joli lien avec le nom du billet: [Les conseilleurs ne
sont pas les payeurs.](http://passiongnulinux.tuxfamily.org/?p=6)

    [précédent billet->203]

nous fera un lien vers le billet 203 sur [précédent
billet](http://passiongnulinux.tuxfamily.org/?p=6). Les liens internes
sous SPIP sont du layout:

    spip.php?article203

il ne mette pas l'adresse en entière:

    http://passiongnulinux.tuxfamily.org/spip.php?article203

Ce qui permet, en cas de déménagement de site (changement d’hébergeur)
de ne pas se retrouver avec des liens casser...
![](http://download.tuxfamily.org/passionlinux/images/png/spipliensbillets.png)  

###### Wordpress:

![](http://download.tuxfamily.org/passionlinux/images/png/wordpressarticles.png)
![](http://download.tuxfamily.org/passionlinux/images/png/wordpresslistarticleaction.png){.overflowing}
Sous Wordpress, c'est encore différent c'est bien un éditeur de layout
**WYSIWYG** mais un autre que le connu [CKeditor](http://ckeditor.com/).
Il y a bien sur tout un tas d’éditeurs disponible en plugins. Mais celui
par défaut est mon préféré avec celui de SPIP.
![](http://download.tuxfamily.org/passionlinux/images/png/wordpressarticles2.png)
Sous Wordpress, c'est comme sous Dotclear, il y a un sélecteur de
billets mais les adresses sont données en entier:

    http://passiongnulinux.tuxfamily.org/?p=6

Du coup si on change d'hébergeur on est dans de sale draps et on se tape
le changement de tous les liens internes.
![](http://download.tuxfamily.org/passionlinux/images/png/wordpressiensbillets.png)  

##### Liste des commentaires:

###### Dotclear:

![](http://download.tuxfamily.org/passionlinux/images/png/dotclearcommenatires.png)
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearcommenatires1.png)  

###### PluXml:

![](http://download.tuxfamily.org/passionlinux/images/png/pluxmllistecommentaire.png){.shrinkToFit
width="1344" height="642"}  

###### SPIP:

![](http://download.tuxfamily.org/passionlinux/images/png/spipcommentaire.png)  

###### Wordpress:

![](http://download.tuxfamily.org/passionlinux/images/png/wordpresscommentaires.png)  

##### Les anti-spams et captcha inclus par défaut:

**Dotclear** en a plusieurs:
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearantispams.png){.transparent}
**Wordpress**, **Pluxml** ou **SPIP** n'ont pas de captcha ou
d'anti-spam par défaut... Si, je mens un peu, **Wordpress a Askimet**,
**PluXml en a un** par défaut qui est une vrai **passoire** et SPIP lui
n'a rien.  

##### Les thèmes:

###### Dotclear:

Il y a un sélecteur de thèmes qui permet de changer, modifier,
personnaliser, d’éditer, ainsi que de télécharger de nouveaux thèmes.
![](http://download.tuxfamily.org/passionlinux/images/png/dotcleartheme.png){.transparent}  

###### PluXml:

Un sélecteur de thème est disponible mais ne permet que d’éditer les
thèmes déjà télécharger et uploader en FTP via son client (pour moi
c'est soit celui de kde ou ou filezilla), rien d'autre n'est faisable.
![](http://download.tuxfamily.org/passionlinux/images/png/pluxmltheme.png){.shrinkToFit
width="1344" height="642"}  

###### SPIP:

C'est un [plugin qui fournit le sélectionneur de
thème](http://contrib.spip.net/SPIP-Zen-Garden). Faut dire que SPIP
fonctionne autrement que les autres CMS, il y a des thèmes et des
squelettes.
![](http://static-contrib.spip.net/local/cache-vignettes/L460xH401/zeng21-64082.jpg?1360336316)
SPIP propose comme ses copains, de nombreux thèmes, pas autant que
Wordpress, par contre il y a beaucoup de squelettes personnalisables
dans les moindres recoins comme Sarka:
![](http://download.tuxfamily.org/passionlinux/images/png/spipsarkalayout.png)
![](http://download.tuxfamily.org/passionlinux/images/png/spipsarkalstyle.png)  

###### Wordpress:

Comme son copain Dotclear, a un sélecteur de thèmes qui permet de
changer, modifier, personnaliser, d’éditer, ainsi que de télécharger de
nouveaux thèmes.
![](http://download.tuxfamily.org/passionlinux/images/png/wordpressthemes.png)  

##### Les plugins:

###### Dotclear:

Comme pour les thèmes, dotclear possède un sélecteur de plugins, qui
permet de chercher, télécharger, régler, activer... ses plugins.
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearplugins.png){.transparent}  

###### PluXml:

PluXml possède le strict minimum, il permet seulement d'activer ou non
un plugins et de les configurer. La recherche et le téléchargement se
fait via le site.
![](http://download.tuxfamily.org/passionlinux/images/png/pluxmlplugins.png){.shrinkToFit
width="1344" height="642"}  

###### SPIP:

SPIP est devenu grand, il fait tout via son gestionnaire de plugins,
comme Wordpress ou Dotclear. A noter que sous SPIP les plugins ont des
dépendances envers d'autres plugins pour fonctionner, mais rien de
grave, SPIP fait tout ça automatiquement.
![](http://download.tuxfamily.org/passionlinux/images/png/spippluginssearch.png){.shrinkToFit
width="1128" height="642"}
![](http://download.tuxfamily.org/passionlinux/images/png/spippluginsactive.png){.shrinkToFit
width="1128" height="642"}  

###### Wordpress:

Réputé pour ses plugins, il est le meilleurs pour cette partie. Comme
dotclear dans son principe.
![](http://download.tuxfamily.org/passionlinux/images/png/wordpressplugins.png)  

##### L'import/export:

###### Dotclear:

Il peut exporter ses données (articles, catégorie, liens, media,
ect...)  dans un fichier.txt et même le compacter, il peut ensuite
l'importer. Il peut aussi importer différent blog, soit par les flux RSS
ou Atom ou un site wordpress. Tout ça sans plugins. Par contre un simple
rapatriement du site via ftp ne suffit pas même avec une base SQL, la
base sera illisible(pourtant présente) et le site bloqué.
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearimport.png){.transparent}  

###### PluXml:

Rien pour sauvegarder/déplacer un site PluXml, il y a juste trois étapes
très simples, car seul un rapatriement des dossier du site par ftp, un
copié/collé suffit. Aucune importation d'autre blog que ceux de PluXml
n'est possible. On va supposer qu'on veut déplacer (sur le même site
avec un autre nom de répertoire, ou bien via ftp pour un changement
d’hébergeur):

1.  éditer le fichier data/configuration/parametres.xml en mettant à
    jour la valeur à la ligne 5 de &lt;parametre name="racine"&gt; pour
    donner le nouvel emplacement du site ! On peut aussi le faire dans
    PluXml (menu paramètres).
2.  copier le répertoire PluXml vers sa nouvelle destination.

Et voilà, c'est pas compliqué : il faut juste penser à effectuer l'étape
No1 ... sinon PluXml ne sera pas content. <span
style="text-decoration: underline;"> **ATTENTION :**</span> Si vous avez
des URL sur votre propre site "en dur" (par exemple ce que génère
CKeditor pour les images, documents et smileys), du layout
<http://mon_site_PluXml/data/images/mon_logo.png> ... et bien ça ne
marchera plus. Il faudra donc penser à les changer : un gros coup de
rechercher/remplacer dans tous vos articles. Si vous avez activé la
réécriture d'URL sur votre site il faudra également vérifier/éditer le
fichier .htaccess, à la ligne 5 RewriteBase /xxx/ ou 'xxx' représente le
nouveau nom de dossier (si PluXml est ou va dans un dossier).  

###### SPIP:

Il sauvegarde ses données (la totalité, du simple nom au réglage du
theme... en passant par les médias) dans une base SQLITE que l'on peut
ensuite télécharger. Ensuite on peut importer la base sur un SPIP vierge
ou non, via les outils de restauration. Des plugins sont disponible pour
importer des sites motorisé par différents CMS. Un copier/coller du
dossier racine du site via ftp suffit aussi pour un déménagement,
seulement il faut penser a changer l'adresse du site dans la
configuration.
![](http://download.tuxfamily.org/passionlinux/images/png/spipsave.png)
![](http://download.tuxfamily.org/passionlinux/images/png/spiprestore.png)  

###### Wordpress:

Aucune importation n'est possible par défaut, il faut déjà installer des
plugins. Ensuite tout est possible. Ce site a été importer depuis un
site Dotclear via un plugins. L'exportation est un simple fichier.xml
qui contient tous les billets, catégorie, mots clés...
![](http://download.tuxfamily.org/passionlinux/images/png/wordpressimport.png)  

##### Personnalisation des URLs:

###### Dotclear:

Permet de changer les URLs des prochains billets mais pas ceux qui sont
déjà écrit...
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearurl.png)  

###### PluXml:

Il permet juste le minimum. ici, en l’occurrence, pas grand chose
puisque je suis en locale sans l'option apache.
![](http://download.tuxfamily.org/passionlinux/images/png/pluxmlurl1.png)  

###### SPIP:

SPIP est complet comme toujours.
![](http://download.tuxfamily.org/passionlinux/images/png/spipurl.png){.shrinkToFit
width="1128" height="642"}  

###### Wordpress:

Lui aussi comme SPIP, est complet.
![](http://download.tuxfamily.org/passionlinux/images/png/wordpressurl.png)  

##### Configuration du site (aperçu):

###### Dotclear:

Beaucoup d'option sont disponible, éparpillé un peu dans différents
coins, dans paramètres du blog, mes préférences, about:config...
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearconfig2.png)  

###### PluXml:

Strict minimum, mais ça suffit.
![](http://download.tuxfamily.org/passionlinux/images/png/pluxmlconfig.png)  

###### SPIP:

Beaucoup de possibilité, dans un seul endroit, possible de rajouter des
options par des plugins, notamment avec le plugin "couteau suisse".
![](http://download.tuxfamily.org/passionlinux/images/png/spipconfig.png){.shrinkToFit
.transparent width="1129" height="642"}  

###### Wordpress:

Pas mal de possibilité mais pas toute faisable de façon graphique.
Beaucoup de plugins pour ajouter d'autres configurations.
![](http://download.tuxfamily.org/passionlinux/images/png/wordpressconfig1.png){.transparent}  

##### Site coté public:

###### Dotclear:

La première page contient les articles récents, on peut aussi choisir si
on préfère une page statique. Les articles sont au choix visible en
entier, soit seule les titres sont visible, soit tronquer, soit tronquer
sauf le dernier billet qui lui est en entier. Pour ce qui est des
thèmes, il y en a assez pour se faire un site sympa.
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearsite1.png)
![](http://download.tuxfamily.org/passionlinux/images/png/dotclearsite2.png)  

###### PluXml:

C'est a nous de mettre les châpos pour que le billets ne soit pas en
entier sur la première page. On peut choisir une page statique comme
page d'accueil. Peu de thèmes.
![](http://download.tuxfamily.org/passionlinux/images/png/pluxmlsite1.png){.shrinkToFit
width="1344" height="642"}
![](http://download.tuxfamily.org/passionlinux/images/png/pluxmlsite2.png){.shrinkToFit
width="1344" height="642"}  

###### SPIP:

Tout est réglable... On ne peut pas faire mieux, surtout si on a le
squelette sarka. Peu de thème(suffisamment tout de même) mais beaucoup
de squelettes qui permette d'avoir un site ressemblant a rien d'autre...
On peut aussi piquer les thèmes de Dotclear via un squelette nommer
[spipclear](http://contrib.spip.net/Spip-Clear).
![](http://download.tuxfamily.org/passionlinux/images/png/sitepassionlinuxsarka.png)
![](http://download.tuxfamily.org/passionlinux/images/png/sitepassionlinuxsarka2.png)
![](http://download.tuxfamily.org/passionlinux/images/png/spipsite.png)  

###### Wordpress:

C'est a nous de mettre la mention lire plus lors de la création des
billets, sinon les billets de la 1ere page seront affiché en entier...
Par contre comme les autres, on peut mettre une page statique comme
accueil. Beaucoup mais beaucoup de thèmes disponible, on s'y perd... En
effet plus de 4000 thèmes sont sélectionnable. Pour le moment je reste
avec le "par défaut 2016".
![](http://download.tuxfamily.org/passionlinux/images/png/wordpresssite1.png)  

##### Conclusion:

Chacun de ces CMS ont leurs petits plus et leurs moins, mais je n'ai pas
vu, du moins, par défaut et sans plugins certaines actions possibles
dans SPIP de base, comme: Vider le cache:
![](http://download.tuxfamily.org/passionlinux/images/png/spipcache.png)
Activation ou non des révisions:
![](http://download.tuxfamily.org/passionlinux/images/png/spiprevision.png)
Et d'autres que je me sers.   **Dotclear** est un très bon outils, il
reste a mes yeux plus accessible et plus simple que les autres, a part
Pluxml qui le bat dans la simplicité et par le peu d'option faisable. Le
point noir de cette outils, c'est qu'on ne peut pas dire si il va rester
encore longtemps, il y a 2 ou 3 devs et quelques irréductibles gaulois
qui sont dessus. Les Départs des protagonistes ont fait perdre cette
aspect primordiale pour ceux qui pensent sur le long terme, l'avenir
incertains de cette outils qui a déjà faillit s’éteindre et qui continu
doucement mais sûrement son bonhomme de chemin, donne un doute
raisonnable sur son utilisation. Dommage car il a tout d'un grand, de
plus il est plaisant d’utilisation. Il mériterait que des gens capable
de coder viennent lui redonner de la visibilité. Je pense aussi que les
français ne savent pas vendre leurs produits, que ça soit PluXml, SPIP
ou Dotclear, ils n'ont pas beaucoup de visibilité sur le net la ou les
américains savent bien inonder de leurs produits et même leurs mauvais,
je suis connaisseur en la matière je roule en américaine...   **Pluxml**
est le plus simpliste et le plus facile. Personnellement il m'a suffit a
un moment donné ou j'en avais marre de bloguer, ou je voulais lâcher,
mais une fois que ce doute est passé, il ne suffit plus, en tout cas pas
pour moi, il lui manque trop de choses, les liens internes inexistant,
les plugins et thèmes a chercher et charger sur le site, le peu de
personnalisation accessible en un clic, tout se fait par édition direct
du code php du thème. Alors c'est vrai que celui qui veut juste poser
une phrase de temps en temps ou écrire de longs textes sans trop
d’interactions , peut se contenter de lui. Il est le plus léger, il est
le plus facile a mettre en place, il est aussi le plus rapide... Bref je
conseille quand même largement Dotclear pour faire du blog que PluXml,
il est trés léger pour bien plus de possibilité, il est bien plus
confortable, ect, ...   Ah, c'est au tour de **SPIP**; Mon chouchou, mon
petit animal de compagnie, entre lui et moi c'est une longue histoire,
c'est dix ans de vie ensemble, c'est des déboires a essayer de coder, a
essayer de faire des boucles, a simplement essayer d'avoir autre chose
que le look par défaut... C'est avant tout une mentalité de dons, donner
son savoir, partager ses connaissances. C'est aussi un outils
polyvalent, il n'est pas fait pour du blog mais pour faire du site, de
l’éditorial, et peut très bien se restreindre a faire du blog... C'est
vrai que son administration est vieillotte, mais elle est bien
fonctionnel. Le squelette par défaut permet montrer ce qu'il peut faire,
mais pas tout ce qu'il peut faire, c'est a nous de modifier ce squelette
pour le rendre unique. C'est aussi un outils plus pour les bidouilleurs,
heureusement que des squelettes existent comme celui de sarka pour le
rendre accessible. C'est aussi un CMS un peu extra-terrestre, car qui a
part lui utilise des squelettes? Par contre, aucun autre CMS arrive a
ses chevilles pour ce qui en est de la typographie et de la syntaxe.
Tout est pensé pour celui qui écrit, bien plus facile a retenir, bien
plus compréhensible, bien plus rapide a faire. Bref, un exemple que je
ne cesse de citer c'est les liens internes, mais je peux aussi parler
d'une horreur que je vois fréquemment sur les autres CMS, je suis sur
que vous aussi avez déjà vu, et aussi sur ce site depuis son passage a
dotclear et maintenant wordpress, des "**:**" se baladant seul sur une
ligne? Genre comme ici un long texte et sur la ligne de dessous un **:**
tout seul couper du mot qu'il précède...

    :

C'est horrible. C'est a cause du fait qu'en français les "**:**" sont
espacé par un espace du mot qu'il précède. SPIP respecte automatiquement
les principales règles d’espacement de la typographie française – ainsi
des espaces insécables sont ajoutées automatiquement devant les
caractères « :», « ; », « ! », « ? » -, et place des espaces insécables
avant et après les guillemets « à la française ». Donc pas de
possibilité de voir un caractère comme « :», « ; », « ! », « ? » sur une
ligne tout seul, il sera accompagné du mot avec un espace insécable. Une
**espace insécable** est un [signe typographique
numérique](https://fr.wikipedia.org/wiki/Caract%C3%A8re_%28typographie%29 "Caractère (typographie)")
consistant en une
[espace](https://fr.wikipedia.org/wiki/Espace_typographique "Espace typographique"){.mw-redirect}
que l'on intercale entre deux
[mots](https://fr.wikipedia.org/wiki/Mot "Mot") (ou un mot et une
[ponctuation](https://fr.wikipedia.org/wiki/Ponctuation "Ponctuation"))
qui ne doivent pas être séparés en fin de ligne. L'espace insécable
permet d'éviter qu'un mot, un ensemble de mots, un nombre, une date ou
une ponctuation soient rejetés et isolés au début de la ligne suivante
lorsque cela nuirait à la fluidité de la lecture. Donc sous SPIP, même
si je ne le fais pas  et que j’écris de cette façon:

    jécris de cette façon:

Noter l'absence d'espace entre façon et le ":", il me fera
automatiquement:

    jécris de cette façon :

En plus d'autre bonne chose que SPIP nous arrange.   Dans **Wordpress**
tout peut être faisable, il suffit juste d'installer les plugins qui
font le job, le plus durs est de les choisir dans la quantité
disponible... Je passe a cette outils et je suis plutôt content de le
faire par rapport a ce que j'avais déjà testé auparavant... Je garde un
regret pour Dotclear qui est un très bon moteur de blog, triste qu'il ne
soit pas reconnu comme tel.
