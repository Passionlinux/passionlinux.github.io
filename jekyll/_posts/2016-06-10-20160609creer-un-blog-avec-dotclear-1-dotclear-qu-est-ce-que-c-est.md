---
title: Créer un blog avec Dotclear 1; Dotclear, qu'est ce que c'est? par Wikipedia
date: 2016-06-10 15:11
layout: post
---

Je commence cette série sur Dotclear, entamé dans [le dernier
article](http://passiongnulinux.tuxfamily.org/?p=97){.ref-post}. On y
verra notamment son installation, sa configuration, comment faire son
premier article,...

Il y a aussi la suite de la série sur SPIP qui est en cours, malgré que
je ne l'utilise plus...

D’après Wikipédia, **Dotclear** est un [moteur de
blog](https://fr.wikipedia.org/wiki/Moteur_de_blog "Moteur de blog")
[libre](https://fr.wikipedia.org/wiki/Logiciel_libre "Logiciel libre")
distribué sous [licence
libre](https://fr.wikipedia.org/wiki/Licence_libre "Licence libre") [GNU
GPLv2](https://fr.wikipedia.org/wiki/Licence_publique_g%C3%A9n%C3%A9rale_GNU "Licence publique générale GNU").
Il est populaire en
[France](https://fr.wikipedia.org/wiki/France "France"), mais son
utilisation hors de ce pays est moins répandue. Dotclear est un logiciel
respectueux des [standards du
Web](https://fr.wikipedia.org/wiki/Standards_du_Web "Standards du Web")
écrit en langage [PHP](https://fr.wikipedia.org/wiki/PHP "PHP").  
<!--more-->

![](https://upload.wikimedia.org/wikipedia/fr/d/dc/Dotclear-logo.png) {#httpsupload.wikimedia.orgwikipediafrddcdotclear-logo.png style="text-align: center;"}
---------------------------------------------------------------------

<span id="Historique" class="mw-headline">Historique</span>
-----------------------------------------------------------

Développé à l'origine par Olivier Meunier seul en
[2002](https://fr.wikipedia.org/wiki/2002_en_informatique "2002 en informatique"),
Dotclear est désormais animé par une petite équipe de bénévoles. En
<time class="nowrap date-lien" datetime="2009-06">[juin](https://fr.wikipedia.org/wiki/Juin_2009 "Juin 2009")
[2009](https://fr.wikipedia.org/wiki/2009_en_informatique "2009 en informatique")</time>,
Olivier Meunier annonce son départ du projet laissant sa place à Xavier
Plantefève^[3](https://fr.wikipedia.org/wiki/Dotclear#cite_note-3)^. En
février 2013 Xavier Plantefève confie les
rênes^[4](https://fr.wikipedia.org/wiki/Dotclear#cite_note-4)^ à Franck
Paul pour conduire les développements futurs. Le développement de la
version 2.0, qui a duré 1 040
jours^[5](https://fr.wikipedia.org/wiki/Dotclear#cite_note-5)^, a été
l'occasion d'une réécriture complète du moteur. Un nombre important de
nouveautés a été
apporté^[6](https://fr.wikipedia.org/wiki/Dotclear#cite_note-6)^ dont la
gestion des
[métadonnées](https://fr.wikipedia.org/wiki/M%C3%A9tadonn%C3%A9e "Métadonnée"),
une utilisation plus simple, des bases de données
[SQLite](https://fr.wikipedia.org/wiki/SQLite "SQLite") et
[PostgreSQL](https://fr.wikipedia.org/wiki/PostgreSQL "PostgreSQL").
Elle ne fonctionne qu'avec la version 5.0 (ou supérieure) de PHP. Le 11
juillet 2009, Dotclear devient une association, elle devient l'éditeur
du logiciel du même
nom^[7](https://fr.wikipedia.org/wiki/Dotclear#cite_note-7)^. Le 3 juin
2010, Dotclear a annoncé la sortie en beta de la version 2.2 du moteur
de blog^[8](https://fr.wikipedia.org/wiki/Dotclear#cite_note-8)^. La
version 2.3 a vu le jour le 16 mai
2011^[9](https://fr.wikipedia.org/wiki/Dotclear#cite_note-9)^. Cette
mise à jour apporte une refonte visuelle de l'interface qui se voit
rafraîchie, et de nouvelles options font leur apparition dans les
préférences utilisateur. Un système de favoris permet d'ajouter un menu
personnalisé comportant les modules que l'on souhaite, bien que cette
fonctionnalité nécessite aux développeurs d’extensions de mettre à jour
celles-ci. Dotclear 2.3.1 a été rendu disponible le 14 juin
2011^[10](https://fr.wikipedia.org/wiki/Dotclear#cite_note-10)^ et
apporte quelques corrections de bogues, et comble une faille de
sécurité. Une version beta de Dotclear 2.4 a été proposée le 13
septembre
2011^[11](https://fr.wikipedia.org/wiki/Dotclear#cite_note-11)^, suivie
de la version finale deux mois plus
tard^[12](https://fr.wikipedia.org/wiki/Dotclear#cite_note-12)^. Voici
les principales nouveautés de cette version 2.4 :

-   Ajout du thème Ductile, pensé pour être facilement adaptable et
    compatible avec les différentes résolutions d'écran, y compris
    les smartphones.
-   Nouveau module pour la gestion de menus (SimpleMenu).
-   Troisième zone pour les widgets.
-   Lot de nouvelles icônes dessinées par Thomas Daveluy, permettant à
    Dotclear de retrouver son statut entièrement sous licence GPL.

Pour Noël, une mise à jour mineure est diffusée, numérotée
2.4.1.2^[13](https://fr.wikipedia.org/wiki/Dotclear#cite_note-13)^
(symbolisant le jour de sa diffusion, le 24 décembre). Elle corrige une
faille de sécurité. Dotclear 2.5 est sorti le 16 mars
2013^[14](https://fr.wikipedia.org/wiki/Dotclear#cite_note-14)^. Cette
version n'apporte pas de gros changement par rapport à la version 2.4.
On peut maintenant utiliser des webfonts dans Ductile et daInstaller est
inclus de base, on note également quelques changements au niveau de
l'intégration des thèmes et des plugins. Doctclear est maintenant
pleinement compatible PHP 5.4, le reste des modifications étant
essentiellement des corrections de bogues. Dotclear 2.6 est sorti le 13
novembre
2013^[15](https://fr.wikipedia.org/wiki/Dotclear#cite_note-15)^. Les
nouveautés incluent une nouvelle charte graphique, des améliorations en
matière d'ergonomie et d'accessibilité, plus d'autres améliorations du
code du serveur et des
plugins^[16](https://fr.wikipedia.org/wiki/Dotclear#cite_note-16)^.
Dotclear 2.7 est sorti le 13 décembre
2014^[17](https://fr.wikipedia.org/wiki/Dotclear#cite_note-17)^. Cette
version intègre un nouvel éditeur,
[dcCKEditor](https://fr.wikipedia.org/wiki/CKEditor "CKEditor") et un
début d'intégration du
[HTML5](https://fr.wikipedia.org/wiki/HTML5 "HTML5"). Dotclear 2.8 est
sorti le 13 août
2015^[18](https://fr.wikipedia.org/wiki/Dotclear#cite_note-18)^. Cette
version fait évoluer le lien entre les modules (plugins et thèmes), met
à jour l'éditeur CKEditor et la librairie
[jQuery](https://fr.wikipedia.org/wiki/JQuery "JQuery").  

<span id="Fonctionnalit.C3.A9s" class="mw-headline">Fonctionnalités</span>
--------------------------------------------------------------------------

<div class="thumb tright">

<div class="thumbinner" style="width: 222px;">

[![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2b/Dotclear-admin.png/220px-Dotclear-admin.png){.thumbimage
width="220" height="168"
srcset="//upload.wikimedia.org/wikipedia/commons/thumb/2/2b/Dotclear-admin.png/330px-Dotclear-admin.png 1.5x, //upload.wikimedia.org/wikipedia/commons/thumb/2/2b/Dotclear-admin.png/440px-Dotclear-admin.png 2x"}](https://commons.wikimedia.org/wiki/File:Dotclear-admin.png?uselang=fr){.image}

<div class="thumbcaption">

<div class="magnify">

</div>

</div>

</div>

</div>

<div class="thumb tright">

<div class="thumbinner" style="width: 222px;">

<div class="thumbcaption">

Interface d'administration de Dotclear 2.0

</div>

</div>

</div>

Il propose entre autres :

-   une installation automatisée ;
-   une interface multilingue ;
-   une gestion multi-utilisateurs ;
-   une gestion
    multi-blogue^[19](https://fr.wikipedia.org/wiki/Dotclear#cite_note-19)^
    (portail de blogues) ;
-   la possibilité d'éditer les thèmes dans l'interface
    d'administration ;
-   la gestion d'[UTF-8](https://fr.wikipedia.org/wiki/UTF-8 "UTF-8") ;
-   un système de
    [greffon](https://fr.wikipedia.org/wiki/Greffon_%28informatique%29 "Greffon (informatique)"){.mw-redirect}
    et thèmes graphiques (thèmes),
-   l'import et l'installation directes des greffons et habillages (pas
    besoin de passer par un [client
    FTP](https://fr.wikipedia.org/wiki/Client_FTP "Client FTP"){.mw-redirect}),
-   une galerie multi-média
    ([png](https://fr.wikipedia.org/wiki/Portable_Network_Graphics "Portable Network Graphics"),
    [odt](https://fr.wikipedia.org/wiki/Odt "Odt"){.mw-redirect}...),
-   un système de modules ("widgets") insérables dans la barre latérale
    de menu...

<span id="Utilisation" class="mw-headline">Utilisation</span>
-------------------------------------------------------------

-   [France
    Télévisions](https://fr.wikipedia.org/wiki/France_T%C3%A9l%C3%A9visions "France Télévisions")
    a adopté Dotclear pour son [service de
    blogs](http://blog.france2.fr){.external .text} en avril 2005.
-   Le
    [PCF](https://fr.wikipedia.org/wiki/Parti_communiste_fran%C3%A7ais "Parti communiste français")
    a adopté Dotclear pour ses [blog de la gauche populaire
    Antilibérale](http://blogs.gauchepopulaire.fr){.external .text} en
    janvier 2007.
-   [Tristan
    Nitot](https://fr.wikipedia.org/wiki/Tristan_Nitot "Tristan Nitot")
    utilise Dotclear sur son [Standblog](http://standblog.org){.external
    .text}.
-   Le
    [registrar](https://fr.wikipedia.org/wiki/Registrar "Registrar"){.mw-redirect}
    français
    [Gandi](https://fr.wikipedia.org/wiki/Gandi "Gandi"){.mw-redirect}
    utilise Dotclear 2 comme plateforme pour son [service
    GandiBlog](http://www.gandi.net/domaine/blog/){.external .text}
    ^[20](https://fr.wikipedia.org/wiki/Dotclear#cite_note-20)^.
-   Le fournisseur d'accès à Internet Free a lancé, en décembre
    2008^[21](https://fr.wikipedia.org/wiki/Dotclear#cite_note-21)^, une
    [plateforme de blogs](http://blog.free.fr/){.external .text} basée
    sur Dotclear 2.

[Voir en ligne.](https://fr.wikipedia.org/wiki/Dotclear)
