---
title: SPIP, un cms pas comme les autres... Pourquoi SPIP et pas un autre ? Partie 7, Insérer des images dans le texte
date: 2016-06-26 23:36
layout: post
---
 

 

<!--more-->

SPIP vous offre la possibilité d’illustrer vos articles et vos brèves
avec des images. Cela s’effectue en plusieurs étapes : vous devez
envoyer le fichier de votre image vers le site, puis insérer l’image à
l’intérieur du texte.

------------------------------------------------------------------------

SPIP vous offre la possibilité d’illustrer vos articles et vos brèves
avec des images. Cela s’effectue en plusieurs étapes : vous devez
envoyer le fichier de votre image vers le site, puis insérer l’image à
l’intérieur du texte.

------------------------------------------------------------------------

Préparation : **Formats d’images**

Lorsque vous créez vos images (avec votre logiciel habituel), vous devez
les créer à l’un des formats suivants :  
-  GIF (extension **.gif**),  
-  JPEG (extension **.jpg**),  
-  PNG (extension **.png**).

Veillez particulièrement à ce que le nom de vos fichiers ait une
*terminaison* indiquant leur format : **.gif**, **.jpg** ou **.png**. Si
vous installez un fichier dont le nom ne contient pas cette extension,
le système ne saura pas utiliser l’image.

------------------------------------------------------------------------

Étape 1 : **Installation des images sur le serveur**

![](http://www.spip.net/local/cache-vignettes/L211xH345/ins_img1gif-7edb-4e254.gif){width="211"
height="345"}Avant de pouvoir insérer vos images à l’intérieur du texte,
il faut bien entendu installer ces images sur le serveur. Cela se fait,
dans SPIP, par l’interface graphique.

Lorsque vous « modifiez » un article ou une brève, la colonne de gauche
vous propose une interface intitulée : « Ajouter une image ». Cela se
présente sous la forme d’un *champ* suivi d’un bouton nommé, suivant les
navigateurs, « parcourir », « Browse », « Sélectionner », « File »,
« Fichier »...

Lorsque vous cliquez sur ce bouton, une interface s’ouvre, vous
permettant de visiter votre disque dur et d’indiquer quel fichier
graphique vous voulez sélectionner.

Cela fait, cliquez sur le bouton intitulé « Télécharger ».

Si l’opération a réussi, votre image apparaît dans la colonne de gauche,
complétée de plusieurs indications...

------------------------------------------------------------------------

Étape 2 : **Les informations liées à votre image**

![](http://www.spip.net/local/cache-vignettes/L209xH471/ins_img2gif-b89b-4f215.gif){width="209"
height="471"}Une fois votre image envoyée au serveur, une case apparaît
sur la gauche de l’écran. Il y a là toutes les informations nécessaires
qui la concernent. (Une partie de ces informations apparaît masquée,
cliquer sur le triangle pour « déplier » la boîte d’information.)

-  *Affichage sous forme de vignette*. Une prévisualisation de votre
image apparaît. Si l’image est de grande taille (plus de 200 pixels de
large), c’est une version de taille réduite qui est affichée.

-  *Raccourcis SPIP*. Voir ci-après : SPIP vous rappelle les 3
« raccourcis » qui vous permettent d’insérer cette image à l’intérieur
de votre texte. Notez que chaque image est « numérotée » ainsi :
« IMG1 », « IMG2 »... Ces « raccourcis » sont utilisés dans la troisième
étape.

-  *Taille de l’image.* Juste au-dessus de l’image, la largeur et la
hauteur de votre image (en pixels - ou « points ») sont rappelées.

-  *Titre et description de l’image.* Vous pouvez, si vous le désirez,
indiquer un nom et une description pour chaque image. Par exemple une
explication, ou une mention du copyright du photographe...

-  *Supprimer cette image.* Comme son nom l’indique, le bouton
« Supprimer cette image » permet d’effacer ce fichier, si vous avez fait
une erreur de manipulation, ou si vous décidez finalement de ne pas
utiliser l’image dans ce texte. Il est conseillé d’effacer les images
inutilisées, afin d’éviter d’encombrer votre serveur avec des fichiers
inutiles.

Vous pouvez recommencer l’opération avec autant d’images que vous le
désirez (un article ou une brève peuvent contenir autant d’images que
nécessaire).

------------------------------------------------------------------------

Étape 3 : **Insérer une image à l’intérieur du texte**

A ce stade, les fichiers graphiques sont bien présents sur le serveur,
mais il reste à indiquer à quel endroit de votre texte vous voulez les
insérer. Pour cela, inutile de faire du HTML, SPIP vous propose un
« raccourci » permettant d’insérer votre image simplement.

-  *Images sans commentaire*

Pour chaque image, voyez la mention des 3 raccourcis :  
-  &lt;img1|left&gt;  
-  &lt;img1|center&gt;  
-  &lt;img1|right&gt;

Recopiez l’un de ces raccourcis (le nombre correspond au numéro de
l’image, il change donc pour chaque fichier), et recopiez-le à
l’intérieur de la case « Texte », là vous désirez le situer dans votre
article. « left » aligne l’image à gauche, « right » à droite, et
« center » place votre image au centre du texte.

Lors de l’affichage à l’écran, SPIP remplacera ces raccourcis par le
code HTML correspondant, en calculant automatiquement la taille des
images.

-  *Images avec titre et description*

Si vous avez indiqué un titre et/ou une description, les mentions
<img...> sont remplacées par :  
-  &lt;doc1|left&gt;  
-  &lt;doc1|center&gt;  
-  &lt;doc1|right&gt;</img...>

Elles s’utilisent de la même façon que ci-dessus ; cependant, lorsque
vous insérez un « raccourci » de ce layout, SPIP insère dans votre texte
non seulement l’image, mais le titre et la description que vous lui avez
donnée. Votre image apparaît ainsi avec, éventuellement, une explication
et des mentions de copyright, le nom de l’artiste, etc.

[Voir en
ligne.](http://www.spip.net/aide/?exec=aide&aide=ins_img#contenu-aide)
