---
title: Créer un blog avec Dotclear #17 Les syntaxes de saisie
date: 2016-06-25 01:26
layout: post
---

<div class="level1">

Vous pouvez rédiger vos billets à l'aide de la syntaxe wiki ou xhtml.
Dans les [Préférences
utilisateur](https://fr.dotclear.org/documentation/2.0/usage/user-preferences "2.0:usage:user-preferences"){.wikilink1}
vous déterminerez la syntaxe utilisée par défaut. Celle-ci peut être
différente pour un billet particulier en [choisissant la
syntaxe](https://fr.dotclear.org/documentation/2.0/usage/entries#choisir-le-layout-de-saisie "2.0:usage:entries"){.wikilink1}
depuis le petit menu déroulant figurant dans le menu d'édition du
billet.

Une présentation synthétique de la description ci-dessous est disponible
dans l'aide de l'éditeur de billets.

</div>

<!--more-->

Syntaxe wiki et correspondances xhtml {#syntaxe-wiki-et-correspondances-xhtml .sectionedit2}
-------------------------------------

<div class="level2">

**Présentation :** A l'aide de balises simples, la syntaxe wiki permet
d'enrichir la présentation sans connaissances particulières. Ces balises
sont ensuite interprétées par le moteur du blog et converties en xhtml.
Si vous ne maîtrisez pas parfaitement le xhtml et n'utilisez pas le mode
[wysiwyg](https://fr.dotclear.org/documentation/glossary#wysiwyg "glossary"){.wikilink1}
il est fortement recommandé d'utiliser le wiki pour éviter ainsi tout
risque d'erreur qui risquerait de générer des dysfonctionnement de
l'affichage du blog.

</div>

### Éléments de bloc {#elements-de-bloc .sectionedit3}

<div class="level3">

 

</div>

#### Blocs

<div class="level4">

**wiki :** Laissez une ligne vide entre chaque bloc de même nature.

</div>

#### Paragraphes

<div class="level4">

**wiki :** texte libre, terminé par une ligne vide si suivi d'un second
paragraphe.

**Correspondance xhtml :**
`<p>Le premier paragraphe.</p><p>Le deuxième paragraphe.</p>`

</div>

#### Titres

<div class="level4">

**wiki :** !!! titre, !! titre ou ! titre pour des titres plus ou moins
importants

**Correspondance xhtml :**

-   <div class="li">

    !!!!!Titre ? `<h1>Titre</h1>`

    </div>

-   <div class="li">

    !!!!Titre ? `<h2>Titre</h2>`

    </div>

-   <div class="li">

    !!!Titre ? `<h3>Titre</h3>`

    </div>

-   <div class="li">

    !!Titre ? `<h4>Titre</h4>`

    </div>

-   <div class="li">

    !Titre ? `<h5>Titre</h5>`

    </div>

<div class="wikinote noteclassic">

**Note :**

le niveau &lt;h1&gt; étant déjà utilisé pour le titre du blog et le
niveau &lt;h2&gt; pour le titre des billets, il est recommandé de
n'utiliser que les niveaux h3 et inférieurs au sein des billets.

</div>

</div>

#### Trait horizontal

<div class="level4">

**wiki :** —- (quatre traits d'union isolés sur une ligne)

**Correspondance xhtml :** `<hr />`

</div>

#### Listes

<div class="level4">

**wiki :** lignes débutant par \* pour des listes à puce ou \# pour des
listes numérotées

Vous pouvez faire des listes imbriquées en mélangeant les codes de
liste. Par exemple :

``` {.code}
   * item 1   ** item 1.1   ** item 1.2   * item 2   * item 3   *# item 3.1   ...
```

**Correspondance xhtml** de l'exemple ci-dessus :

``` {.code}
 <ul>   <li>item 1   <ul>     <li>item 1.1</li>     <li>item 1.1</li>   </ul></li>   <li>item 2</li>   <li>item 3   <ol>     <li>item 3.1</li>   </ol></li> </ul>
```

</div>

#### Texte préformaté {#texte-preformate}

<div class="level4">

**wiki :** espace avant chaque ligne de texte.

**Correspondance xhtml :** `<pre>lignes de texte préformaté</pre>`

</div>

#### Bloc de citation :

<div class="level4">

**wiki :** `>` devant chaque ligne de texte.

**Correspondance xhtml :**
`<blockquote><p>Les paragraphes de la citation.</p></blockquote>`

</div>

### Éléments de formatage {#elements-de-formatage .sectionedit4}

<div class="level3">

 

</div>

#### Emphase

<div class="level4">

**wiki :** deux apostrophes

``` {.code}
 ''texte''
```

**Correspondance xhtml :** `<em>texte</em>`

</div>

#### Forte emphase :

<div class="level4">

**wiki :** deux soulignés

``` {.code}
 __texte__
```

**Correspondance xhtml :** `<strong>texte</strong>`

</div>

#### Retour forcé à la ligne {#retour-force-a-la-ligne}

<div class="level4">

**wiki :**

``` {.code}
 texte.%%%
```

**Correspondance xhtml :** `<br />`

</div>

#### Insertion

<div class="level4">

**wiki :** deux plus

``` {.code}
 ++texte++
```

**Correspondance xhtml :** `<ins>texte</ins>`

</div>

#### Suppression

<div class="level4">

**wiki :** deux traits d'union

``` {.code}
 --texte--
```

**Correspondance xhtml :** `<del>texte</del>`

</div>

#### Liens

<div class="level4">

**wiki :**

-   <div class="li">

    \[url\]

    </div>

-   <div class="li">

    \[nom|url\]

    </div>

-   <div class="li">

    \[nom|url|langue\]

    </div>

-   <div class="li">

    \[nom|url|langue|titre\]

    </div>

**Correspondance xhtml :**

-   <div class="li">

    `<a href="url-cible">url-cible</a>`

    </div>

-   <div class="li">

    `<a href="url-cible">nom</a>`

    </div>

-   <div class="li">

    `<a href="url-cible" hreflang="fr">nom</a>`

    </div>

-   <div class="li">

    `<a href="url-cible" hreflang="fr" title="titre">nom</a>`

    </div>

</div>

#### Images

<div class="level4">

**wiki** :

-   <div class="li">

    ``` {.code}
     ((url|texte alternatif))
    ```

    </div>

-   <div class="li">

    ``` {.code}
     ((url|texte alternatif|position))
    ```

    </div>

-   <div class="li">

    ``` {.code}
     ((url|texte alternatif|position|description longue))
    ```

    </div>

La position peut prendre les valeurs L ou G (gauche), R ou D (droite) ou
C (centré).

**Correspondance xhtml :**

-   <div class="li">

    `<img src="url" alt="texte alternatif" />`

    </div>

-   <div class="li">

    `<img src="url" alt="texte alternatif" style="display:block; float:left; margin:0 1em 1em 0" />`
    (si position : L ou G)

    </div>

-   <div class="li">

    `<img src="url" alt="texte alternatif" style="display:block; float:right; margin:0 0 1em 1em" longdesc="description longue" />`
    (si position : R ou D)

    </div>

</div>

#### Ancre

<div class="level4">

**wiki :** \~ancre\~

**Correspondance xhtml :** `<a name="ancre"></a>`

</div>

#### Acronyme

<div class="level4">

**wiki :** ??acronyme|titre??

**Correspondance xhtml :** `<acronym title="titre">acronyme</acronym>`

</div>

#### Citation en ligne

<div class="level4">

**wiki :**

-   <div class="li">

    ``` {.code}
     {{citation}}
    ```

    </div>

-   <div class="li">

    ``` {.code}
     {{citation|langue}}
    ```

    </div>

-   <div class="li">

    ``` {.code}
     {{citation|langue|url}}
    ```

    </div>

**Correspondance xhtml :**

-   <div class="li">

    `<q>citation</q>`

    </div>

-   <div class="li">

    `<q lang="fr">citation</q>`

    </div>

-   <div class="li">

    `<q lang="fr" cite="url">citation</q>`

    </div>

</div>

#### Code

<div class="level4">

**wiki :** @@code ici@@

**correspondance xhtml :** `<code>code ici</code>`

</div>

#### Note de bas de page

<div class="level4">

**wiki :** texte\$\$Corps de la note\$\$

**Correspondance xhtml :**

``` {.code}
 texte<sup>[<a href="url-blog#pnote-xxx-x" id="rev-pnote-xxx-x">x</a>]</sup> (...) <div class="footnotes"><h4>Notes</h4> <p>[<a href="url-blog/#rev-pnote-xxx-x" id="pnote-xxx-x">x</a>] Corps de la note</p></div>
```

</div>

### Compléments {#complements .sectionedit5}

<div class="level3">

 

</div>

#### Empêcher le formatage du texte {#empecher-le-formatage-du-texte}

<div class="level4">

Pour insérer un caractère sans que celui-ci soit reconnu comme un
caractère de formatage, ajoutez le caractère avant celui-ci. Par exemple
:

``` {.code}
   [texte entre crochet qui n'est pas un lien]
```

</div>

#### Insérer du code HTML au sein de la syntaxe wiki {#inserer-du-code-html-au-sein-de-la-syntaxe-wiki}

<div class="level4">

Vous pouvez ponctuellement avoir besoin d'insérer du code
<abbr title="HyperText Markup Language">HTML</abbr> dans votre texte au
format Wiki. Pour cela, utilisez le code suivant en laissant une ligne
vide avant et après cette insertion :

``` {.code}
   ///html   <p style="color:red;">mon texte en rouge</p>   ///
```

Pour insérer du code <abbr title="HyperText Markup Language">HTML</abbr>
dans le courant d'un paragraphe en Wiki (inline), il faut utiliser la
syntaxe suivante :

``` {.code}
   Début du paragraphe, ``<span style="color:blue;">Plop</span>``, fin du paragraphe
```

</div>

Aller plus loin {#aller-plus-loin .sectionedit6}
---------------

<div class="level2">

-   <div class="li">

    [Toutes les balises
    xhtml](http://giminik.developpez.com/xhtml/ "http://giminik.developpez.com/xhtml/"){.urlextern}

    </div>

-   <div class="li">

    [Contrôle de validité
    xhtml](http://validator.w3.org/ "http://validator.w3.org/"){.urlextern}
    (en anglais)

    </div>

<p>
[Voir en
ligne.](https://fr.dotclear.org/documentation/2.0/usage/syntaxes)

</div>
