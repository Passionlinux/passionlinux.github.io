---
title: SPIP, un cms pas comme les autres... Pourquoi SPIP et pas un autre ? Partie 8, Joindre des documents multimédia
date: 2016-06-27 23:41
layout: post
---

L’interface de SPIP vous permet de proposer sur votre site des fichiers
multimédia (son, vidéo, textes...).

Les rédacteurs peuvent joindre des documents aux articles. Ces documents
peuvent être soit présentés à la suite du texte (à la façon de « pièces
jointes »), soit présentés à l’intérieur du texte sous la forme d’une
vignette de prévisualisation.

Les administrateurs du site peuvent, de plus, installer des documents
directement dans les rubriques.

Notez bien la différence importante entre ces deux utilisations : joints
aux articles, les documents sont des « pièces jointes », qui n’ont pas
d’intérêt sans l’article auquel ils sont associés (dans la navigation
dans le site, on peut consulter de tels fichiers à partir des
articles) ; lorsqu’ils sont installés directement dans les rubriques,
les documents deviennent des éléments du site comparables aux articles
et aux brèves, et non plus des compléments d’information.

<!--more-->

Étape 1 : **Installation des documents sur le serveur**

![](http://www.spip.net/local/cache-vignettes/L208xH490/ins_doc1gif-f558-92b09.gif){width="208"
height="490"}L’installation des fichiers sur le serveur se fait au
travers de l’interface « Joindre un document » pour les articles, et
« Publier un document dans cette rubrique » pour les rubriques.

Vous remarquerez que, pour les articles, cette interface apparaît à deux
endroits différents : en bas de la page de chaque article, et dans la
colonne de gauche (sous les images) lorsque vous modifiez un article.
Ces interfaces ont exactement la même fonction, mais vous utiliserez
l’une ou l’autre en fonction de vos besoins. Pour les rubriques,
l’installation des documents se fait sur la page de la rubrique
concernée.

Avant d’installer vos fichiers, vous devez les créer sur votre
ordinateur. L’interface d’envoi des documents vous rappelle la liste des
formats autorisés sur ce système. *Veillez absolument à nommer vos
fichiers avec la terminaison correcte (par exemple,* « xxxxxx.mp3 »
*pour un fichier au format MP3.*

L’interface est la même que pour les images : le bouton « Fichier », ou
« File », ou « Parcourir », « Browse » (selon les navigateurs) ouvre une
fenêtre qui vous permet de sélectionner le fichier sur votre disque dur.
Une fois ce fichier sélectionné, cliquez sur « Télécharger » pour
envoyer le fichier. *Attention : selon la taille de votre fichier, cette
opération peut prendre du temps. Notez aussi que, selon les réglages de
l’hébergeur de votre site, les fichiers trop gros pourront être
refusés ; dans ce cas, vous pourrez contourner cette limitation en*
[installant vos fichiers par
FTP](http://www.spip.net/ecrire/?exec=aide&aide=ins_upload&var_lang=fr){.spip_out}.

------------------------------------------------------------------------

Étape 2 : **Informations et vignette**

![](http://www.spip.net/local/cache-vignettes/L211xH452/ins_doc2gif-b01a-3d413.gif){width="211"
height="452"}Une fois le fichier transféré sur le serveur, une boîte
d’information apparaît. Plusieurs opérations peuvent y être réalisées.

-  *Vignette de prévisualisation*

Cette notion est très importante : contrairement aux images, que l’on
insère dans le corps du texte, les documents n’apparaissent pas
directement. Une vignette de prévisualisation est présentée au visiteur,
sur laquelle il pourra cliquer pour obtenir le document correspondant.

La partie supérieure de la boîte d’information vous permet de choisir la
vignette de prévisualisation. Vous pouvez opter pour une *vignette par
défaut*, ou installer un *logo personnalisé*.

La vignette par défaut est installée automatiquement par le système, en
fonction du format du document. L’avantage de laisser une telle vignette
est que la présentation des documents d’un même layout sur l’ensemble de
votre site sera uniforme.

Si vous préférez, vous pouvez installer un logo (de taille réduite de
préférence, et au format GIF, JPG ou PNG), qui apparaîtra à la place de
la vignette par défaut. Une fois un tel logo installé, un lien
« Supprimer la vignette personnalisée » vous permettra de revenir à la
vignette par défaut si nécessaire.

-  Dans la page de modification des articles, les « raccourcis » vous
permettant d’insérer le document dans le corps du texte sont présentés,
identiques à ceux des images.

-  La partie inférieure vous permet de donner un titre et de fournir un
descriptif pour votre document. Inutile d’indiquer ici le format et le
poids du fichier multimédia, cette information sera fournie
automatiquement par le système de publication.

-  Enfin, le bouton « Supprimer ce document » permet d’effacer les
documents inutiles. *Notez bien : il est impératif de supprimer les
documents non désirés, faute de quoi ils apparaîtront sur le site
public.*

-  **Dans le cas des documents installés dans les rubriques,** vous
pouvez de plus modifier la date de mise en ligne du document (sur le
même principe que vous modifiez la date de publication d’un article ou
d’une brève). Une fois ces réglages effectués, les documents des
rubriques sont immédiatement disponibles sur le site public (il n’est
pas nécessaire de les « valider » comme les brèves ou les articles).

------------------------------------------------------------------------

Étape 3 : **Insérer les documents dans le texte des articles**

Pour les documents associés aux articles, vous pouvez vous contenter de
les installer et de préciser les informations (étapes 1 et 2 ci-dessus).
Lorsque vous publierez l’article, ces documents apparaîtront à la suite
du texte sous la forme d’une liste de *documents joints*.

Cependant, vous pouvez également décider d’insérer les vignettes de
prévisualisation à l’intérieur du texte. Vous obtiendrez ainsi des
images cliquables à l’intérieur de l’article.

Ici, la procédure est exactement la même que pour les images, à la
différence près que les vignettes seront des éléments cliquables.
Insérez un raccourci de la forme &lt;imgxx|yy&gt; ou &lt;docxx|yy&gt;
selon que vous voulez afficher uniquement la vignette, ou bien le titre
et le descriptif.

*Notez bien :* les documents que vous aurez installé à l’intérieur du
texte n’appaîtront plus *sous l’article*. Pour les articles, il y a donc
deux emplacements où apparaissent les documents : à l’intérieur du texte
(vignette cliquable), ou à la suite de l’article sous la mention
« Document joint ».

------------------------------------------------------------------------

Cas particulier : **Les documents vidéo et sonores**

Certains formats de fichiers multimédia sont conçus pour être affichés
directement dans une page Web (par exemple une vidéo insérée directement
dans l’article).

Pour pouvoir insérer de tels documents dans le corps de l’article, non
plus sous forme de vignette cliquable, mais en tant qu’animation
multimédia, vous devez indiquer ses dimensions : largeur et hauteur
absolument supérieures à zéro (pour les fichiers audio, on choisira pour
largeur la dimension que l’on souhaite attribuer au curseur de
défilement, et une hauteur réduite, par exemple 25 pixels).

*Notez bien :* les cases vous permettant d’indiquer les dimensions
n’apparaissent que pour les documents dont le fichier correspond à
certains formats acceptés par SPIP pour l’intégration à l’intérieur des
articles (notamment : avi, quicktime, real, flash).

Une fois ces dimensions fixées, un raccourci SPIP supplémentaire vous
sera proposé, de la forme &lt;embxx|yy&gt; (pour mémoire :
« **emb**ed »).

Si vous connaissez bien le fonctionnement de ces layouts d’inclusion,
sachez que vous pouvez ajouter des paramètres supplémentaires, par
exemple :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="2">
&lt;emb54|center|autostart=true|quality=high&gt;

</textarea>
</p>
[Voir en
ligne.](http://www.spip.net/aide/?exec=aide&aide=ins_doc#contenu-aide)
