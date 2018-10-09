---
title: Debian et ses Textes fondateurs
date: 2016-04-05 19:47
layout: post
---

<div>

    Quelques années après son lancement, Debian a formalisé les
principes qu'elle devait suivre en tant que projet de logiciel libre.
Cette démarche militante permet une croissance sereine en s'assurant que
tous les membres progressent dans la même direction. Pour devenir
développeur Debian, tout candidat doit d'ailleurs convaincre de son
adhésion aux principes établis dans les textes fondateurs du projet.

</div>

<div>

Le processus de développement est constamment débattu, mais ces textes
fondateurs sont très consensuels et n'évoluent que rarement. La
constitution les protège des changements erratiques : une majorité
qualifiée de trois quarts est nécessaire pour approuver tout amendement.

</div>

<!--more-->

<div>

<div>

### [](){#sect.social-contract}1.2.1. L'engagement vis-à-vis des utilisateurs

</div>

[](){#idm140632702937376}[](){#idm140632702936416}

<div>

On trouve aussi un « contrat social ». Quelle est la place d'un tel
texte dans un projet ne visant qu'à concevoir un système
d'exploitation ? C'est très simple, Debian œuvre pour ses utilisateurs
et, par extension, pour la société. Ce contrat résume donc les
engagements pris. Voyons ces points plus en détail :

</div>

<div>

1.  <div>

    Debian demeurera totalement libre.

    </div>

    <div>

    C'est la règle numéro un. Debian est et restera constituée
    exclusivement de logiciels libres. De plus, tous les logiciels
    développés en propre par Debian seront libres.

    </div>

    <div>

    <div>

    PERSPECTIVE Au delà du logiciel

    </div>

    <div>

    La première version du contrat social disait « Debian demeurera un
    ensemble logiciel totalement libre ». La disparition de ces trois
    mots (avec la ratification de la version 1.1 du contrat au mois
    d'avril 2004) traduit une volonté d'obtenir la liberté non seulement
    des logiciels mais aussi de la documentation et de tout ce que
    Debian souhaite fournir dans son système d'exploitation.

    </div>

    <div>

    Ce changement, qui ne se voulait qu'éditorial, a en réalité eu de
    nombreuses conséquences, avec notamment la suppression de certaines
    documentations problématiques. Par ailleurs, l'usage de plus en plus
    fréquent de microcodes (firmwares) dans les pilotes pose des
    problèmes : nombreux sont ceux qui ne sont pas libres, mais sont
    néanmoins nécessaires au bon fonctionnement du
    matériel correspondant.

    </div>

    </div>

2.  <div>

    Nous donnerons en retour à la communauté du logiciel libre.

    </div>

    <div>

    Toute amélioration apportée par le projet Debian à un logiciel
    intégré à la distribution est envoyée à l'auteur de ce dernier
    (dit « amont »). D'une manière générale, Debian coopère avec la
    communauté au lieu de travailler isolément.

    </div>

    <div>

    <div>

    COMMUNAUTÉ Auteur amont ou développeur Debian ?

    </div>

    [](){#idm140632691472528}[](){#idm140632691471568}[](){#idm140632691470608}

    <div>

    Traduction littérale de upstream author, le terme « auteur amont »
    désigne le ou les auteurs/développeurs d'un logiciel, qui l'écrivent
    et le font évoluer. A contrario, un « développeur Debian » se
    contente en général de partir d'un logiciel existant pour le
    transformer en paquet Debian (la désignation « mainteneur Debian »
    est plus explicite).

    </div>

    <div>

    Bien souvent, la ligne de démarcation n'est pas aussi nette. Le
    mainteneur Debian écrit parfois un correctif, qui profite à tous les
    utilisateurs du logiciel. De manière générale, Debian encourage
    l'implication des responsables de paquets dans le développement
    « amont » (ils deviennent alors contributeurs sans se cantonner au
    rôle de simples utilisateurs d'un logiciel).

    </div>

    </div>

3.  <div>

    Nous ne dissimulerons pas les problèmes.

    </div>

    <div>

    Debian n'est pas parfaite et l'on y découvre tous les jours des
    problèmes à corriger. Tous ces bogues sont répertoriés et
    consultables librement, par exemple sur le Web.

    </div>

4.  <div>

    Nos priorités sont nos utilisateurs et les logiciels libres.

    </div>

    <div>

    Cet engagement est plus difficile à définir. Debian s'impose ainsi
    un biais lorsqu'elle doit prendre une décision et écartera une
    solution de facilité pénalisante pour ses utilisateurs au profit
    d'une solution plus élégante, même si elle est plus difficile à
    mettre en œuvre. Il s'agit de prendre en compte en priorité les
    intérêts des utilisateurs et du logiciel libre.

    </div>

5.  <div>

    Programmes non conformes à nos standards sur les logiciels libres.

    </div>

    <div>

    Debian accepte et comprend que ses utilisateurs souhaitent parfois
    utiliser certains logiciels non libres. Elle s'engage donc à mettre
    à leur disposition une partie de son infrastructure, pour distribuer
    sous forme de paquets Debian les logiciels non libres
    qui l'autorisent.

    </div>

    <div>

    <div>

    COMMUNAUTÉ Pour ou contre la section non-free ?

    </div>

    [](){#idm140632691460592}[](){#idm140632691459472}

    <div>

    L'engagement de conserver une structure d'accueil pour des logiciels
    non libres (i.e. la section non-free, voir encadré [VOCABULAIRE Les
    archives main, contrib et
    non-free](https://www.debian.org/doc/manuals/debian-handbook/apt.fr.html#sidebar.sections))
    est régulièrement remis en cause au sein de la communauté Debian.

    </div>

    <div>

    Ses détracteurs arguent qu'il détourne certaines personnes de
    logiciels libres équivalents et contredit le principe de servir
    exclusivement la cause des logiciels libres. Les partisans
    rappellent plus prosaïquement que la majorité des logiciels de
    non-free sont des logiciels « presque libres », entravés seulement
    par une ou deux restrictions gênantes (la plus fréquente étant
    l'interdiction de tirer un bénéfice commercial du logiciel). En
    distribuant ces logiciels dans la branche non-free, on explique
    indirectement à leur auteur que leur création serait mieux reconnue
    et plus utilisée si elle pouvait être intégrée dans la section
    main : ils sont ainsi poliment invités à changer leur licence pour
    servir cet objectif.

    </div>

    <div>

    Après une première tentative infructueuse en 2004, la suppression
    totale de la section non-free ne devrait plus revenir à l'ordre du
    jour avant plusieurs années, d'autant plus qu'elle contient de
    nombreuses documentations utiles qui y ont été déplacées parce
    qu'elles ne répondaient plus aux nouvelles exigences de la
    section main. C'est notamment le cas pour certaines documentations
    de logiciels issus du projet GNU (en particulier Emacs et Make).

    </div>

    <div>

    Signalons que l'existence de non-free gêne considérablement la Free
    Software Foundation. C'est la raison principale justifiant l'absence
    de Debian dans sa liste des systèmes d'exploitation recommandés.

    </div>

    </div>

</div>

</div>

<div>

<div>

### [](){#sect.dfsg}1.2.2. Les principes du logiciel libre selon Debian

</div>

[](){#idm140632691448992}[](){#idm140632691448064}[](){#idm140632691447104}[](){#idm140632691446016}

<div>

Ce texte de référence définit quels logiciels sont « suffisamment
libres » pour être intégrés à Debian. Si la licence d'un logiciel est
conforme à ces principes, il peut être intégré à la section main ; dans
le cas contraire, et si sa libre redistribution est permise, il peut
rejoindre la section non-free. Celle-ci ne fait pas officiellement
partie de Debian : il s'agit d'un service annexe fourni aux
utilisateurs.

</div>

<div>

Plus qu'un critère de choix pour Debian, ce texte fait autorité en
matière de logiciel libre puisqu'il a servi de socle à la « définition
de l'open source ». C'est donc historiquement l'une des premières
formalisations de la notion de « logiciel libre ».

</div>

<div>

La licence publique générale de GNU (GNU General Public License), la
licence BSD et la licence artistique sont des exemples de licences
libres traditionnelles respectant les 9 points mentionnés dans ce texte.
Vous en trouverez ci-dessous la traduction, telle que publiée sur le
site web de Debian.
<div>

? <http://www.debian.org/social_contract.fr.html#guidelines>

</div>

</div>

<div>

1.  <div>

    <div>

    Redistribution libre et gratuite

    </div>

    La licence d'un composant de Debian ne doit pas empêcher quiconque
    de vendre ou donner le logiciel sous forme de composant d'un
    ensemble (distribution) constitué de programmes provenant de
    différentes sources. La licence ne doit en ce cas requérir ni
    redevance ni rétribution.

    </div>

    <div>

    <div>

    B.A.-BA Les licences libres

    </div>

    [](){#idm140632691436880}[](){#idm140632691435440}[](){#idm140632691434480}[](){#idm140632691433040}[](){#idm140632691432080}[](){#idm140632691430480}[](){#idm140632691429360}[](){#idm140632691427920}

    <div>

    La GNU GPL, la licence BSD et la licence artistique respectent
    toutes trois les principes du logiciel libre selon Debian. Elles
    sont pourtant très différentes.

    </div>

    <div>

    La GNU GPL, utilisée et promue par la FSF (Free Software Foundation,
    ou fondation du logiciel libre), est la plus courante. Elle a pour
    particularité de s'appliquer à toute œuvre dérivée et redistribuée :
    un programme intégrant ou utilisant du code GPL ne peut être diffusé
    que selon ses termes. Elle interdit donc toute récupération dans une
    application propriétaire. Ceci pose également de gros problèmes pour
    le réemploi de code GPL dans des logiciels libres incompatibles avec
    cette licence. Ainsi, il est parfois impossible de lier une
    bibliothèque diffusée sous GPL à un programme placé sous une autre
    licence libre. En revanche, cette licence est très solide en droit
    américain : les juristes de la FSF ont participé à sa rédaction et
    elle a souvent contraint des contrevenants à trouver un accord
    amiable avec la FSF sans aller jusqu'au procès.
    <div>

    ? <http://www.gnu.org/copyleft/gpl.html>

    </div>

    </div>

    <div>

    La licence BSD est la moins restrictive : tout est permis, y compris
    l'intégration de code BSD modifié dans une application propriétaire.
    Microsoft ne s'en est d'ailleurs pas privé car la couche TCP/IP de
    Windows NT est fondée sur celle du noyau BSD.
    <div>

    ? <http://www.opensource.org/licenses/bsd-license.php>

    </div>

    </div>

    <div>

    Enfin, la licence artistique réalise un compromis entre les deux
    précédentes : l'intégration du code dans une application
    propriétaire est possible, mais toute modification doit
    être publiée.
    <div>

    ? <http://www.opensource.org/licenses/artistic-license-2.0.php>

    </div>

    </div>

    <div>

    Le texte complet (en anglais) de ces licences est disponible dans
    /usr/share/common-licenses/ sur tout système Debian. Certaines de
    ces licences disposent de traductions en français, mais leur statut
    reste officieux et leur valeur légale est encore en cours de
    discussion ; le texte de référence reste alors la version anglaise.

    </div>

    </div>

2.  <div>

    <div>

    Code source

    </div>

    Le programme doit inclure le code source et sa diffusion, sous forme
    de code source comme de programme compilé, doit être autorisée.

    </div>

3.  <div>

    <div>

    Applications dérivées

    </div>

    La licence doit autoriser les modifications et les applications
    dérivées ainsi que leur distribution sous les mêmes termes que ceux
    de la licence du logiciel original.

    </div>

4.  <div>

    <div>

    Intégrité du code source de l'auteur

    </div>

    La licence peut défendre de distribuer le code source modifié
    seulement si elle autorise la distribution avec le code source de
    fichiers correctifs destinés à modifier le programme au moment de
    sa construction. La licence doit autoriser explicitement la
    distribution de logiciels créés à partir de code source modifié.
    Elle peut exiger que les applications dérivées portent un nom ou un
    numéro de version différent de ceux du logiciel original (c'est un
    compromis : le groupe Debian encourage tous les auteurs à ne
    restreindre en aucune manière les modifications des fichiers, source
    ou binaire).

    </div>

5.  <div>

    <div>

    Aucune discrimination de personne ou de groupe

    </div>

    La licence ne doit discriminer aucune personne ou groupe
    de personnes.

    </div>

6.  <div>

    <div>

    Aucune discrimination de champ d'application

    </div>

    La licence ne doit pas défendre d'utiliser le logiciel dans un champ
    d'application particulier. Par exemple, elle ne doit pas défendre
    l'utilisation du logiciel dans une entreprise ou pour la
    recherche génétique.

    </div>

7.  <div>

    <div>

    Distribution de licence

    </div>

    Les droits attachés au programme doivent s'appliquer à tous ceux à
    qui il est distribué sans obligation pour aucune de ces parties de
    se conformer à une autre licence.

    </div>

8.  <div>

    <div>

    La licence ne doit pas être spécifique à Debian

    </div>

    Les droits attachés au programme ne doivent pas dépendre du fait de
    son intégration au système Debian. Si le programme est extrait de
    Debian et utilisé et distribué sans Debian mais sous les termes de
    sa propre licence, tous les destinataires doivent jouir des même
    droits que ceux accordés lorsqu'il se trouve au sein du
    système Debian.

    </div>

9.  <div>

    <div>

    La licence ne doit pas contaminer d'autres logiciels

    </div>

    La licence ne doit pas placer de restriction sur d'autres logiciels
    distribués avec le logiciel. Elle ne doit par exemple pas exiger que
    tous les autres programmes distribués sur le même support soient des
    logiciels libres.

    </div>

    <div>

    <div>

    <div>

    <div>

    B.A.-BA Le copyleft

    </div>

    </div>

    </div>

    [](){#idm140632697484432}[](){#idm140632697483472}

    <div>

    Le copyleft (ou « gauche d'auteur ») est un principe qui consiste à
    faire appel au mécanisme des droits d'auteurs pour garantir la
    liberté d'une œuvre et de ses dérivées — au lieu de restreindre les
    droits des utilisateurs comme dans le cas des
    logiciels propriétaires. Il s'agit d'ailleurs d'un jeu de mots sur
    le terme copyright, équivalent américain du droit d'auteur. Richard
    Stallman a trouvé cette idée quand un ami friand de calembours
    écrivit sur une enveloppe qu'il lui adressa : « copyleft: all rights
    reversed » (copyleft : tous droits renversés). Le copyleft impose la
    conservation de toutes les libertés initiales lors de la
    distribution d'une version modifiée (ou non) du logiciel. Il est
    donc impossible de dériver un logiciel propriétaire d'un logiciel
    placé sous copyleft.

    </div>

    <div>

    La famille de licences copyleft la plus célèbre est sans aucun doute
    la GNU GPL et ses dérivées, la GNU LGPL — GNU Lesser General Public
    License et la GNU FDL — GNU Free Documentation License.
    Malheureusement, les licences copyleft sont généralement
    incompatibles entre elles ! En conséquence, il est préférable de
    n'en utiliser qu'une seule.

    </div>

    </div>

</div>

<div>

[](){#sidebar.bruce-perens}
<div>

COMMUNAUTÉ Bruce Perens, un leader chahuté

</div>

[](){#idm140632697473904}[](){#idm140632697472944}[](){#idm140632697471984}

<div>

Bruce Perens a été le deuxième leader du projet Debian, juste après Ian
Murdock. Il fut très controversé pour ses méthodes dynamiques et assez
dirigistes. Il n'en reste pas moins un contributeur important, à qui
Debian doit notamment la rédaction des fameux « principes du logiciel
libre selon Debian » (ou DFSG pour Debian Free Software Guidelines),
idée originelle d'Ean Schuessler. Par la suite, Bruce en dérivera la
célèbre « définition de l'open source » en y gommant toutes les
références à Debian.
<div>

? <http://www.opensource.org/>

</div>

</div>

<div>

Son départ du projet fut quelque peu mouvementé mais Bruce est resté
assez fortement attaché à Debian puisqu'il continue de promouvoir cette
distribution dans les sphères politiques et économiques. Il intervient
encore épisodiquement sur les listes de diffusion pour donner son avis
et présenter ses dernières initiatives en faveur de Debian.

</div>

[](){#idm140632697468112}[](){#idm140632697466992}[](){#idm140632697465552}[](){#idm140632697464240}[](){#idm140632697462928}[](){#idm140632697461616}[](){#idm140632697460304}[](){#idm140632697458992}[](){#idm140632697457680}[](){#idm140632697456368}[](){#idm140632697455056}[](){#idm140632697453744}[](){#idm140632697452432}[](){#idm140632697451120}[](){#idm140632697449808}[](){#idm140632697448496}[](){#idm140632697447184}[](){#idm140632697445872}[](){#idm140632697444560}[](){#idm140632697443600}

<div>

Dernier point anecdotique, c'est à lui que l'on doit l'inspiration des
« noms de code » des différentes versions de Debian (1.1 — Rex, 1.2 —
Buzz, 1.3 — Bo, 2.0 — Hamm, 2.1 — Slink, 2.2 — Potato, 3.0 — Woody, 3.1
— Sarge, 4.0 — Etch, 5.0 — Lenny, 6.0 — Squeeze, 7 — Wheezy, 8 — Jessie,
9 (pas encore publiée) — Stretch, 10 (pas encore publiée) — Buster,
Unstable — Sid. Ils correspondent tous à des personnages de Toy Story.
Ce film d'animation entièrement réalisé en images de synthèse fut
produit par Pixar, employeur de Bruce à l'époque où il était leader
Debian. Le nom « Sid » a un statut particulier puisqu'il restera
éternellement associé à Unstable ; dans le film, il s'agit de l'enfant
des voisins, incorrigible brise-tout — gare à vous donc si vous
approchez Unstable de trop près ! Par ailleurs, Sid est l'acronyme de
Still In Development (encore et toujours en cours de développement).

</div>

</div>

</div>

Voir en ligne : [1.2. Les textes
fondateurs](https://www.debian.org/doc/manuals/debian-handbook/sect.foundation-documents.fr.html)
