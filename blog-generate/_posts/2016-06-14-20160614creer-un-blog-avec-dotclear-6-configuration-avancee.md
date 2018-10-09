---
title: Créer un blog avec Dotclear #6 Configuration avancée
date: 2016-06-14 23:53
layout: post
---

<div class="level1">

En suivant depuis l'interface d'administration le lien **about:config**
on a accès aux paramètres de configuration avancée.

<div class="wikinote noteclassic">

**Note :**

<p>
Cette page présente deux onglets : **Paramètres globaux** et
**Paramètres du blog**. Par défaut tout nouveau blog de l'installation
adoptera les indications données dans Paramètre globaux. Si l'on ne veut
modifier certains paramètres que pour un blog précis on les modifiera
dans l'onglet Paramètres du blog.

</div>

Notez que la plupart des paramètres peuvent être renseignés depuis le
tableau de bord du blog puis **Préférences du blog**.

</div>

<!--more-->

### Revue de détail {#revue-de-detail .sectionedit2}

<div class="level3">

 

</div>

#### allow\_comments et allow\_trackbacks

<div class="level4">

Ces deux paramètres autorisent ou interdisent les commentaires et les
trackbacks pour tout le blog.

</div>

#### blog\_timezone

<div class="level4">

Fuseau horaire du blog.

</div>

#### comments\_nofollow

<div class="level4">

Ajoute au lien laissé par les commentateurs vers leur site la propriété
*rel="no-follow"* qui indiquent aux robots d'indexation des moteurs de
recherche de ne pas « suivre » ce lien.

</div>

#### comments\_pub

<div class="level4">

Active ou désactive la publication immédiate des commentaires. Si
l'option choisie est « non » les commentaires sont placés hors ligne en
attente de votre mise en ligne ou suppression.

</div>

#### comments\_ttl

<div class="level4">

Durée d'ouverture des commentaires après publication du billet. Cette
valeur doit s'exprimer en nombre de jours. La valeur 0 correspond à
l'absence de limite.

</div>

#### copyright\_notice

<div class="level4">

Ce champ (qui n'accepte pas d'enrichissement html) permet d'afficher une
note de copyright dans les flux de syndication. Si vous souhaitez
l'afficher également dans vos pages vous pouvez utiliser la fonction
template :

``` {.code}
 {{tpl:BlogCopyrightNotice}}
```

</div>

#### date\_format

<div class="level4">

Mise en forme de la présentation des dates. Les paramètres disponibles
sont listés dans le [Manuel
PHP](http://fr.php.net/manual/fr/function.strftime.php "http://fr.php.net/manual/fr/function.strftime.php"){.urlextern}.

</div>

#### editor

<div class="level4">

Ce champ permet d'indiquer le nom de la personne responsable du contenu
du blog. Cette information sera affichée dans les informations du flux
de syndication.

</div>

#### enable\_html\_filter

<div class="level4">

Active ou désactive le filtrage des balises xhtml. Lorsque cette option
est activée les balises non conformes saisies dans le billet ne sont pas
interprétées.

</div>

#### enable\_xmlrpc

<div class="level4">

Active ou désactive l'interface
[XML/RPC](http://www.xmlrpc.com/ "http://www.xmlrpc.com/"){.urlextern}.

</div>

#### lang

<div class="level4">

Langue du blog.

</div>

#### media\_exclusion

<div class="level4">

Exclure des fichiers du gestionnaire de médias. Par exemple, pour
exclure les fichiers \*.php et \*.py :

``` {.code}
 /.(php|py)$/i
```

</div>

#### media\_img\_m\_size, media\_img\_s\_size et media\_img\_t\_size

<div class="level4">

Détermine les tailles en pixels des miniatures m (medium), s (small) et
t (thumbnail) créées par le gestionnaire de médias. Cette valeur
détermine la taille en pixels du plus grand côté, que ce soit la
longueur ou la largeur.

</div>

#### media\_img\_title\_pattern

<div class="level4">

Motif du titre des images utilisé lors de l'insertion d'une image dans
un billet.

</div>

#### nb\_comment\_per\_feed

<div class="level4">

Détermine le nombre de commentaires affichés dans le flux RSS et Atom
des commentaires.

</div>

#### nb\_post\_per\_feed

<div class="level4">

Détermine le nombre de billets affichés dans le flux et Atom des
billets.

</div>

#### nb\_post\_per\_page

<div class="level4">

Détermine le nombre de billets par page.

</div>

#### post\_url\_format

<div class="level4">

Modèle de formatage des
<abbr title="Uniform Resource Locator">URL</abbr> spécifiques des
billets.

</div>

#### public\_path

<div class="level4">

Emplacement du répertoire des médias depuis le fichier index.php du
répertoire où est installée l'application Dotclear. Le slash final n'est
pas nécessaire.

</div>

#### public\_url

<div class="level4">

<abbr title="Uniform Resource Locator">URL</abbr> du répertoire des
médias. Le slash final n'est pas nécessaire.

<div class="wikinote notetip">

**Astuce :**

<p>
Vous pouvez utiliser une
<abbr title="Uniform Resource Locator">URL</abbr> absolue commençant par
`http://`, pour servir les médias depuis un sous-domaine par exemple.

</div>

</div>

#### robots\_policy

<div class="level4">

Police des robots des moteurs de recherche.

</div>

#### short\_feed\_items

<div class="level4">

Active ou désactive la troncature des flux RSS et Atom. Lorsque cette
option est activée les flux contiennent seulement le début des billets.

</div>

#### theme

<div class="level4">

Thème choisi pour l'affichage du blog.

</div>

#### themes\_path

<div class="level4">

Emplacement du répertoire des thèmes depuis le fichier index.php du
répertoire où est installée l'application Dotclear. Le slash final n'est
pas nécessaire.

</div>

#### themes\_url

<div class="level4">

<abbr title="Uniform Resource Locator">URL</abbr> du répertoire des
thèmes. Le slash final n'est pas nécessaire.

<div class="wikinote notetip">

**Astuce :**

<p>
Vous pouvez utiliser une
<abbr title="Uniform Resource Locator">URL</abbr> absolue commençant par
`http://`, pour servir les thèmes depuis un sous-domaine par exemple.

</div>

</div>

#### time format

<div class="level4">

Mise en forme de l'affichage des heures. Les paramètres disponibles sont
listés dans le [Manuel
PHP](http://fr.php.net/manual/fr/function.strftime.php "http://fr.php.net/manual/fr/function.strftime.php"){.urlextern}.

</div>

#### tpl\_allow\_php

<div class="level4">

Si ce paramètre a pour valeur "oui", permet d'insérer du code PHP dans
ses templates (tout simplement en utilisant les tags &lt;?php, ?&gt;).

</div>

#### tpl\_use\_cache

<div class="level4">

Active ou désactive le cache des templates.

</div>

#### trackbacks\_pub

<div class="level4">

Active ou désactive la publication immédiate des trackbacks. Si l'option
choisie est « non » les trackbacks sont placés hors ligne en attente de
votre mise en ligne ou suppression.

</div>

#### trackbacks\_ttl

<div class="level4">

Durée d'ouverture des trackbacks après publication du billet. Cette
valeur doit s'exprimer en nombre de jours. La valeur 0 correspond à
l'absence de limite.

</div>

#### url\_scan

<div class="level4">

Méthode de lecture des <abbr title="Uniform Resource Locator">URL</abbr>
(path\_info ou query\_string). Si vous souhaitez adopter le path\_info,
assurez-vous que votre hébergeur le supporte.

</div>

#### use\_smilies

<div class="level4">

Active ou désactive l'affichage des smileys dans les billets et les
commentaires.

</div>

#### wiki\_comments

<div class="level4">

Autorise ou interdit l'emploi de la syntaxe wiki dans les commentaires.

[Voir en
ligne.](https://fr.dotclear.org/documentation/2.0/admin/aboutconfig)

</div>
