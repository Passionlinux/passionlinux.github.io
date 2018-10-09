---
title: RPM a des failles, REDHAT n'a pas les moyens de s'en occuper !#2
date: 2016-09-28 13:08
layout: post
---

Je fais suite ici au premier billet portant [le même
titre](http://passiongnulinux.tuxfamily.org/2016/09/23/rpm-a-des-failles-redhat-na-pas-les-moyens-de-sen-occuper/),
Cascador est venu compléter dans les commentaires et a donné le lien ou
j'avais eu l'info, merci a lui, car j’écris avec quelques difficultés,
comme actuellement avec ma connexion qui est perdu, merci a Wordpress de
sauvegarder directement dans mon navigateur pour éviter de perdre ce que
j’écris, un plus qui fait que je garde ce Wordpress, même si je compte
repasser maintenant a Dotclear au lieu de SPIP (c'est a méditer et pas a
faire d'un simple coup de tête...). Je balance ici et non sur le
précédent billet pas pour faire gonfler les stats de mon blog mais pour
une question de praticité, en effet je vais citer les différents
protagonistes et de plus, je pense que c'est quelque chose d'important
car c'est le cœur d'une distribution qui est touché.  
<!--more-->  
Sur le précédent je parlais de DEB et de RPM, ce n'est pas DEB (format
de paquets) qui est touché mais bien le concurrent de RPM (outils en
ligne de commande pour gérer ses paquets et non le format de paquets
portant le même nom). Je cite un peu mes conneries:  

> Avant de partir, j’avais été interpellé par un sujet, ne trouvant plus
> ni la source ni d’autre qui en parle, une comparaison de RPM face a
> DEB que RPM et DEB comportaient des bugs et des failles, juste la
> c’est normale, mais que les corrections allaient plus vite sur DEB
> alors que RPM tardait a être corrigé et comme réponse REDHAT donnait
> qu’il n’avait pas les moyens pour corriger a toute allure ! Alors que
> DEB a corrigé très vite…
> </p>

Bon on recommence et on remplace la ou il y a
[DEB](https://fr.wikipedia.org/wiki/Deb) par
[Dpkg](https://fr.wikipedia.org/wiki/Dpkg) et donc il faut bien sur lire
[RPM](https://fr.wikipedia.org/wiki/RPM_Package_Manager) comme
[gestionnaire de
paquet](https://fr.wikipedia.org/wiki/Gestionnaire_de_paquets) et non le
[format de
paquets](https://fr.wikipedia.org/wiki/Gestionnaire_de_paquets#D.C3.A9finitions),
c'est ça d’être sans une connexion internet fiable et rapide, on se sent
coupé du monde et on fait le téléphone arabe, ce qui donne un truc bien
différent de ce qui est dit a l'origine!! Donc j'ai en effet lu sur le
[blog de Cyrille](https://cyrille-borne.com/social/), ou plutôt l'un des
blogs de Cyrille, un billet qui, je le reprend dans son intégralité ici
mais qui est disponible [a cette
adresse](https://cyrille-borne.com/social/index.php?article57/vulnerabilites-dans-rpm),
parle de quelque chose qui n'a pas fait grand bruit et qui pourtant
touche en profondeur chaque linuxien puisque c'est le gestionnaire de
paquets, un outils puissant et surtout vitale pour le système. Je
m'aperçois du reste que ce n'est pas Cyrille mais Cep qui l’écrit,
[c'est pas la première fois que je me fais piéger par c'est le blog de
Cyrille donc c'est Cyrille qui écrit uniquement! (voir le commentaire de
Cascador).](http://passiongnulinux.tuxfamily.org/2016/08/05/lmde-lautre-deception/)
Voici le billet en question:  

> Vulnérabilités dans RPM
> =======================
>
> <small> Rédigé par cep - <time datetime="2016-08-31">31 août
> 2016</time> - [Aucun
> commentaire](https://cyrille-borne.com/social/index.php?article57/vulnerabilites-dans-rpm#comments "Aucun commentaire")
> </small> Hanno Böck, journaliste freelance, a réalisé quelques tests
> de sécurité sur les gestionnaires de paquets DPKG et RPM et remonté
> quelques bugs critiques qu'il a signalés aux différents responsables.
> Il semblerait que pour DPKG la réactivité à corriger les failles fut
> excellente. Concernant RPM ce ne serait pas le cas et il note aussi
> quelques difficultés à trouver des responsables. Il note par ailleurs,
> d'après lui, un développement cahotique. Ceci semble tout de même
> curieux lorsqu'on sait que derrière RPM il y a principalement Redhat.
> À suivre.
> [Sources](https://blog.fuzzing-project.org/52-Multiple-vulnerabilities-in-RPM-and-a-rant.html)

Comme c'est intéressant mais ce qui est encore plus intéressant c'est
[l'article
source](https://blog.fuzzing-project.org/52-Multiple-vulnerabilities-in-RPM-and-a-rant.html)
en lui même, je passe par la traduction de google pour livrer quelque
chose de potable dans notre langue et voici donc l'article complet en
français traduis par google (j'espere avoir les droits:  

<header class="clearfix">
> <span class="notranslate">[Multiples vulnérabilités dans RPM - et une diatribe](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=https://blog.fuzzing-project.org/52-Multiple-vulnerabilities-in-RPM-and-a-rant.html&usg=ALkJrhjk8V702BZT8ufa8V_9exxitZKLew)</span>
> ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
>
> <span class="notranslate"> <span
> class="serendipity_byline block_level"><span
> class="single_user">Publié par [Hanno
> Böck](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=https://blog.fuzzing-project.org/authors/1-Hanno-Boeck&usg=ALkJrhjIpuB24ScRRavXRXTJmH0lGqw_fA)
> sur</span></span></span> <time datetime="2016-08-26T16:45:00+02:00">
> <span class="notranslate"> <span
> class="serendipity_byline block_level">Vendredi, Août 26.
> 2016</span></span> </time>

</header>
> <div class="clearfix content serendipity_entry_body">
>
> <span class="notranslate"> L'année dernière en Novembre je décidai que
> ce pourrait être une bonne idée de fuzz les parseurs d'outils de
> gestion des paquets dans les distributions Linux.</span> <span
> class="notranslate"> Je me suis vite trouvé un couple de questions
> DPKG et RPM.</span> <span class="notranslate"> Pour dpkg le processus
> est allé très lisse.</span> <span class="notranslate"> Je leur ai
> signalé à l'équipe de sécurité de Debian, huit jours plus tard, des
> correctifs et des avis de sécurité ont été publiés à la fois par
> Debian et Ubuntu, les principales distributions utilisant dpkg.</span>
> <span class="notranslate"> Pour RPM le processus a été un peu plus
> difficile.</span> <span class="notranslate"> Si vous voulez signaler
> un bug à vous RPM premier peut se demander où en faire rapport.</span>
> <span class="notranslate"> Le RPM page web \[1\] est une installation
> de trac qui a son propre bug tracker.</span> <span
> class="notranslate"> Toutefois, si vous essayez d'enregistrer un
> compte là, vous serez redirigé vers un site HTTPS avec un certificat
> expiré qui ne correspond pas au nom de domaine.</span> <span
> class="notranslate"> Dans le cas où vous êtes courageux et dire à
> votre navigateur d'ignorer tous les avertissements, vous serez
> accueillis par un trac cassé prospectifs sans CSS.</span> <span
> class="notranslate"> Si vous passez et créer un compte, vous
> apprendrez que cela ne vous aide pas, parce que, pour être autorisé à
> signaler un bug, vous devez d'abord demander sur la liste de diffusion
> ou dans le canal IRC pour l'autorisation \[2\].</span> <span
> class="notranslate"> C'est probablement le point où beaucoup de
> journalistes bien intentionnés de bugs abandonner.</span> <span
> class="notranslate"> D'accord, mais RPM signifiait à l'origine
> "gestionnaire de paquets Red Hat" (on m'a dit aujourd'hui qu'il
> représente RPM Package Manager), alors peut-être Red Hat se sent
> responsable.</span> <span class="notranslate"> Donc, je l'ai signalé
> trois bugs avec des exemples de fichiers les déclencher à l'équipe de
> sécurité de Red Hat le 20 Novembre.</span> <span class="notranslate">
> La réponse a été - pour le moins - un peu insatisfaisantes.</span>
> <span class="notranslate"> Je vais vous citer pleinement: "Merci pour
> le rapport.</span> <span class="notranslate"> Nous avons également
> reçu au sujet de 30 rapports d'erreur dans RPM de</span> <span
> class="notranslate"> un journaliste différent récemment, donc le
> traitement de chacun d'eux (le vôtre et le</span> <span
> class="notranslate"> autres) vont prendre un peu de temps.</span>
> <span class="notranslate"> Nous ne disposons tout simplement les
> ressources</span> <span class="notranslate"> de passer des heures et
> des heures à analyser tous les rapports d'erreur ".</span> <span
> class="notranslate"> Ok, donc je ne suis pas le seul RPM de fuzzing et
> les peut-être des bugs seront corrigés un jour.</span> <span
> class="notranslate"> J'ai attendu.</span> <span class="notranslate">
> En attendant, je suis contacté par une autre personne qui avait
> également essayé de rapporter les bogues de fuzzing en RPM et qui a
> fait des expériences similaires (peut-être la même personne qui a
> rapporté les 30+ Crashers, je ne sais pas).</span> <span
> class="notranslate"> En Février, je décidé de demander à ce que l'état
> des choses est.</span> <span class="notranslate"> Je leur ai aussi
> donné une période de 30 jours jusqu'à ce que je publierai les bugs (je
> sais qu'il est maintenant passé depuis longtemps, je ne devrais pas
> avoir laissé cette question attendre si longtemps).</span> <span
> class="notranslate"> Je fini par avoir un appel avec un membre de
> l'équipe de sécurité de Red Hat et échangé quelques mails.</span>
> <span class="notranslate"> J'appris que RPM a un dépôt Github \[3\],
> qui contient des correctifs pour certains (mais pas tous) des
> questions que je rapporté, toutefois que cela nulle part référencées
> sur son site Internet.</span> <span class="notranslate"> Je puis
> Fuzzed le code RPM git actuelle à nouveau et a trouvé deux autres
> questions que je signale également l'équipe de sécurité de Red
> Hat.</span> <span class="notranslate"> Statut aujourd'hui est que la
> dernière version de RPM sur son site Internet - 4.12.0.1 - est à
> partir de Juillet 2015, de sorte que tous les bugs encore affecte
> cette version.</span> <span class="notranslate"> Cependant, il semble
> qu'il y ait un non-officiel 4.13 de presse qui est nulle part pour
> être trouvée sur la page Web du RPM, mais Red Hat utilise ensemble
> avec quelques corrections \[4\].</span> <span class="notranslate"> Et
> le dépôt Github dit la dernière version est 4.12.0, donc selon trois
> sources différentes trois versions différentes sont l'actuel (4.12.0,
> 4.12.0.1, 4.13).</span> <span class="notranslate"> Un des bogues - un
> débordement de pile (en écriture) - est encore présent dans le dernier
> code sur Github.</span> <span class="notranslate"> **Commend et
> conclusion**</span> <span class="notranslate"> Ce blog se lit
> probablement comme un grand coup de gueule sur la façon non
> professionnelle Red Hat est dans le traitement des problèmes de
> sécurité potentiels.</span> <span class="notranslate"> Mais cela est
> contraire à mon expérience habituelle.</span> <span
> class="notranslate"> Je vois souvent des développeurs Red Hat étant
> très actif dans la communauté de la sécurité du logiciel libre et
> souvent contribuer de manière positive.</span> <span
> class="notranslate"> Tout simplement je pense mieux de Red Hat.</span>
> <span class="notranslate"> Ce n'est pas un vendeur de l'entreprise
> douteuse où je ne serais pas le moins peu surpris d'une telle
> réaction.</span> <span class="notranslate"> Le processus de
> développement de RPM semble être totalement chaotique, il est clair ni
> où l'on signale des bugs ni où l'on obtient les derniers bugs de code
> et de sécurité ne sont pas fixés dans un délai raisonnable.</span>
> <span class="notranslate"> Il y a eu quelques événements récents qui
> me font sentir particulièrement inquiet à ce sujet: Un inconnu a créé
> une entrée dans le numéro de suivi libarchive \[5\] qui pointe vers un
> document anonyme \[6\] avec une description très détaillée des
> diverses failles de sécurité dans le FreeBSD processus de mise à jour
> (la plupart d'entre eux sont encore non fixée).</span> <span
> class="notranslate"> La chose la plus inquiétante à ce sujet est
> cependant que le poste anonyme mentionne l'existence des documents
> similaires affectant plusieurs distributions Linux.</span> <span
> class="notranslate"> Ces documents ne sont pas encore publiquement
> montré et étant donné la nature incertaine de cet incident, il est
> difficile de savoir si jamais ils deviendront publics ou
> exister.</span> <span class="notranslate"> Mais cela devrait être
> encore assez pour avoir un oeil plus attentif aux failles de sécurité
> potentielles dans toutes les pièces de systèmes de gestion de paquets
> Linux raison.</span> <span class="notranslate"> Je ne l'ai pas analysé
> le processus d'installation du RPM en détail, je ne peux pas dire à
> quel point il est probable que l'outil RPM ne voit jamais un fichier
> d'entrée malformé.</span> <span class="notranslate"> Il semble
> téléchargements se produisent sur HTTP, mais la première chose qui se
> passe est une vérification de signature.</span> <span
> class="notranslate"> Comme la signature fait partie du fichier RPM il
> doit déjà être analysé pour cela.</span> <span class="notranslate">
> L'impact exact de ces bugs nécessiterait une analyse plus
> approfondie.</span> <span class="notranslate"> Mais indépendamment de
> la façon dont probable que ce soit, je pense que l'analyseur dans un
> tel élément crucial du logiciel devrait être robuste.</span> <span
> class="notranslate"> Il doit être sûr d'utiliser l'outil rpm pour
> afficher des informations sur un fichier sur la ligne de
> commande.</span> <span class="notranslate"> \[1\]
> [http://rpm.org/](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=http://rpm.org/&usg=ALkJrhh4E4lroyqxHLnmBt_JOdsAZpfTiw)</span>
> <span class="notranslate"> \[2\]
> [http://rpm.org/wiki/ReportingBugs](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=http://rpm.org/wiki/ReportingBugs&usg=ALkJrhj-R1bvbby-JHF2PMvf7yG93AhUtg)</span>
> <span class="notranslate"> \[3\]
> [https://github.com/rpm-software-management/rpm](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=https://github.com/rpm-software-management/rpm&usg=ALkJrhiH82Lm2IseItGAtlJun7cCNXDgmQ)</span>
> <span class="notranslate"> \[4\]
> [http://pkgs.fedoraproject.org/cgit/rpms/rpm.git/diff/rpm-4.13.0-rpmtd-out-of-bounds.patch?h=f22&id=165614f3dd42caa188f78b55e7723dad2900b2f4](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=http://pkgs.fedoraproject.org/cgit/rpms/rpm.git/diff/rpm-4.13.0-rpmtd-out-of-bounds.patch%3Fh%3Df22%26id%3D165614f3dd42caa188f78b55e7723dad2900b2f4&usg=ALkJrhjfXWX0ljZnUWSXXGApZfchOi112Q)</span>
> <span class="notranslate"> \[5\]
> [https://github.com/libarchive/libarchive/issues/743](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=https://github.com/libarchive/libarchive/issues/743&usg=ALkJrhhiiCCDXlAqwcPopjiAfDHMP3nnMA)</span>
> <span class="notranslate"> \[6\]
> [https://gist.github.com/anonymous/e48209b03f1dd9625a992717e7b89c4f](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=https://gist.github.com/anonymous/e48209b03f1dd9625a992717e7b89c4f&usg=ALkJrhhLcZ0wPMgm56l_UZjPJy2Tdl5EwA)</span>
> <span class="notranslate"> Tous les bugs ont été trouvés avec l'aide
> de lop floue américain.</span> <span class="notranslate"> Voici les
> bugs:</span> <span class="notranslate"> Stack Overflow dans glob () /
> rpmglob.c.</span> <span class="notranslate"> Exemple de fichier (test
> avec rpm -i \[entrée\]):</span> <span class="notranslate">
> <https://crashes.fuzzing-project.org/rpm-stackoverflow-glob.rpm></span>
> <span class="notranslate"> Non fixée dans le code de Git en
> cours.</span> <span class="notranslate"> Heap hors limites lu
> headerVerifyInfo () / header.c.</span> <span class="notranslate">
> Exemple de fichier (test avec "rpm -i \[entrée\]"):</span> <span
> class="notranslate">
> <https://crashes.fuzzing-project.org/rpm-heap-oob-read-headerVerifyInfo.rpm></span>
> <span class="notranslate"> Git commit:</span> <span
> class="notranslate">
> [https://github.com/rpm-software-management/rpm/commit/8e847d52c811e9a57239e18672d40f781e0ec48e](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=https://github.com/rpm-software-management/rpm/commit/8e847d52c811e9a57239e18672d40f781e0ec48e&usg=ALkJrhgXrBng_v9TC8orlX9SfJi3rOIwGQ)</span>
> <span class="notranslate"> accès pointeur Null / segfault dans
> StringFormat () / formats.c</span> <span class="notranslate"> Exemple
> de fichier (test avec "rpm -i \[entrée\]"):</span> <span
> class="notranslate">
> <https://crashes.fuzzing-project.org/rpm-nullptr-rpmtdFormat.rpm></span>
> <span class="notranslate"> Git commit:</span> <span
> class="notranslate">
> [https://github.com/rpm-software-management/rpm/commit/cddf43a56f19711866371f02f378dc4095b0fadd](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=https://github.com/rpm-software-management/rpm/commit/cddf43a56f19711866371f02f378dc4095b0fadd&usg=ALkJrhiyC-d-E-SBJkzz3_nC0B2x8uEAtQ)</span>
> <span class="notranslate"> Hors limites lu dans rpmtdGetNumber () /
> rpmtd.c</span> <span class="notranslate"> Exemple de fichier (test
> avec "rpm -qi -p - \[entrée\]")</span> <span class="notranslate">
> <https://crashes.fuzzing-project.org/rpm-heap-oob-read-rpmtdGetNumber.rpm></span>
> <span class="notranslate"> Git commit:</span> <span
> class="notranslate">
> [https://github.com/rpm-software-management/rpm/commit/b722cf86200505b3e3fcbb2095c4ff61f1f5a2ab](https://translate.googleusercontent.com/translate_c?depth=1&hl=fr&prev=search&rurl=translate.google.fr&sl=en&u=https://github.com/rpm-software-management/rpm/commit/b722cf86200505b3e3fcbb2095c4ff61f1f5a2ab&usg=ALkJrhi-yqWy6tCandzdbn4LVZIzJvYLjw)</span>
> <span class="notranslate"> Enfin une chose gênant d'admettre: Dans mon
> rapport original j'ai inclus une autre segfault dans headerVerifyInfo
> () avec des raisons obscures.</span> <span class="notranslate">
> Cependant, je suis désormais incapable de reproduire celui-ci.</span>
> <span class="notranslate"> Il peut être dû au compilateur options,
> différents paramètres ou des dépendances de ligne de commande sur mon
> système qui ont changé.</span> <span class="notranslate"> Pour être
> complet, je suis toujours fournir le fichier de l'échantillon:</span>
> <span class="notranslate">
> <https://crashes.fuzzing-project.org/rpm-segfault-headerVerifyInfo.rpm></span>
> <span class="notranslate"> (Idéalement, les développeurs de RPM
> devraient inclure tous les exemples de fichiers dans une suite de test
> qu'ils passent régulièrement contre une adresse assainisseur
> construction de RPM.)</span> <span class="notranslate"> S'il vous
> plaît note également que je pense que cette liste soit incomplète et
> il y a probablement plus de questions qui pourraient être découverts
> avec plus fuzzing.</span> <span class="notranslate"> Je vais tester
> qu'une fois tous les problèmes existants sont fixés.</span>
>
> </div>

<div class="clearfix content serendipity_entry_body">

Bon comme je l'ai dis, c'est du google traduction, mais c'est assez
clair pour comprendre les grandes lignes, dont une qui me fait tiquer:

</div>

> <div class="clearfix content serendipity_entry_body">
>
> <span class="notranslate">"Merci pour le rapport.</span> <span
> class="notranslate"> Nous avons également reçu au sujet de 30 rapports
> d'erreur dans RPM de</span> <span class="notranslate"> un journaliste
> différent récemment, donc le traitement de chacun d'eux (le vôtre et
> le</span> <span class="notranslate"> autres) vont prendre un peu de
> temps.</span> <span class="notranslate"> Nous ne disposons tout
> simplement les ressources</span> <span class="notranslate"> de passer
> des heures et des heures à analyser tous les rapports d'erreur
> ".</span>
>
> </div>

<div class="clearfix content serendipity_entry_body">

Comment redhat peut balancer de tels propos quand on sait que Debian a
gentiment corrigé dans la semaine et je suppose en remerciant le rapport
du gars. Comment une société qui a comme business modèle une
distribution sécurisé peut dire de telle âneries?

</div>

<div class="clearfix content serendipity_entry_body">

Ce qui me choque aussi c'est le coté bordélique des distributions linux
dont celles basé sur RPM et leur bugzilla, je trouve qu'il y a une
meilleur approche avec le reportbug de Debian qu'avec un bugzilla, avec
[reportbug](https://wiki.debian.org/fr/reportbug) on se sent plus
impliqué et surtout plus proche des développeurs, c'est du reste pas
plus compliqué si on est sur une debian puisque celle ci nous aide dans
la démarche et que celle ci est faisable de plusieurs façons et par
plusieurs moyens, on peut le faire via la console en ncurse, via une
interface gtk ou via par mail.

</div>

<div class="clearfix content serendipity_entry_body">

De ce que je connais de bugzilla, c'est vrai que c'est simple, mais les
doublons se fait très facilement la ou reportbug vérifie et nous montre
ceux qui peuvent coïncider avec le notre.

</div>

<div class="clearfix content serendipity_entry_body">

Mais la question n'est pas la, d'un coté on a un modèle communautaire
avec Debian qui fait le taff sans se plaindre de l'autre une entité
commerciale et a but lucratif qui se fait de la tune, qui dit qu'ils
n'ont pas assez de moyens, en gros ils ont les moyens pour faire des
doublons avec des outils comme
[DNF](https://fr.wikipedia.org/wiki/Dandified_Yum) (pourquoi ne pas
avoir pris
[zypper](https://fr.wikipedia.org/wiki/OpenSUSE#Ligne_de_commande_Zypper)
de suse?) et d'autres développement que Cascador nous parle bien mieux
que moi dans son billet [L’innovation du côté de chez Red
Hat](https://www.blog-libre.org/2016/04/02/linnovation-du-cote-de-chez-red-hat/)
mais n'a pas les moyens de mettre une personne sur la sécurité de
l'outil de bas niveau mais qui se charge de tout au niveau des paquets?

</div>

<div class="clearfix content serendipity_entry_body">

Je ne suis pas un fan des redhat et consorts, je préfère de loin le
monde de debian. Je trouve notamment que Redhat avec tout le bien qu'il
apporte dans le logiciel opensource, est trop directive, considérant les
besoins des utilisateurs de leurs systèmes gratuits ou même leurs avis
comme moins important que les leurs. Aussi je pense qu'on est des rats
de laboratoire pour eux, faut dire que les peu de contactes que j'ai eu
avec Fedora m'ont bien refroidis et je garde une mauvaise image surtout
de leur kde, dont les devs principaux ne sont pas non plus content du
manque de moyens pour cet environnement(allez chez opensuse). Je suis
plus suse, je les trouve déjà plus libertaire, plus soucieux des
utilisateurs de leur système gratuits qu'est opensuse, plus a l’écoute.

</div>

<div class="clearfix content serendipity_entry_body">

</div>

<div class="clearfix content serendipity_entry_body">

Bon j'ai réparé mes erreurs, il ne reste plus qu'a citer mes sources:

</div>

<div class="clearfix content serendipity_entry_body">

<https://blog.fuzzing-project.org/52-Multiple-vulnerabilities-in-RPM-and-a-rant.html>

</div>

<div class="clearfix content serendipity_entry_body">

<https://lwn.net/Articles/698453/>

</div>
