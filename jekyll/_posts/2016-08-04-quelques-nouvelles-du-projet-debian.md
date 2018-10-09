---
title: Quelques nouvelles du projet Debian
date: 2016-08-04 01:49
layout: post
---

Dans le dernier [Nouvelles du projet
Debian](https://www.debian.org/News/weekly/2016/03/) du 29 juillet 2016,
on apprend comme toujours pas mal de petites choses qui peuvent
intéresser, comme:  
<!--more-->

-   **Mate 1.14 dans unstable:** Mike Gabriel [a
    annoncé](https://sunweavers.net/blog/node/42) que MATE 1.14 a été
    introduit dans unstable, avec des constructions pour les
    23 architectures prises en charge par Debian. Mike remarque que le
    changement principal est le passage de GTK2 à GTK3 et qu'il y a
    quelques problèmes connus comme ceux rencontrés lors d'une exécution
    dans une session de bureau distant basé sur NXv3. L'équipe remercie
    tous ceux qui ont aidé à l'introduction de MATE dans Debian.
-   **Nouvelles diverses pour les développeurs:** Julien Cristau a
    envoyé le [n° 41 des Nouvelles diverses pour les
    développeurs](https://lists.debian.org/debian-devel-announce/2016/06/msg00002.html).
    Parmi les points forts : la nouvelle version de debhelper compat 10
    est prête pour des tests ; les paquets source peuvent maintenant
    inclure des signatures de l'amont ; une modification dans Apt permet
    d'utiliser “by-hash” pour éviter des incohérences de somme de
    hachage ; de petits changements de miroir pour améliorer le réseau
    de miroirs de Debian ; la suite “stretch-debug” est maintenant
    remplie, et le paquet init perd son statut “essential” et “required”
    peut ainsi être exclu des chroots minimaux.
-   **Versions intermédiaires:** Debian “Wheezy”
    [7.11](https://www.debian.org/News/2016/2016060402) : la onzième et
    dernière mise à jour de la version oldstable Debian 7 (nom de code
    “Wheezy”) a été publiée le 4 juin 2016. Debian “Jessie”
    [8.5](https://www.debian.org/News/2016/20160604) : la cinquième mise
    à jour de la version stable Debian 8 (nom de code “Jessie”) a aussi
    été publiée le 4 juin 2016.
-   **Modifications dans le processus des nouveaux membres:** Enrico
    Zini
    [signale](https://lists.debian.org/debian-devel-announce/2016/06/msg00003.html)
    certaines modifications dans le processus des nouveaux membres ainsi
    qu'un guide du processus de candidature. Le site
    [nm.debian.org](https://nm.debian.org) offre maintenant une gestion
    en libre-service de l'essentiel des démarches qui devrait aider les
    candidats et leurs intercesseurs pour fournir les données et les
    informations, et, pour les responsables des comptes et les
    développeurs Debian, faciliter leur avis. Ces changements améliorent
    le processus des nouveaux membres dans divers domaines, notamment en
    aidant les responsables des comptes Debian et les membres du bureau
    de Debian à se concentrer sur les vérifications et les décisions sur
    les candidatures.
-   **Wheezy LTS et le passage à OpenJDK 7:** Markus Koschany a
    poursuivi les précédentes [annonces sur la prise en
    charge](https://www.debian.org/News/2016/20160425) et les
    modifications de Wheezy LTS. Il a donné plus d'informations sur le
    contexte de la décision de [passer de OpenJDK 6 à OpenJDK 7 dans
    Wheezy
    LTS](http://java.debian.net/blog/2016/06/wheezy-lts-and-the-switch-to-openjdk-7.html),
    un changement déclenché par la fin de vie d'Ubuntu 12.04 qui
    utilise OpenJDK 6. Ce passage a pris en considération le choix d'une
    version par défaut pour un cycle de version stable, l'impact qu'il
    pourrait avoir sur les utilisateurs et une interrogation sur le
    besoin de la prise en charge de JDK6 pour une courte période de
    12 mois en comparaison de la longueur de la durée du suivi à long
    terme (LTS).
-   **Brèves du chef de projet Debian:** Mehdi Dogguy, chef du projet
    Debian [donne des
    nouvelles](https://lists.debian.org/debian-devel-announce/2016/06/msg00008.html)
    de ses activités et des événements dans le projet. Il a annoncé les
    modifications faites à la délégation de l'équipe Newmaint, des notes
    sur sa participation à DebConf16 et au camp d'été, des nominations
    pour l'équipe anti-harcèlement, un compte-rendu sur les procédures
    de remboursement et les achats d'actifs.
-   **GCC 6 et binutils pour la publication de Debian Stretch:**
    Matthias Klose [a annoncé que GCC 6 serait par
    défaut](https://lists.debian.org/debian-devel-announce/2016/06/msg00007.html)
    la collection de compilateurs GNU pour Stretch. GCC 6 est disponible
    dans testing et peut à présent devenir la version par défaut des
    systèmes en installant les paquets gcc/g++ à partir d'experimental.
    Matthias signale les échecs de construction connus et les projets
    pour la publication. Les paquets qui utilisent les versions
    précédentes de GCC deviendront critiques pour la
    prochaine publication. Binutils va passer d'un cycle de publication
    de 12 mois à un cycle de 6 mois ; binutils 2.27 ou plus est attendu
    pour Stretch.
-   **Nouvelle équipe pkg-security:** Gianfranco Costamagna [a annoncé
    une nouvelle équipe
    pkg-security](https://lists.debian.org/debian-devel/2016/06/msg00259.html)
    qui se focalisera sur la fourniture d'une liste des outils de
    sécurité maintenus par des distributions aval et sur leur fusion en
    retour dans Debian. Le [wiki de l'équipe
    pkg-security](https://wiki.debian.org/Teams/pkg-security) contient
    plus d'information sur l'équipe, ses tâches et son infrastructure.
-   **Résolutions générales:** [Remplacement de « Chairman » par
    « Chair » dans toute la Constitution
    de Debian.](https://www.debian.org/vote/2016/vote_003) – proposition
    de Margarita Menterola, voici le lien vers la
    [discussion](https://lists.debian.org/debian-vote/2016/07/msg00028.html).
    [Rendre publique la liste de diffusion
    debian-private](https://www.debian.org/vote/2016/vote_002)
    – proposition de Nicolas Dandrimont, voici le lien vers la
    [discussion](https://lists.debian.org/debian-vote/2016/07/msg00089.html).On
    y découvre des discussions intéressantes qui peuvent être noyé parmi
    les milliers de posts, comme la discussion de la liste des
    développeurs Debian, Steve McIntyre réfléchit sur l'utilité d'une
    [version “Jessie et
    demi”](https://lists.debian.org/debian-devel/2016/07/msg00054.html).
    Bien que le nom ne soit pas fixé, la discussion sur ce qui doit être
    inclus dans cette publication commence avec un noyau rétroporté, un
    installateur Debian reconstruit, des pilotes X, xserver et
    d'autres paquets. L'idée est que plusieurs portages arm64, amd64
    récent et ppc64el devraient bénéficier de cette publication et de
    son image d'installation réseau.

De bonnes choses comme toujours, notamment des astuces comme [un guide
du débutant pour les paquets source de
Debian](http://thewaterbabe.in/2016/06/13/a-beginners-guide-to-debian-source-packages/)partagé
par Keerthana Krishnan. Pour ceux qui ne connaissent pas ce petit
récapitulatif c'est [ici que ça se
passe](https://www.debian.org/News/weekly).
