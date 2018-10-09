---
title: "Installation Debian 2"
date: 2017-12-02T20:08:04+01:00
layout: post
---

Ce que je fais après l'installation de ma Debian #2

Depuis le dernier billet parlant de mon installation de debian, j'ai 
remarqué des oublis, et comme annoncé a la fin du billet, je vais écrire
 ici certains manques. Pourquoi pas sur le précédent, simplement que 
j'ai peur que ça passe a la trappe.

J'avais oublié létape qui permet de rendre <a class="ref-post" href="http://passiongnulinux.tuxfamily.org/?p=35">les applications GTK mieux intégrés dans KDE</a>:
<ul><li>
<div><a class="urlextern" title="http://packages.debian.org/kde-config-gtk-style" href="http://packages.debian.org/kde-config-gtk-style" target="blank">kde-config-gtk-style, module de configuration de KDE pour la sélection du style GTK+ 2/3.x</a></div></li><li>
<div><a class="urlextern" title="http://packages.debian.org/gtk2-engines-oxygen" href="http://packages.debian.org/gtk2-engines-oxygen" target="blank">gtk2-engines-oxygen,thème Oxygen pour les applications basées sur GTK2+</a></div></li><li>
<div><a class="urlextern" title="http://packages.debian.org/gtk3-engines-oxygen" href="http://packages.debian.org/gtk3-engines-oxygen" target="blank">gtk3-engines-oxygen,thème Oxygen pour les applications basées sur GTK3+ (Debian Wheezy)</a></div></li></ul>
<div>Donc dans une console:</div>
<pre> # apt-get install kde-config-gtk-style gtk2-engines-oxygen gtk3-engines-oxygen</pre>
Je rassemblerais les différents billets, car d'autres vont suivre, sur une seule page.
