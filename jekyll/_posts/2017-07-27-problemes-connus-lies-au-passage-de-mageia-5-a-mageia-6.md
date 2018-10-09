---
title: Problèmes connus liés au passage de Mageia 5 à Mageia 6
date: 2017-07-27 14:19
layout: post
---

Je matais un peu le blog en attendant que Mageia s'installe, je tombe
sur
[ça](http://blog.mageia.org/fr/2017/07/22/problemes-connus-lies-au-passage-de-mageia-5-a-mageia-6/):  

> Depuis la sortie de [Mageia 6 la semaine
> dernièr](https://blog.mageia.org/fr/2017/07/16/mageia-6-est-la/)e, il
> y a eu plusieurs rapports d’erreurs concernant la mise à jour à partir
> de Mageia 5, en particulier pour les utilisateurs opérant sous KDE 4.
> Ce n’est pas surprenant lorsque l’on voit la complexité du passage de
> KDE 4 à PLASMA 5, ces problèmes n’ont malheureusement pas été détectés
> par l’équipe Assurance Qualité durant la phase de tests avant
> publication. Nous désirons à la fois reconnaître que nous sommes
> conscients des problèmes et travaillons à les résoudre et nous assurer
> que ceux qui désirent mettre Mageia 5 à niveau soient conscients des
> problèmes et[lisent préalablement les
> errata](https://wiki.mageia.org/en/Mageia_6_Errata-fr). Pour éviter de
> mauvaises surprises aux utilisateurs les moins techniquement à l’aise,
> nous avons désactivé temporairement la notification de mise à niveau
> qui invite les utilisateurs a évoluer vers Mageia 6 à partir de leur
> session en cours.  
> <!--more-->  
> Notons que ces soucis n’existent pas dans le cas des installations
> nouvelles et que d’après les expériences d’installation, en
> particulier,  les passages de KDE4 vers Plasma 5 sont nettement plus
> faciles par une nouvelle installation. A priori tous les problèmes de
> mises à niveau devraient être corrigés par des mises à jour de
> paquetages, aussi nous n’envisageons pas de publier de nouvelles
> images ISO. La section dans l’errata concernant[les mises à
> niveau](https://wiki.mageia.org/en/Mageia_6_Errata-fr#Probl.C3.A8mes_de_mise_.C3.A0_niveau)
> détaille la procédure pour minimiser certains des problèmes connus. Il
> est important de  noter  que l’utilisation de paquetages tiers
> installés dans Mageia 5, tels que les pilotes graphiques, constitue
> une source importante de problèmes. Voici un petit résumé des points à
> considérer :
>
> -   La mise à niveau depuis KDE 4 avec mgaonline amène un affichage
>     détérioré, donc les utilisateurs ignorent le résultat de
>     l’installation et risquent de redémarrer sur un système
>     non fonctionnel.
>     -   [L’errata au sujet des mises à
>         niveau](https://wiki.mageia.org/en/Mageia_6_Errata-fr#Probl.C3.A8mes_de_mise_.C3.A0_niveau),
>         particulièrement [les notes sur les systèmes
>         complexes](https://wiki.mageia.org/en/Mageia_6_Errata-fr#Conseil_pour_les_mises_.C3.A0_niveau_complexes)
>         peuvent aider pour terminer une mise à niveau.
> -   Les pilotes graphiques sont aussi un problème, surtout NVIDIA.
>     Plusieurs utilisateurs font face à un [problème de boucle sans
>     fin](https://bugs.mageia.org/show_bug.cgi?id=21263).
>     -   Assurez vous d’utiliser les pilotes officiels de Mageia avant
>         la mise à niveau, il y a aussi [des moyens de se sortir de ce
>         problème dans
>         l’errata](https://wiki.mageia.org/en/Mageia_6_Errata-fr#Red.C3.A9marrages_sans_fin_apr.C3.A8s_avoir_bascul.C3.A9_entre_les_pilotes_graphiques_NVIDIA_libres_et_propri.C3.A9taires)
>         et dans ce [rapport de
>         bogue](https://bugs.mageia.org/show_bug.cgi?id=21263).
>
> Une remarque au sujet des mises à niveau en général, les réaliser hors
> ligne avec l’ISO Classique ne fonctionne que si les dépôts updates
> sont activés, car une mise à niveau complète de Mageia 5 exige plus de
> paquetages que ceux qui sont disponibles sur l’image ISO. La façon
> recommandée de démarrer une mise à niveau est de la réaliser depuis un
> terminal non graphique (par ex. tty2 accessible via Ctrl+Alt+F2) en
> utilisant urpmi, comme souligné dans [les notes de
> version](https://wiki.mageia.org/en/Mageia_6_Notes_de_version-fr#Mise_.C3.A0_niveau_en_ligne.2C_en_utilisant_urpmi_.28ligne_de_commande.2FCLI.29).
> Si vous rencontrez un problème de mise à niveau, prenez contact avec
> la communauté sur [les
> forums](https://www.mageialinux-online.org/mlo/), [listes de
> diffusion](https://ml.mageia.org/l/info/discuss) ou
> [IRC](irc://irc.freenode.net/#mageia%22), où des utilisateurs avertis
> peuvent vous aider à résoudre les problèmes et bien souvent à réparer
> un système en apparence détruit. En dehors de ces problèmes de mises à
> niveau qui affectent quelques utilisateurs de Mageia 5, la plupart de
> ceux qui utilisent Mageia 6 semblent plutôt satisfaits, nous allons
> continuer de présenter certains des développements intéressants
> réalisés pour cette publication dans de futurs billets. *Rédigé par
> Donald Stewart – Traduit par Yogilou et Lebarhon*

En voyant cette annonce on se demande à quoi a servit la longue attente,
je pensais que Mageia testait un peu pendant cette phase les différents
bureaux et leurs mises à jour depuis la version précédente de Mageia...
On va encore dire que je casse du sucre sur la dite distribution.
