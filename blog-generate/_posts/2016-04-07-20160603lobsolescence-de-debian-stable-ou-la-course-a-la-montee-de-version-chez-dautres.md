---
title: L'obsolescence de debian stable ou la course à la montée de version chez d'autres
date: 2016-04-07 12:55
layout: post
---

<div class="main">

<div class="chapo surlignable">

Cette article fait suite à celui
[ci](http://frederic.bezies.free.fr/blog/?p=14289){.spip_out} Comme
toujours dans le monde du libre, deux écoles se font la « guerre », les
utilisateurs des distributions à sortie stable, c’est a dire
distribution à version (comme debian, mageia, mandriva, ubuntu, fedora,
opensuse), et les distributions en sortie continue (comme archlinux).  
Chacun y allant de ses pics, fausses vérités ou de ses arguments plus
foireux les uns que les autres…

</div>

<div class="texte surlignable">

Je connais bien les deux écoles, j’ai le cul entre deux chaises avec ma
stable qui appartient à la 1^re^ et ma sid qui peut passer dans la
seconde, sinon si sid ne vous conviens pas dans cette catégorie, j’ai eu
une époque archlinux. Autant je peux comprendre qu’on puisse vouloir
jouer a la montée de version autant je ne vois pas en quoi une debian
stable peut être obsolète.  
<!--more-->  
Comme d’habitude [Frederic
Bezies](http://frederic.bezies.free.fr/blog/){.spip_out} critique ce
qu’il ne comprend pas, c’est a dire que debian préfère la stabilité des
versions sur sa stable, au risque de ne pas avoir les dernières versions
qui ne changent rien sauf leurs numéros de version tout en critiquant
les utilisateurs de debian stable de zélote car on est pas de son avis,
oui c’est ça le zélote, il ne supporte pas qu’on puisse prouver le
contraire de ce qu’il dit...  
Je choisis comme lui le fait, de citer une partie :  
> il y a de temps en temps des polémiques qui montrent la limite de
> certaines politiques techniques, mais aussi l’aveuglement zélote de
> certains utilisateurs envers leur distribution.
> </p>

> Tomber dans le culte de la stabilité ne veut pas dire qu’on doive
> traiter les développeurs qui en ont marre de recevoir des rapports de
> bugs invalides car une distribution oublie de rétroporter certaines
> versions.

> La politique – au sens gestion de la cité – de Debian GNU/Linux envers
> sa branche stable est très bien, mais elle conduit IMMANQUABLEMENT à
> une obsolescence croissante d’une partie de la logithèque. On me
> rétorquera que stable veut dire solide comme du roc. Soit. Mais est-ce
> que cela signifie se trimballer des logiciels abandonnés en amont
> comme pour LibreOffice par exemple ?

.  

> Mais des logiciels plus sensibles comme une suite bureautique
> </p>

> C’est un problème de choix entre la stabilité et l’obsolence lente qui
> entraine une production de retours inutiles car déjà corrigé. Ce qui
> est vrai pour XScreenSaver doit aussi l’être pour LibreOffice. Je me
> demande combien de rapports de bugs liés à la version proposée par la
> Debian GNU/Linux Jessie (la 4.4.2) sont clos comme invalides ou
> pourrissent sur pied. Il est vrai qu’au 6 avril 2016, la version
> stable est la 5.0.5 et la version de « test » est la 5.1.1.

...  

> C’est un problème de communication et une politique de stabilité qui
> commence à montrer ses limites un an après la sortie d’une nouvelle
> Debian GNU/Linux stable.
> </p>

> Soit, c’est le risque que je prends. J’en reviens toujours à la même
> quadrature du cercle : Entre stabilité et fraicheur logicielle, il
> faut savoir trouver le point d’équilibre. Trop dur à faire
> comprendre ?

Pour le coté zélote, bon il est vrai, je suis pro-debian et lui est
pro-arch, lequel de nous est le plus fanatique ? Celui qui ne fait que
répéter que debian est obsolète ou celui qui démonte ses lignes une par
une ? Dans les commentaires, je lui répond et vu que je ne suis pas de
son avis, il est désagréable et casse mais a part lancer des trucs sur
une distributions qu’il n’a pas l’air de connaître, c’est ça d’être sur
une distribution en rolling, on passe son temps a géré son système et on
ne voit pas ce qui nous entoure…  
Donc il avance des choses comme dans son article, « se trimballer des
logiciels abandonnés en amont comme pour LibreOffice », non Fred(puis je
t’appeler ainsi ?) les logiciels sous debian stable ne sont pas
abandonner, même si les versions ne sont plus maintenues en amont,
debian continue de fournir des patchs de sécurité pour les mises a jour
concernant des failles. Elle va même jusqu’à envoyer les corrections au
développeur pour en cas ou il les incorpore dans les dites versions.
Ensuite, comme logiciels « plus sensibles », il y a plus risqué qu’une
suite bureautique… Il aurais pu parler de navigateur web sous debian
mais non il décide de parler de la suite bureautique. Bon, alors si on
veut vraiment parler de la suite bureautique qui est je cite « la
version proposée par Debian GNU/Linux Jessie (la 4.4.2) » prouve « un
problème de communication et une politique de stabilité qui commence à
montrer ses limites un an après la sortie d’une nouvelle Debian
GNU/Linux stable. » car « la version stable est la 5.0.5 et la version
de « test » est la 5.1.1. », je dis seulement que debian propose une
version 4.4.x et une 5.1.1 qui est elle, [la dernière version stable du
projet](https://fr.libreoffice.org/download/libreoffice-stable/){.spip_out},
dans [backports](http://passiongnulinux.tuxfamily.org/?p=17){.spip_in}.
D’apres lui c’est compliqué et pas faisable par tous car si je reprend
ses mots :  
« Devoir jongler avec trois niveaux de dépôts, voire quatre, rajouter
des dépôts tiers, c’est à la portée du premier venu. » voulant dire par
la que c’est compliqué et « C’est juste le principe de devoir rajouter
un dépôt. Trop habitué à une distribution qui évite le rajout de dépôt
pour le moindre logiciel. », ça me paraît trop gros comme foutage de
gueule.  
Il est le premier a nous parler de arch, de son installateur (qui n’est
pas des plus facile) et du AUR. En gros il est en train de dire que
l’activation du dépôt backports est compliqué alors que celui-ci peut se
faire en graphique via synaptic et logithèque de gnome… Alors que la
même personne nous donne les mérites d’un truc plus complexe (c’est a
dire aur et arch en générale)… De plus pour être franc jusqu’au bout, je
lui ai dis qu’on avait la possibilité sous debian de facilement
rétro-porter les versions, c’est a dire sous stable rebuilder les
paquets directement de sid pour avoir les dernières versions (voir
[Création de paquets
DEB](http://passiongnulinux.tuxfamily.org/?p=30){.spip_in} ). Ce qui est
pour moi aussi facile que yaourt et AUR… La ou il a pas tord c’est quand
il dis ceci : « C’est un problème de choix entre la stabilité et
l’obsolence lente qui entraine une production de retours inutiles car
déjà corrigé. » .  
Mais encore une fois est ce la faute a debian si des utilisateurs font
des rapports de bugs au mauvaise endroit ? Debian est clair sur ce
point, je cite le
[wiki](http://www.debian.org/Bugs/Reporting){.spip_out} :  

> **Ne pas signaler le bogue en amont**  
> Si vous signalez le bogue dans Debian, n’envoyez pas vous-même de
> copie aux responsables amonts du logiciel, car il est possible que le
> bogue n’existe que dans Debian. Si nécessaire, le responsable du
> paquet fera suivre le bogue.
> </p>

Alors comme d’habitude il se victimise, se plaint (je cite son dernier
article
[http://frederic.bezies.free.fr/blog...](http://frederic.bezies.free.fr/blog/?p=14291){.spip_out}
) dont le titre est evocant :  

> Communauté gangrénée par ses extrémistes divers, que ce soit en
> relation avec le système d’initialisation (pro ou anti systemd), la
> distribution GNU/Linux (pro ou anti-Debian / Archlinux / Fedora, etc…)
> </p>

> Outre le fait que j’ai déjà dit plusieurs fois que cette inutile
> guerre sur les systèmes d’initialisation ne servira en rien la cause
> du libre,

Mais le monsieur ne fait que répéter a bout de champs :  

> J’en reviens toujours à la même quadrature du cercle : Entre stabilité
> et fraicheur logicielle, il faut savoir trouver le point d’équilibre.
> Trop dur à faire comprendre ?
> </p>

Je réitère la question, est ce si dur a comprendre que stable chez
debian c’est :  
Des mises a jour qui ne vont pas :

-   faire évoluer la logithèque,
-   installer des programmes supplémentaires,
-   retirer des programmes,
-   ajouter des fonctions,
-   retirer des fonctions,
-   …

Ce qui va être fait par les mises a jour :

-   corrections de bugs,
-   corrections de sécurité,

Et comme stabilité pour debian signifie :

-   stabilité du logiciel, le moins de bugs possible(comme toute
    distribution de qualité normalement)
-   stabilité des fonctionnalités, comme dit plus haut, pas d’ajouts ni
    de pertes de fonctions, tel programme doit être en mesure de faire
    les mêmes choses au début de la version stable et jusqu’à la fin de
    cette stable
-   stabilité de l’archive, pas d’ajout ni de perte de programmes, les
    dépôts debian doivent contenir le même nombre de paquets a la sortie
    de la stable(etch admettons) et jusqu’à la fin de sa vie.

<p>
De ce fait, on n’est pas « surpris » de ne plus trouver tel paquet, de
voir tel programme perdre telle fonction… Et surtout une mise a jour
debian ne change rien et ne touche a rien, elle corrige seulement… Est
ce dur a comprendre qu’on est pas tous accro a la monté de version qui
apporte rien, chrome en est un exemple, firefox aussi qui suit
maintenant cette mode de celle qui a la plus grosse. A quoi me sert le
dernier libreoffice pour le peu que je m’en sert ?  
A quoi me sert le dernier kde a part jouer avec ?  
A quoi me sert le dernier gnome si ce n’est que voir des régressions sur
certain point ?

</div>

</div>

 
