---
title: Ce que je fais après l'installation de ma Debian 2
date: 2016-07-14
layout: post
---

Depuis le dernier billet parlant de mon installation de debian, j'ai
remarqué des oublis, et comme annoncé a la fin du billet, je vais écrire
ici certains manques. Pourquoi pas sur le précédent, simplement que j'ai
peur que ça passe a la trappe. J'avais oublié l’étape qui permet de
rendre [les applications GTK mieux intégrés dans
KDE](http://passiongnulinux.tuxfamily.org/?p=35){.ref-post}:

-   <div>

    [kde-config-gtk-style, module de configuration de KDE pour la
    sélection du style GTK+
    2/3.x](http://packages.debian.org/kde-config-gtk-style "http://packages.debian.org/kde-config-gtk-style"){.urlextern}

    </div>

-   <div>

    [gtk2-engines-oxygen,thème Oxygen pour les applications basées sur
    GTK2+](http://packages.debian.org/gtk2-engines-oxygen "http://packages.debian.org/gtk2-engines-oxygen"){.urlextern}

    </div>

-   <div>

    [gtk3-engines-oxygen,thème Oxygen pour les applications basées sur
    GTK3+
    (Debian Wheezy)](http://packages.debian.org/gtk3-engines-oxygen "http://packages.debian.org/gtk3-engines-oxygen"){.urlextern}

    </div>

<div>

Donc dans une console:

</div>

     # apt-get install kde-config-gtk-style gtk2-engines-oxygen gtk3-engines-oxygen

Je rassemblerais les différents billets, car d'autres vont suivre, sur
une seule page.
