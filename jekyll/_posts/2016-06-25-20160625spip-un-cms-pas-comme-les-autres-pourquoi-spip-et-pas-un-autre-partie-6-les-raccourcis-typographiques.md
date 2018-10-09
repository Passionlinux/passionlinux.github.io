---
title: SPIP, un cms pas comme les autres... Pourquoi SPIP et pas un autre ? Partie 6, Les raccourcis typographiques
date: 2016-06-25 10:40
layout: post
---

Dans l'article **"[Pourquoi Dotclear et pas SPIP, PluXml ou
Wordpress?](/index.php?post/Pourquoi-Dotclear-et-pas-SPIP%2C-PluXml-ou-Wordpress){.ref-post}"**
, je disais a quel point j'appréciais SPIP et sa typographie spécifique,
je laisse donc un peu de coté la série sur Dotclear pour continuer celle
de SPIP, et quoi de mieux que de parler de l'un de ses grands points
forts ?

![](http://www.spip.net/squelettes/img/spip.png)

**Pour faciliter la mise en page des documents publiés avec SPIP, le
système propose un certain nombre de « raccourcis SPIP » destinés :  
-  à simplifier l’utilisation par des utilisateurs ne connaissant pas le
HTML ;  
-  à faciliter le traitement automatique de la mise en page.**

Par conséquent naturellement vous pouvez toujours utiliser le code HTML
dans vos documents SPIP, mais nous vous conseillons d’utiliser de
préférence ces quelques raccourcis SPIP (peu nombreux), qui sont
beaucoup plus faciles à mémoriser et plus particulièrement permettent au
système certaines opérations automatisées.

<!--more-->

### Les raccourcis typographiques simples de SPIP {#les-raccourcis-typographiques-simples-de-spip .spip}

Dans un premier temps, nous présentons ici les raccourcis typographiques
les plus courants et les plus simples. Pour les utilisateurs qui
souhaiteraient affiner encore le contrôle de la mise en forme de leurs
textes, nous présenterons des versions plus complexes de ces raccourcis.

*N.B.* Les raccourcis simples répondent déjà largement à la grande
majorité des besoins, et permettent de publier en ligne presque aussi
simplement que l’on écrit un mail.

-  **Typographie française automatique**

SPIP respecte automatiquement les principales règles d’espacement de la
typographie française - ainsi des espaces insécables sont ajoutées
devant les caractères « :», « ; », « ! », « ? » -, et place des espaces
insécables avant et après les guillemets « à la française ».

(Note : cette fonctionnalité n’est activée que sur les sites dont la
langue principale est le français.)

-  **Créer des paragraphes**

Pour créer des paragraphes, il suffit de laisser une ligne vide, un peu
comment on sépare les paragraphes dans un email (on « saute » une
ligne).

Le fait de simplement « revenir à la ligne » (retour-chariot) sans
séparer les deux paragraphes par une ligne vide ne suffit pas pour
provoquer un changement de paragraphe (cela ne provoque même pas un
retour à la ligne).

Vous pouvez laisser plusieurs lignes vides à la suite sans que cela
modifie la présentation.

[]()  
-  **Insérer une puce**

On peut insérer une puce en début de ligne dans SPIP : il suffit de
revenir à la ligne et de commencer la nouvelle ligne avec un tiret
(« - »).

Notez : ici un simple retour à la ligne suffit (on peut faire des
énumérations dans le même paragraphe) ; mais si l’on « saute » une ligne
avant la ligne commençant par un tiret, une ligne vide est affichée
avant l’énumération.

Par exemple,

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="7">
- Qu'est-ce que cela peut faire que je lutte pour la mauvaise cause
puisque je suis de bonne foi? - Et qu'est-ce que ça peut faire que je
sois de mauvaise foi puisque c'est pour la bonne cause. (Jacques
Prévert)

</textarea>
</p>
sera affiché ainsi :

> -  Qu’est-ce que cela peut faire que je lutte pour la mauvaise cause
> puisque je suis de bonne foi ?  
> -  Et qu’est-ce que ça peut faire que je sois de mauvaise foi puisque
> c’est pour la bonne cause. (Jacques Prévert)

On notera qu’il s’agit bien d’insérer une *puce* et non de créer une
liste ([pour créer des listes
voir](http://www.spip.net/aide/?aide=raccourcis#listes){.spip_ancre})

-  **Gras et italique**

On indique simplement du texte *en italique* en le plaçant entre des
accolades simples : « `...du texte {en italique} en...` ».

On indique du texte **en gras** en le plaçant entre des accolades
doubles : « `...du texte {{en gras}} en...` ».

-  **Intertitres**

Les intertitres sont des titres à l’intérieur d’un texte permettant d’en
indiquer la structure. Dans SPIP, on les indique très simplement en les
plaçant entre des accolades triples : « `{{{Un titre de partie}}}` »
affichera le texte en gras et centré :

> ### Un titre de partie {#un-titre-de-partie .spip}

-  **Trait de séparation horizontal**

Il est très simple d’insérer un trait de séparation horizontal sur toute
la largeur du texte : il suffit de placer une ligne ne contenant qu’une
succession d’au moins quatre tirets, ainsi :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="2">
----

</textarea>
</p>
donne :

> ------------------------------------------------------------------------

------------------------------------------------------------------------

-  **Les liens hypertextes**

On fabriquera facilement un lien hypertexte avec le code suivant :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="2">
SPIP est une initiative du \[minirézo-&gt;http://www.minirezo.net/\].

</textarea>
</p>
devient :

> SPIP est une initiative du
> [minirézo](http://www.minirezo.net/){.spip_out}.

(Mnémotechnique : le tiret suivi d’un chevron dessine une sorte de
flèche qui indique que le texte du lien (avant la flèche) « pointe
vers » une adresse.)

L’adresse du lien peut être une adresse absolue (commençant, comme ici,
par `http://`{.spip_code dir="ltr"}), une adresse relative (vers une
autre page du même site), un lien vers un document utilisant un
protocole de l’internet (`ftp://`{.spip_code dir="ltr"}...), une adresse
email (« `[->minirezo@rezo.net]`{.spip_code dir="ltr"} »)...

Application spécifique : vous pouvez afficher en toutes lettres un lien
cliquable sous la forme d’une adresse URL, en n’indiquant rien avant la
« flèche ». Par exemple :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="2">
\[-&gt;http://dmoz.org/World/Deutsch/Kultur/Literatur/Autoren\_und\_Autorinnen/P/Proust,\_Marcel/\]

</textarea>
</p>
affiche :

> [http://dmoz.org/World/Deutsch/Kultu...](http://dmoz.org/World/Deutsch/Kultur/Literatur/Autoren_und_Autorinnen/P/Proust,_Marcel/){.spip_url
> .spip_out}

Notez que, dans le cas des URL très longues, l’affichage est tronqué
(pour éviter de dégrader votre interface graphique), mais le lien
hypertexte pointe vers la bonne adresse.

[]()

Il est possible de préciser la langue de la page vers laquelle le lien
pointe, ce que les navigateurs afficheront à leur convenance. Pour cela,
il faut mettre le code-langue entre accolades.

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="2">
\[Un site en français{fr}-&gt;http:///www.adresse.tld\]

</textarea>
</p>
Cela est particulièrement recommandé lorsque la page de destination
n’est pas dans la même langue que votre texte.

Si l’on veut donner beaucoup d’informations sur le lien sans allonger
excessivement la zone cliquable, on peut provoquer l’apparition d’une
info-bulle en plaçant avant la flèche le signe | suivi du texte
souhaité :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="2">
\[voir ici|Ce lien vous expliquera tout ce qu'il faut
savoir-&gt;http:///www.adresse.tld\]

</textarea>
</p>
affichera `voir ici`, le reste du texte n’apparaissant qu’au survol.

-  **Liens hypertextes à l’intérieur du site**

Ce même système de liens hypertextes facilite, de plus, la création de
liens à l’intérieur de votre site sous SPIP. La seule subtilité consiste
à repérer le *numéro* de l’article, de la rubrique, ou de la brève vers
laquelle vous voulez mener votre lien hypertexte :
![NUMERO](http://www.spip.net/local/cache-vignettes/L200xH65/articlenumerca71-4aa1e.gif){width="200"
height="65"} lorsque vous « visitez », dans l’espace privé, un article,
une brève ou une rubrique, la colonne de gauche contient un pavé
indiquant, en gros caractères, ce numéro.

C’est ce numéro que vous allez indiquer dans le lien hypertexte :

-   Lien vers l’article 342 (quatre possibilités) :  
   `lien vers [l'article->342]     lien vers [l'article->art342]     lien vers [l'article->article 342] `  
   Application spécifique : `[->art342]` (on n’a rien indiqué avant
    la « flèche ») affichera automatiquement le titre de l’article 342
    avec un lien vers cet article.

<!-- -->

-   Lien vers la rubrique 12 :  
   `lien vers [la rubrique->rub12]     lien vers [la rubrique->rubrique 12] `

<!-- -->

-   Lien vers la brève 65 :  
   `lien vers [la brève->br65]     lien vers [la brève->breve 65]     lien vers [la brève->brève 65] `

<!-- -->

-   Auteurs, mots-clés, sites, images, documents :  
   `lien vers [un auteur->aut13] ou [le même auteur->auteur13]     lien vers [un mot->mot32]     lien vers [un site syndiqué->site1]     lien vers [un document joint->doc17] ou [le même document->document17]     lien vers [une image->img13] ou [la même image->image13] `

Application spécifique : on peut, là aussi, ne rien spécifier avant la
« flèche » (`[->aut13]`...). SPIP insérera automatiquement les
informations nécessaires. Dans le cas d’un document joint ou d’une
image, si l’on a indiqué un titre manuellement, c’est ce titre qui sera
affiché ; sinon c’est le nom du fichier lui-même qui sera utilisé.

Les raccourcis pour mentionner la langue et créer une info-bulle,
expliqués pour les liens externes, fonctionnent également pour les liens
internes.

<div align="right">

en savoir plus : [liens vers un
glossaire](http://www.spip.net/aide/?aide=raccourcis#glossaire),  
[ancres
nommées](http://www.spip.net/aide/?aide=raccourcis#ancres){.spip_ancre}.

</div>

-  **Notes de bas de page**

Une note de bas de page est, habituellement, signalée par un numéro
placé à l’intérieur du texte, numéro repris en bas de page et proposant
un complément d’information.

Dans SPIP, cette fonctionnalité (assez lourde à gérer manuellement en
HTML) est automatisée : les notes sont numérotées par SPIP, qui gère
également des liens hypertextes à l’intérieur du document pour passer
directement de l’appel de note au texte de la note correspondante, et
vice-versa.

Une note de bas de page est indiquée, dans SPIP, entre doubles
crochets :
« `Une note[[Voici un complément d'information.]] de bas de page.` »
sera affiché sous la forme : « Une note<span
class="spip_note_ref"> \[[1](http://www.spip.net/aide/?aide=raccourcis#nb1 "Voici un complément dinformation."){#nh1
.spip_note}\]</span> de bas de page. »

<div align="right">

[en savoir plus : des notes non
automatiques](http://www.spip.net/aide/?aide=raccourcis#notes)

</div>

-  **Citer un extrait (de forum)**

Il est souvent pratique, dans un forum de discussion, de citer un
extrait du message auquel on est en train de répondre. Pour homogénéiser
la présentation de telles citations, SPIP propose le raccourci
`<quote>...</quote>`.

Par exemple :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="4">
&lt;quote&gt;C'est drôlement bien, SPIP.&lt;/quote&gt; Kikou, je suis
bien d'accord :-)

</textarea>
</p>
donne :

> > C’est drôlement bien, SPIP.
>
> Kikou, je suis bien d’accord :-)

### Fonctionnalités plus complètes {#fonctionnalités-plus-complètes .spip}

Les raccourcis qui suivent offrent des fonctionnalités plus puissantes
et d’un usage plus spécifique. Si cela est votre premier contact avec
les raccourcis de SPIP, il est sans doute inutile que vous tentiez de
les apprendre par cœur dès maintenant. Il vous suffit de savoir qu’ils
existent ; lorsque vous en aurez réellement besoin, revenez sur cette
page, il sera alors beaucoup plus facile pour vous de mémoriser des
raccourcis dont vous avez réellement l’utilité.

-  **Tableaux**

Pour réaliser des tableaux très simples dans SPIP, il suffit de faire
des lignes dont les « cases » sont séparées par le symbole « | »
(*pipe*, un trait vertical), lignes commençant et se terminant par des
traits verticaux. Il est impératif de laisser des lignes vides avant et
après ce tableau.

Par exemple, le tableau :

  Nom         Prénom     Age
  ----------- ---------- -----------
  Marso       Ben        23 ans
  Capitaine              non connu
  Philant     Philippe   46 ans
  Cadoc       Bébé       4 mois

se code ainsi :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="5">
| {{Nom}} | {{Prénom}} | {{Age}} | | Marso | Ben | 23 ans | | Capitaine
| | non connu | | Philant | Philippe | 46 ans | | Cadoc | Bébé | 4 mois
|

</textarea>
</p>
Remarquez que toutes les entrées de la première ligne sont placées en
gras. SPIP identifie ainsi qu’il s’agit d’une page d’entête, et lui
attribue une présentation différente des autres lignes (fond de couleur
différente). La présence d’une telle ligne n’est pas obligatoire.

On peut aussi ajouter une légende et un résumé à la table. Ces deux
informations sont optionnelles mais sont très importantes pour rendre la
table accessible aux mal-voyants, le résumé donnant une meilleure idée
du contenu de la table.  
Ces informations sont spécifiées entre double trait vertical avant la
table comme ceci :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="6">
||Légende|Résumé|| | {{Nom}} | {{date de naissance}} | {{Ville}} | |
Jacques | 5/10/1970 | Paris | | Claire | 12/2/1975 | Belfort | | Martin
| 1/31/1957 | Nice | | Marie | 23/12/1948 | Perpignan |

</textarea>
</p>
et apparaitront comme cela :

  Nom       date de naissance   Ville
  --------- ------------------- -----------
  Jacques   5/10/1970           Paris
  Claire    12/2/1975           Belfort
  Martin    1/31/1957           Nice
  Marie     23/12/1948          Perpignan

  : Légende

On peut ne pas spécifier l’une ou l’autre des informations, mais il faut
bien penser à mettre un trait vertical simple devant le résumé si vous
ne spécifiez que celui-ci : `|| | résumé ||`{.spip_code dir="ltr"}

Il est également possible de fusionner une case avec d’autres, en
réduisant son contenu à `|<|`{.spip_code dir="ltr"} pour la fusionner
avec la case qui la précède horizontalement ; ou à `|^|`{.spip_code
dir="ltr"} pour la fusionner avec la case qui la précède verticalement.

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="5">
||Tableau avec fusion| Raccourci de fusion|| | {{Colonne 1}} | {{Colonne
2}} | {{Colonne 3}} | | Ligne 1 | L1C2 et L1C3 |&lt;| | Ligne 2 | L2C2
et L3C2|L2C3| | Ligne 3 |\^| L3C3 |

</textarea>
</p>
donnera

<table class="spip" summary="Raccourci de fusion">
<caption>
Tableau avec fusion

</caption>
<thead>
<tr class="row_first">
<th id="idc6b9_c0">
Colonne 1

</th>
<th id="idc6b9_c1">
Colonne 2

</th>
<th id="idc6b9_c2">
Colonne 3

</th>
</tr>
</thead>
<tbody>
<tr class="row_odd odd">
<td headers="idc6b9_c0">
Ligne 1

</td>
<td colspan="2" headers="idc6b9_c1">
L1C2 et L1C3

</td>
</tr>
<tr class="row_even even">
<td headers="idc6b9_c0">
Ligne 2

</td>
<td headers="idc6b9_c1" rowspan="2">
L2C2 et L3C2

</td>
<td headers="idc6b9_c2">
L2C3

</td>
</tr>
<tr class="row_odd odd">
<td headers="idc6b9_c0">
Ligne 3

</td>
<td headers="idc6b9_c2">
L3C3

</td>
</tr>
</tbody>
</table>
[]()

### Fabriquer des listes ou des énumérations {#fabriquer-des-listes-ou-des-énumérations .spip}

-  Un simple retour à la ligne s’obtient en tapant `_` (le trait de
soulignement ou *underscore*) au début de la ligne, suivi d’une espace.

*N.B.* En typographie classique, le simple retour à la ligne est très
rare (limité essentiellement à la poésie). On le confond souvent avec le
changement de paragraphe tel qu’il est affiché sur les documents
imprimés (sans espacement vertical entre les paragraphes), alors que,
par défaut, les butineurs Web insèrent un espacement entre les
paragraphes. Beaucoup d’utilisateurs cherchent à reproduire cette
caractéristique de l’imprimé (pas d’espacement vertical) en insérant de
simples retours à la ligne entre ce qu’ils considèrent être des
paragraphes ; cela est un erreur qui risque de nuire à la facilité de
maintenance et d’évolution de leur site. La solution consiste à définir,
dans les squelettes, une feuille de style (CSS) décrivant le
comportement des paragraphes (c’est-à-dire, selon les choix, pas
d’espacement vertical entre les paragraphes, indentation de la première
ligne...).

-  On peut faire des **énumérations imbriquées** en ajoutant des étoiles
après le tiret d’énumération.

Ainsi :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="8">
-\* Ton cheval est: -\*\* alezan; -\*\* bai; -\*\* noir; -\* mais mon
lapin est: -\*\* blanc; -\*\*\* angora; -\*\*\* ou à poil ras.

</textarea>
</p>
donne :

> -   Ton cheval est :
>     -   alezan ;
>     -   bai ;
>     -   noir ;
> -   mais mon lapin est :
>     -   blanc ;
>         -   angora ;
>         -   ou à poil ras.

-  Enfin, on peut faire des **listes numérotées** en utilisant le
`#`{.spip_code dir="ltr"} à la place de l’étoile :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="3">
-\# premier -\# deuxieme -\# troisieme

</textarea>
</p>
donnera :

> 1.  premier
> 2.  deuxième
> 3.  troisième

[  
-  **Les liens hypertextes vers un glossaire externe**]()

[]()

[Vous pouvez en outre créer très rapidement un lien hypertexte vers la
définition d’un terme dans un glossaire externe ; pour un terme donné,
il suffit d’insérer au sein de votre texte le raccourci
`[?terme]`{.spip_code dir="ltr"}.]()

[]()

[Ainsi le code suivant :
« `{À la recherche du temps perdu} est l'uvre majeure de [?Marcel Proust]`{.spip_code
dir="ltr"} » donnera à l’affichage : « *À la recherche du temps perdu*
est l’œuvre majeure de]()[Marcel
Proust](http://fr.wikipedia.org/wiki/Marcel_Proust){.spip_glossaire} ».
Pensez à cliquer sur le lien pour vérifier que le terme entré (nom
propre ou nom commun) est correctement orthographié, et qu’il pointe sur
une destination valide.

Le glossaire externe prédéfini est
[Wikipedia](http://www.wikipedia.org){.spip_out} qui impose certaines
[conventions sur les
titres](http://fr.wikipedia.org/wiki/Wikip%C3%A9dia:Conventions_sur_les_titres){.spip_out}.
Cette encyclopédie multilingue écrite sur un mode coopératif est ouverte
à tous les contributeurs via Internet ; prenez le temps de la connaître
et d’y contribuer afin d’enrichir ce fonds de savoir partagé.

Vous pouvez aussi référencer un autre glossaire en plaçant après le
terme le signe \# suivi du nom *G* du glossaire. SPIP appliquera alors
la fonction `glossaire_`*G* sur le terme pour obtenir le lien à insérer.
Cette fonction aura été placée dans le fichier `mes_options.php`. Si le
nom *G* se termine par des chiffres, ceux-ci seront préalablement
retirés de ce nom, et formeront le deuxième argument de la fonction, ce
qui est très utile pour un glossaire divisé en sections. On écrira
donc :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="2">
\[?read\#man2\]

</textarea>
</p>
pour indiquer que l’on référence l’explication du terme `read` dans la
section 2 du glossaire nommé `man`.

Les raccourcis pour mentionner la langue et créer une info-bulle,
expliqués pour les liens externes, fonctionnent également pour les
glossaires.

[]()  
-  **Des ancres nommées**

Vous pouvez définir des « ancres HTML » afin de pouvoir construire un
lien direct vers un point donné au milieu d’une page d’un site SPIP. Il
suffit d’introduire le raccourci :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="2">
\[direct&lt;-\]

</textarea>
</p>
et cela créera une ancre de nom `direct`{.spip_code dir="ltr"}. Ainsi,
s’il s’agit, par exemple, de l’article 3723, l’URL
`http://monsite/article.php3?id_article=3723#direct`{.spip_code
dir="ltr"} conduira directement à l’endroit de l’article où est situé
cette ancre.

Il est à noter que les ancres sont compatibles avec les [liens
hypertexte à l’intérieur du
site](http://www.spip.net/aide/?aide=raccourcis#liensite){.spip_ancre}.
Ainsi, le raccourci « `[ce point précis->art123#precis]`{.spip_code
dir="ltr"} » conduira vers l’ancre nommée « `precis`{.spip_code
dir="ltr"} » défini dans l’article 123.

[]()  
-  **Des notes non automatiques**

Dans la plupart des cas, le système de notes automatiques indiqué
ci-dessus suffit amplement. Cependant, vous pouvez gérer les notes d’une
manière non automatique en « forçant » le choix du numéro ou de la
mention affichée pour réaliser le lien.

Le principe général consiste à indiquer votre choix de la mention
utilisée entre chevrons au début de la note :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="2">
Une note «forcée»\[\[&lt;xxx&gt; Le texte de la note.\]\]

</textarea>
</p>
Sur ce principe :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="18">
vous pouvez utiliser les notes numérotées automatiques\[\[En plaçant le
texte de la note entre crochets.\]\], - mais aussi forcer la
numérotation de la note\[\[&lt;23&gt; En indiquant le numéro de la note
entre les symboles «&lt;» et «&gt;».\]\], - utiliser des notes sous
forme d'astérisques \[\[&lt;\*&gt; En plaçant simplement une astérisque
entre les symboles «&lt;» et «&gt;».\]\], - fabriquer des notes sans
références (non numérotées); attention, de telles notes ne présentent
plus de lien entre la note et l'appel de note\[\[&lt;&gt; En n'indiquant
rien entre les symboles «&lt;» et «&gt;».\]\], - donner un nom (en
toutes lettres) à une note; cet usage est très répandu pour les
références bibliographiques\[\[&lt;Rab&gt; François Rabelais.\]\]; -
rappeler une note déjà existante\[\[&lt;23&gt;\]\] en indiquant le
numéro de cette note entre les symboles «&lt;» et «&gt;» et en laissant
vide le reste de la note.

</textarea>
</p>
donne :

> vous pouvez utiliser les notes numérotées automatiques<span
> class="spip_note_ref"> \[[2](http://www.spip.net/aide/?aide=raccourcis#nb2 "En plaçant le texte de la note entre crochets."){#nh2
> .spip_note}\]</span>,  
> -  mais aussi forcer la numérotation de la note<span
> class="spip_note_ref"> \[[23](http://www.spip.net/aide/?aide=raccourcis#nb23 "En indiquant le numéro de la note entre les symboles «  »."){#nh23
> .spip_note}\]</span>,  
> -  utiliser des notes sous forme d’astérisques<span
> class="spip_note_ref"> \[[\*](http://www.spip.net/aide/?aide=raccourcis#nb_2A "En plaçant simplement une astérisque entre les symboles «  »."){#nh_2A
> .spip_note}\]</span>,  
> -  fabriquer des notes sans références (non numérotées) ; attention,
> de telles notes ne présentent plus de lien entre la note et l’appel de
> note,  
> -  donner un nom (en toutes lettres) à une note ; cet usage est très
> répandu pour les références bibliographiques<span
> class="spip_note_ref"> \[[Rab](http://www.spip.net/aide/?aide=raccourcis#nbRab "François Rabelais."){#nhRab
> .spip_note}\]</span> ;  
> -  rappeler une note déjà existante<span
> class="spip_note_ref"> \[[23](http://www.spip.net/aide/?aide=raccourcis#nb23){.spip_note}\]</span>
> en indiquant le numéro de cette note entre les symboles « &lt; » et
> « &gt; ». et en laissant vide le reste de la note.

-  **Court-circuiter les raccourcis SPIP**

Dans certains cas, il peut être utile d’indiquer à SPIP que certaines
parties d’un document ne doivent pas être « traitées » par le filtre des
raccourcis typographiques : vous ne voulez pas corriger la typographie,
vous devez afficher du code source (par exemple en PHP,
JavaScript...)...

Le code de ce raccourci est :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="2">
&lt;HTML&gt;texte à ne pas transformer; attention!&lt;/HTML&gt;

</textarea>
</p>
ce qui donne :

> texte à ne pas transformer; attention!

(ici, notez l’absence d’espaces avant le point-virgule et le point
d’exclamation).

-  **Afficher du code informatique**

Certains utilisateurs de SPIP veulent parfois afficher du code
informatique dans leurs pages. Le raccourci `<code>...</code>` est là
pour ça.

Exemple :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="3">
&lt;code&gt;&lt;?php // ceci est du langage php echo "bonjour";
?&gt;&lt;/code&gt;

</textarea>
</p>
donne

> <div class="spip_code" dir="ltr" style="text-align: left;">
>
> `<?php     // ceci est du langage php       echo "bonjour";  ?>`
>
> </div>

Il existe un autre raccourci pour publier des extraits de code
informatique de plusieurs lignes : `<cadre>...</cadre>`. Cela place le
code dans un « formulaire » (ceci est souvent utilisé sur la présente
page). L’avantage de cette méthode est de faciliter grandement le
copier-coller à partir de votre page Web : il suffit de placer le
curseur à l’intérieur du code, de faire « tout sélectionner » (ctrl-A)
pour pouvoir copier directement le code. De plus sur de nombreux
butineurs, ce cadre permet de bien restituer les tabulations en début de
ligne.

Voici un exemple :

<p>
<textarea class="spip_cadre" cols="40" dir="ltr" readonly="readonly" rows="19">
class Texte { var layout = 'texte'; var texte; } class Champ { var layout =
'champ'; var nom\_champ, id\_champ; var cond\_avant, cond\_apres; //
tableaux d'objets var fonctions; }

</textarea>
</p>
[Voir en ligne.](http://www.spip.net/aide/?aide=raccourcis#contenu-aide)
