---
title: Création/Mise à jour de paquets DEB
date: 2016-06-03 12:13
layout: post
---

Après la publication d'un paquet, il sera rapidement nécessaire de le
mettre à jour.

<div class="section">

<div class="titlepage">

<div>

<div>

[](){#newrevision}8.1. Nouvelle révision Debian {#nouvelle-révision-debian .title}
-----------------------------------------------

<p>
[](){#newrevision}

</div>

<p>
[](){#newrevision}

</div>

<p>
[](){#newrevision}

</div>

Soit un rapport de bogue numéroté `#654321`{.literal}, concernantvotre
paquet et décrivant un problème que vous pouvez résoudre. Voici ce
quevous devez faire pour créer une nouvelle révision du paquet :

<div class="itemizedlist">

[](){#newrevision} [](){#newrevision}
-   pour un nouveau correctif :
    <div class="itemizedlist">

    -   configurer le nom du correctif :
        `dquilt newnomdubogue.patch`{.literal}</em></code> ;
    -   déclarer le fichier à modifier :
        `dquilt addfichier-bogué`{.literal}</em></code> ;
    -   corriger le problème dans le paquet source pour le bogue amont ;
    -   l'enregistrer
        en`nomdubogue.patch`{.filename}</em></code> :`dquilt refresh`{.literal} ;
    -   ajouter sa description : `dquilt header -e`{.literal} ;

    </div>

-   pour la mise à jour d'un correctif :
    <div class="itemizedlist">

    -   rappeler le correctif`toto.patch`{.filename}</em></code>
        existant :`dquilt pop toto.patch`{.literal}</em></code> ;
    -   corriger le problème dans
        l'ancien`toto.patch`{.filename}</em></code> ;
    -   mettre à jour
        `toto.patch`{.filename}</em></code> :`dquilt refresh`{.literal} ;
    -   mettre à jour sa description : `dquilt header -e`{.literal} ;
    -   appliquer tous les correctifs en enlevant les
        approximations(<span class="emphasis">*fuzz*</span>) :
        `while dquilt push; do dquilt refresh;done`{.literal} ;

    </div>

<!-- -->

-   [](){#newrevision}[](){#newrevision}ajouter une nouvelle révision au
    début du fichier`changelog`{.filename} Debian, par exemple avec
    `dch-i`{.literal}, ou explicitement avec
    `dch -vversion`{.literal}</em>-*`révision`*</code>,et ajoutez
    ensuite les commentaires en utilisant votre
    éditeurfavori ;[^\[78\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#ftn.idp39901104){#idp39901104
    .footnote}
-   ajouter une courte description du bogue et de la solution dans
    l'entrée duchangelog, suivie par `Closes: #654321`{.literal}. De
    cette manière,le rapport de bogue sera <span
    class="emphasis">*automagiquement*</span> fermé par lelogiciel de
    maintenance des archives une fois le paquet accepté dansl'archive
    Debian ;
-   répéter les opérations précédentes pour corriger plus de bogues tout
    enmettant à jour le fichier `changelog`{.filename}
    avec`dch`{.literal} selon votre besoin ;
-   recommencer ce qui a été fait en [Section 6.1, « Reconstruction
    complète »](https://www.debian.org/doc/manuals/maint-guide/build.fr.html#completebuild "6.1. Reconstruction complète"){.xref}
    et [Chapitre 7, *Contrôle des erreurs du
    paquet*](https://www.debian.org/doc/manuals/maint-guide/checkit.fr.html "Chapitre 7. Contrôle des erreurs du paquet"){.xref} ;
-   une fois satisfait, modifier la valeur de distribution
    dans`changelog`{.filename} d'`UNRELEASED`{.literal} à la valeurde
    distribution cible `unstable`{.literal} (ou
    même`experimental`{.literal}).
    [^\[79\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#ftn.idp39910880){#idp39910880
    .footnote}
-   envoyer le paquet comme en [Chapitre 9, *Envoi de
    paquet*](https://www.debian.org/doc/manuals/maint-guide/upload.fr.html "Chapitre 9. Envoi de paquet"){.xref}.
    La différence est quecette fois, l'archive source originale ne sera
    pas incluse, car elle n'a pasété modifiée et est déjà dans
    l'archive Debian.

</div>

<p>
Un cas délicat peut se produire quand vous faites un paquet local
pourexpérimenter l'empaquetage avant d'envoyer la version normale vers
l'archiveofficielle, par exemple`1.0.1`{.literal}</em>-*`1`*</code>.Pour
des mises à niveau plus en douceur, il vaut mieux créer une entrée
de`changelog`{.filename} avec une chaîne de version
comme`1.0.1`{.literal}</em>-*`1~rc1`*</code>.Vous pouvez nettoyer le
`changelog`{.filename} en fusionnant cesentrées de modification en une
unique entrée pour le paquetofficiel. Consultez [Section 2.6, « Nom et
version de
paquet »](https://www.debian.org/doc/manuals/maint-guide/first.fr.html#namever "2.6. Nom et version de paquet"){.xref}
pour l'ordre des chaînes deversion.  
<!--more-->

</div>

<div class="section">

<div class="titlepage">

<div>

<div>

[](){#inspectnewupstream}8.2. Examen d'une nouvelle version amont {#examen-dune-nouvelle-version-amont .title}
-----------------------------------------------------------------

<p>
[](){#inspectnewupstream}

</div>

<p>
[](){#inspectnewupstream}

</div>

<p>
[](){#inspectnewupstream}

</div>

Lors de la préparation de paquets d'une nouvelle version amont
pourl'archive Debian, vous devez commencer par vérifier la nouvelle
versionamont. Commencez par lire les `changelog`{.filename}
et`NEWS`{.filename} amonts, ainsi que toute autre
documentationdistribuée avec la nouvelle version. Examinez ensuite les
modifications entre les anciennes et nouvelles sourcesamont, pour
guetter tout changement suspect :

``` {.screen}
$ diff -urN toto-ancienneversion toto-nouvelleversion
```

<p>
Les modifications de certains fichiers automatiquement créés par
Autotoolscomme `missing`{.filename},
`aclocal.m4`{.filename},`config.guess`{.filename},
`config.h.in`{.filename},`config.sub`{.filename},
`configure`{.filename},`depcomp`{.filename},
`install-sh`{.filename},`ltmain.sh`{.filename} et
`Makefile.in`{.filename} peuventêtre ignorées. Vous pouvez les effacer
avant d'exécuter<span class="command">**diff**</span> pour examiner les
sources.

</div>

[](){#inspectnewupstream}

<div class="section">

[](){#inspectnewupstream}
<div class="titlepage">

[](){#inspectnewupstream}
<div>

[](){#inspectnewupstream}
<div>

[](){#inspectnewupstream}  
[](){#inspectnewupstream}[](){#newupstream}8.3. Nouvelle version amont {#nouvelle-version-amont .title}
----------------------------------------------------------------------

<p>
[](){#newupstream}

</div>

<p>
[](){#newupstream}

</div>

<p>
[](){#newupstream}

</div>

[](){#newupstream}[](){#newupstream}Si un paquet
`toto`{.systemitem}</em></code> est correctementempaqueté au nouveau
format `3.0 (native)`{.literal} ou`3.0 (quilt)`{.literal}, empaqueter
une nouvelle version amontconsiste essentiellement à déplacer l'ancien
répertoire`debian`{.filename} dans les nouvelles sources. Ce peut être
réaliséen exécutant
`tar xvzf/chemin`{.literal}</em>/*`vers`*/*`toto`*\_*`ancienneversion`*.debian.tar.gz</code>depuis
la nouvelle arborescence source décompressée.
[^\[80\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#ftn.idp39936912){#idp39936912
.footnote} Bien sûr, vous devez vous occuper de quelquesroutines
évidentes :

<div class="itemizedlist">

-   création d'une copie des sources amont dans un
    fichier`toto_nouvelleversion`{.filename}</em>.orig.tar.gz</code> ;
-   mise à jour du ficher `changelog`{.filename} Debian
    avec`dch -vnouvelleversion`{.literal}</em>-*`1`*</code> :
    <div class="itemizedlist">

    -   ajout d'une entrée avec `New upstream release.`{.literal}
        (nouvelleversion amont) ;
    -   description succincte des modifications <span
        class="emphasis">*dans la nouvelle versionamont*</span> qui
        corrigent des bogues et ferment les rapports associésen ajoutant
        `Closes:#numéro_de_bogue`{.literal}</em></code> ;
    -   description succincte des modifications <span
        class="emphasis">*à la nouvelle versionamont*</span> par le
        responsable qui corrigent des bogues et ferment lesrapports
        associés en ajoutant
        `Closes:#numéro_de_bogue`{.literal}</em></code> ;

    </div>

-   application de tous les correctifs en enlevant les
    approximations(« <span class="emphasis">*fuzz*</span> ») :
    `while dquilt push; do dquiltrefresh; done`{.literal}.

</div>

Si la fusion des correctifs ne s'applique pas proprement, examinez
lasituation (des indices sont laissés dans les
fichiers`.rej`{.filename}) :

<div class="itemizedlist">

-   si un correctif appliqué aux sources a été intégré aux sources
    amont :
    <div class="itemizedlist">

    -   `dquilt delete`{.literal} pour l'enlever ;

    </div>

-   si un correctif appliqué aux sources entre en confit avec les
    nouvellesmodifications des sources amont :
    <div class="itemizedlist">

    -   `dquilt push -f`{.literal} pour appliquer les anciens correctifs
        touten forçant les rejets
        comme`truc`{.filename}</em>.rej</code> ;
    -   édition manuelle du fichier`truc`{.filename} pour obtenir
        lerésultat attendu de`truc`{.filename}</em>.rej</code> ;
    -   `dquilt refresh`{.literal} pour mettre à jour le correctif ;

    </div>

-   continuer comme d'habitude avec
    `while dquilt push; do dquiltrefresh; done`{.literal}.

</div>

Cette méthode peut être automatisé avec <span class="citerefentry"><span
class="refentrytitle">uupdate</span>(1)</span> :

``` {.screen}
$ apt-get source toto...dpkg-source: info: extraction de toto dans toto-ancienneversiondpkg-source: info: extraction de toto_ancienneversion.orig.tar.gzdpkg-source: info: extraction de toto_ancienneversion-1.debian.tar.gz$ ls -Ftoto-ancienneversion/toto_ancienneversion-1.debian.tar.gztoto_ancienneversion-1.dsctoto_ancienneversion.orig.tar.gz$ wget http://example.org/toto/toto-nouvelleversion.tar.gz$ cd toto-ancienneversion$ uupdate -v nouvelleversion ../toto-nouvelleversion.tar.gz$ cd ../toto-nouvelleversion$ while dquilt push; do dquilt refresh; done$ dch... documentation des modifications réalisées
```

<p>
Si le fichier `debian/watch`{.filename} est configuré comme décriten
[Section 5.22,
« `watch`{.filename} »](https://www.debian.org/doc/manuals/maint-guide/dother.fr.html#watch "5.22. watch"){.xref},
la commande <span class="command">**wget**</span> estinutile. Exécutez
simplement <span class="citerefentry"><span
class="refentrytitle">uscan</span>(1)</span> dans le
répertoire`toto`{.filename}</em>-*`ancienneversion`*</code>à la place de
la commande <span class="command">**uupdate**</span> suffit. Les
sourcesmises à jour seront <span
class="emphasis">*automagiquement*</span> recherchées,téléchargées, et
la commande <span class="command">**uupdate**</span> seraexécutée.
[^\[81\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#ftn.idp39985632){#idp39985632
.footnote} Vous pouvez publier ces sources mises à jour en recommençant
ce qui a étéfait en [Section 6.1, « Reconstruction
complète »](https://www.debian.org/doc/manuals/maint-guide/build.fr.html#completebuild "6.1. Reconstruction complète"){.xref},
[Chapitre 7, *Contrôle des erreurs du
paquet*](https://www.debian.org/doc/manuals/maint-guide/checkit.fr.html "Chapitre 7. Contrôle des erreurs du paquet"){.xref}
et [Chapitre 9, *Envoi de
paquet*](https://www.debian.org/doc/manuals/maint-guide/upload.fr.html "Chapitre 9. Envoi de paquet"){.xref}.

</div>

<div class="section">

<div class="titlepage">

<div>

<div>

[](){#packagestyle}8.4. Mise à jour du style d'empaquetage {#mise-à-jour-du-style-dempaquetage .title}
----------------------------------------------------------

<p>
[](){#packagestyle}

</div>

<p>
[](){#packagestyle}

</div>

<p>
[](){#packagestyle}

</div>

[](){#packagestyle}[](){#packagestyle}La mise à jour du style
d'empaquetage n'est pas nécessaire lors de la mise àjour d'un paquet.
Néanmoins, le faire permet de profiter de tout lepotentiel du système
`debhelper`{.systemitem}moderne et du format source `3.0`{.literal} :
[^\[82\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#ftn.idp39993344){#idp39993344
.footnote}

<div class="itemizedlist">

-   si vous devez, pour quelque raison que ce soit, recréer des fichiers
    modèlesqui avaient été effacés, vous pouvez exécuter <span
    class="command">**dh\_make**</span> ànouveau depuis le répertoire
    des sources Debian, avec l'option`--addmissing`{.literal}. Puis
    modifiez-les de façon adéquate ;
-   si le paquet n'a pas été mis à jour pour utiliser la syntaxe<span
    class="command">**dh**</span> de `debhelper`{.systemitem} v7+ dans
    le fichier`debian/rules`{.filename}, mettez-le à jour pour
    utiliser<span class="command">**dh**</span>. Mettez à jour le
    fichier`debian/control`{.filename} en conséquence ;
-   si vous voulez mettre à jour le fichier `rules`{.filename} créé
    avecle mécanisme d'héritage `Makefile`{.filename} du système
    decompilation usuel Debian (`cdbs`{.systemitem}) versla syntaxe
    <span class="command">**dh**</span>, consultez les documents
    suivants pourcomprendre ses variables de configuration
    `DEB_*`{.literal} :
    <div class="itemizedlist">

    -   copie locale de
        `/usr/share/doc/cdbs/cdbs-doc.pdf.gz`{.filename} ;
    -   [Le système de compilation usuel Debian
        (CDBS),FOSDEM 2009](http://meetings-archive.debian.net/pub/debian-meetings/2009/fosdem/slides/The_Common_Debian_Build_System_CDBS/){.ulink} ;

    </div>

-   si vous avez un paquet source `1.0`{.literal} sans
    fichier`toto`{.filename}</em>.diff.gz</code>, vous pouvez lemettre à
    jour au récent format source `3.0 (native)`{.literal} encréant
    `debian/source/format`{.filename} contenant`3.0 (native)`{.literal}.
    Le reste des fichiers`debian/*`{.filename} peut être simplement
    copié ;
-   si vous avez un paquet source `1.0`{.literal} avec
    fichier`toto`{.filename}</em>.diff.gz</code>, vous pouvez lemettre à
    jour au récent format source `3.0 (quilt)`{.literal} encréant
    `debian/source/format`{.filename} contenant`3.0 (quilt)`{.literal}.
    Le reste des fichiers`debian/*`{.filename} peut être
    simplement copié. Importez lefichier `gros.diff`{.filename} créé par
    la
    commande`filterdiff -z -x '*/debian/*'toto`{.literal}</em>.diff.gz &gt;
    gros.diff</code> dans votresystème <span
    class="command">**quilt**</span>, au besoin ;
    [^\[83\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#ftn.idp40017184){#idp40017184
    .footnote}
-   si l'empaquetage a été créé en utilisant un autre système de
    correctif comme`dpatch`{.systemitem}, `dbs`{.systemitem} ou
    `cdbs`{.systemitem} avec `-p0`{.literal},`-p1`{.literal} ou
    `-p2`{.literal}, convertissez-le à`quilt`{.systemitem} avec
    `deb3`{.filename}disponible en <http://bugs.debian.org/581186> ;
-   si l'empaquetage a été créé avec la commande <span
    class="command">**dh**</span> et leparamètre
    `--with quilt`{.literal} ou les commandes<span
    class="command">**dh\_quilt\_patch**</span> et <span
    class="command">**dh\_quilt\_unpatch**</span>,enlevez-les et
    utilisez le nouveau format source`3.0 (native)`{.literal}.

</div>

<p>
Vous devriez consulter les [propositions d'améliorationsDebian (DEP -
Debian Enhancement Proposals)](http://dep.debian.net/){.ulink} et
adopter lespropositions marquées « ACCEPTED ». Les autres tâches
décrites en [Section 8.3, « Nouvelle version
amont »](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#newupstream "8.3. Nouvelle version amont"){.xref}
sont aussi àeffectuer.

</div>

<div class="section">

<div class="titlepage">

<div>

<div>

[](){#utf8}8.5. Conversion en UTF-8 {#conversion-en-utf-8 .title}
-----------------------------------

<p>
[](){#utf8}

</div>

<p>
[](){#utf8}

</div>

<p>
[](){#utf8}

</div>

[](){#utf8}[](){#utf8}Si les documents amonts sont encodés avec
d'anciens jeux de caractères, lesconvertir en
[UTF-8](http://fr.wikipedia.org/wiki/UTF-8){.ulink} peut être utile :

<div class="itemizedlist">

-   avec <span class="citerefentry"><span
    class="refentrytitle">iconv</span>(1)</span> pour convertir
    l'encodage defichiers texte :

    ``` {.screen}
    iconv -f latin1 -t utf8 truc_entrée.txt > truc_sortie.txt
    ```

-   avec <span class="citerefentry"><span
    class="refentrytitle">w3m</span>(1)</span> pour convertir les
    fichiers HTML enfichier texte UTF-8. Assurez-vous d'exécuter cette
    commande avec desparamètres régionaux en UTF-8 :

    ``` {.screen}
    LC_ALL=en_US.UTF-8 w3m -o display_charset=UTF-8         -cols 70 -dump -no-graph -T text/html         < foo_in.html > truc_sortie.txt
    ```

</div>

</div>

<div class="section">

<div class="titlepage">

<div>

<div>

[](){#reminders}8.6. Rappels pour la mise à jour de paquets {#rappels-pour-la-mise-à-jour-de-paquets .title}
-----------------------------------------------------------

<p>
[](){#reminders}

</div>

<p>
[](){#reminders}

</div>

<p>
[](){#reminders}

</div>

Voici quelques rappels pour la mise à jour de paquets :

<div class="itemizedlist">

[](){#reminders} [](){#reminders}
-   préservez les anciennes entrées `changelog`{.filename} (cela va
    desoit, mais des personnes ont parfois utilisé `dch`{.literal} au
    lieude `dch -i`{.literal}) ;
-   les modifications Debian existantes doivent être réévaluées ; jetez
    tout cequi a été incorporé en amont (sous une forme ou une autre),
    et souvenez-vousde garder ce qui ne l'a pas été, à moins qu'il n'y
    ait une bonne raison dene pas le faire ;
-   si le système de construction a été modifié (avec un peu de chance,
    vousêtes au courant depuis l'inspection des modifications amont),
    mettez à jourles dépendances de construction
    `debian/rules`{.filename} et`debian/control`{.filename}, si besoin
    est ;

<!-- -->

-   [](){#reminders}[](){#reminders}vérifiez dans le [système de gestion
    de bogues(BTS)](http://www.debian.org/Bugs/){.ulink} que personne
    n'a fourni de correctifs aux bogues ouverts ;
-   vérifiez le contenu du fichier `.changes`{.filename} pour
    vousassurer que vous envoyez vers la bonne distribution, que les
    rapports debogue refermés sont correctement listés dans les
    champs`Closes`{.literal}, que les champs `Maintainer`{.literal}
    et`Changed-By`{.literal} correspondent, que le fichier est
    signé avecGPG, etc.

</div>

</div>

<div class="footnotes">

------------------------------------------------------------------------

<div id="ftn.idp39901104" class="footnote">

[^\[78\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#idp39901104){.para}Pour
obtenir la date au format voulu, utilisez `LANG=C date-R`{.literal}.

</div>

<div id="ftn.idp39910880" class="footnote">

[^\[79\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#idp39910880){.para}Si
vous utilisez la commande `dch -r`{.literal} pour faire cettedernière
modification, n'oublier pas de sauver le fichier`changelog`{.filename}
explicitement dans l'éditeur.

</div>

<div id="ftn.idp39936912" class="footnote">

[^\[80\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#idp39936912){.para}
Si un paquet `toto`{.systemitem} est empaquetéavec l'ancien format
`1.0`{.literal}, ce peut plutôt être réalisé enexécutant
`zcat/chemin`{.literal}</em>/*`vers`*/*`toto`*\_*`ancienneversion`*.diff.gz|patch-p1</code>
depuis la nouvelle arborescence source décompressée.

</div>

<div id="ftn.idp39985632" class="footnote">

[^\[81\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#idp39985632){.para}
Si la commande <span class="command">**uscan**</span> télécharge les
sources mises à jourmais n'exécute pas la commande <span
class="command">**uupdate**</span>, vous devriezcorriger le fichier
`debian/watch`{.filename} pour avoir`debian uupdate`{.literal} après
l'URL.

</div>

<div id="ftn.idp39993344" class="footnote">

[^\[82\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#idp39993344){.para}
Si votre parrain ou d'autres responsables s'opposent à la mise à jour
dustyle d'empaquetage existant, ne vous embêtez pas à argumenter. Il y a
deschoses plus importantes à faire.

</div>

<div id="ftn.idp40017184" class="footnote">

[^\[83\]^](https://www.debian.org/doc/manuals/maint-guide/update.fr.html#idp40017184){.para}vous
pouvez découper `gros.diff`{.filename} en plusieurs petitscorrectifs
incrémentaux avec la commande <span
class="command">**splitdiff**</span>.
Voir en ligne :
[debian.org](https://www.debian.org/doc/manuals/maint-guide/update.fr.html){.spip_out}

</div>

</div>
