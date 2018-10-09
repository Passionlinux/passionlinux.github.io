---
title: Ubuntu part seul dans l'espace avec MIR
date: 2013-07-21 19:07
layout: post
---

<div class="main">

<div class="texte surlignable">

Et voila, ubuntu fait encore parler d’elle !  
Cette fois, on critique son choix sur le fait de choisir autre chose que
les autres acteurs du libre pour remplacer xorg. Voila ce qu’on peut
lire sur linuxfr.org :  
> Le monde du Libre s’est appuyé pendant de longues années sur le
> serveur d’affichage X Window System. Le protocole X date de 1984 et,
> en dépit de nombreuses extensions, il commence à montrer son âge. De
> nombreuses critiques ont été émises sur le caractère impénétrable de
> son code, sur son modèle de sécurité inexistant et sur son
> inadaptation aux machines modernes. Depuis 2008, un remplaçant
> répondant au nom de Wayland est développé par Kristian Høgsberg et de
> nombreux autres contributeurs. Ce nouveau protocole se débarrasse de
> tous les résidus accumulés par X au fil des années, et il propose une
> solution moderne et optimisée (voir cet article LWN qui explique les
> enjeux et cette vidéo de Daniel Stone à la conférence LCA 2013). Il
> est important de noter que les développeurs de Wayland sont souvent
> d’anciens développeurs X.Org (Stone est un bon exemple) qui ont donc
> une connaissance poussée des limitations du serveur X et une expertise
> suffisante pour jauger les qualités de Wayland. NdM : merci à
> patrick\_g pour son journal. Journal à l’origine de la dépêche (272
> clics)  
> Mir sur le wiki Ubuntu (254 clics)  
> Wayland — site officiel (213 clics)  
> Ubuntu Building Own Display Server, Unity To Switch to Qt/QML (OMG
> Ubuntu) (80 clics)  
> Canonical : les fouteurs de merde, le retour — un autre journal sur le
> sujet (497 clics) Après plusieurs années de développement (et de
> concertation), la première version stable 1.0 de Wayland est sortie en
> octobre dernier, et le futur des serveurs d’affichage libres semblait
> alors tout tracé. Après une phase de transition plus ou moins longue
> (le temps d’adapter les bibliothèques graphiques à Wayland), nous
> allions tous basculer vers ce nouveau protocole moderne et efficace.
> Bien entendu, comme pour de nombreuses autres briques du système, les
> machines sous Android utilisent une solution d’affichage spécifique
> (nommée SurfaceFlinger). On peut penser que Google a voulu un système
> optimisé pour les téléphones et sur lequel il pouvait avoir la main
> sans être obligé de collaborer avec la communauté. La situation future
> de l’affichage dans le monde Linux semblait donc claire :
> SurfaceFlinger pour les machines sous Android, et Wayland pour les
> systèmes GNU/Linux traditionnels. C’est pour ça que l’annonce de
> Canonical du développement de Mir, un tout nouveau remplaçant pour
> X.Org, a surpris et irrité de nombreux observateurs. Canonical désire
> faire converger ses projets afin d’avoir une pile unifiée pour les
> machines de bureau et les smartphones. Selon cette société, X.Org et
> Wayland ne sont pas adaptés à cette convergence et il était nécessaire
> de créer un nouveau protocole.  
> Dans le wiki dédié à Mir, certaines critiques étaient avancées sur
> Wayland, notamment la sécurité de Wayland y était critiquée, car la
> gestion des évènements était considéré comme semblable à celle de X et
> donc souffrait des mêmes problèmes de sécurité. Aux yeux des
> développeurs de Wayland, cette justification semble grotesque. Une
> discussion a immédiatement commencé sur le compte Google+ de Kristian
> Høgsberg, et les critiques pleuvent. Selon Daniel Stone la
> justification avancée est complètement fausse (et l’auteur du texte
> employé par Canonical n’a même pas pris la peine de se renseigner
> auprès des développeurs Wayland). En fait, dans Wayland (contrairement
> à X), les évènements en entrée sont envoyés à un seul client et les
> clients ne peuvent pas réémettre d’évènement. Donc, un client
> « pirate » qui détournerait les évènements en mettant une fenêtre
> transparente en plein écran ferait que les clients normaux ne
> reçoivent plus rien, ce qui est facile à voir… Kristian Høgsberg a
> également souligné l’absurdité des arguments : The things they claim
> wayland/weston input can’t be extended to support \[…\] is already
> implemented and working in weston today… « Selon eux, Wayland et
> Weston ne peuvent soi?disant pas gérer certaines entrées \[…\] qui
> sont pourtant déjà implémentées et fonctionnent dans Weston à ce
> jour… » Carsten Haitzler (le Rasterman du projet Enlightenment) est
> également très critique : A reads of the Mir stuff says to me “Oh,
> look. We don’t understand Wayland at all, neither do we grok X11 that
> much either.” Their reasoning on the input in Wayland are just total
> bunk. I would just say “ignore Mir/Canonical and just keep plodding on
> with Wayland.” « Une lecture des trucs sur Mir me fait dire : “Oh,
> écoute, on ne comprend rien à Wayland et on ne capte pas beaucoup X11
> non plus.” Leur raisonnement sur la gestion des entrées dans Wayland
> est tout simplement faux. Je dirais juste : “ignorons Mir/Canonical et
> continuons de travailler avec Wayland.” » Dave Airlie (développeur
> noyau pour les pilotes graphiques) souligne l’amateurisme que révèle
> ce projet : They barely have anyone competent enough to write a
> display server, the fact that they are actually quite ignorant of how
> Wayland works makes it even more apparent. « Ils n’ont quasiment
> personne de suffisamment compétent pour écrire un serveur d’affichage,
> leur ignorance du fonctionnement de Wayland le met d’autant plus en
> évidence. » Dave a également posté sur son blog au sujet du projet
> Mir : Now the question becomes : do you want the display server that
> you are going to base the future of the Linux desktop and possible
> mobile spaces on a server written by people too stupid to understand
> the current open source project in the space ? The thing is putting
> stuff on the screen really isn’t the hard part of display servers,
> getting input to where it needs to go is, and making it secure. Input
> methods are hard, input is hard, guess what they haven’t even
> contemplated implementing yet ? « La question est de savoir si vous
> souhaitez que l’avenir de Linux sur le bureau et potentiellement sur
> les plates?formes mobiles repose sur un serveur d’affichage qui est
> développé par des personnes incapables de comprendre la solution libre
> de référence? ? Le fait est que ce n’est pas afficher des choses à
> l’écran qui est la partie compliquée d’un serveur d’affichage? ;
> récupérer les entrées et les envoyer de manière sécurisée à leur
> destination, ça c’est difficile. Gérer les méthodes d’entrées est
> difficile, un système d’entrée est difficile. Devinez ce qu’ils n’ont
> pas encore envisagé d’implémenter? ? » Cette volée de bois vert
> générale s’explique par plusieurs facteurs. Tout d’abord, des grosses
> erreurs dans la description du fonctionnement de Wayland ont irrité
> beaucoup de monde. Et le fait que ce projet Mir soit en cours depuis
> plusieurs mois (comme le révèle l’analyse de l’arbre Bazaar) ne
> présage rien de bon quant au degré d’ouverture de Canonical. Pourquoi
> avoir ainsi travaillé en secret? ? En outre, comme c’est souvent le
> cas avec Canonical, toutes les contributions extérieures devront
> passer par un partage du droit d’auteur (Contributor License
> Agreement). Cela signifie que Canonical aura le droit de changer la
> licence de vos contributions et d’inclure votre code dans un produit
> propriétaire. Enfin, le projet Mir est vu comme un risque de
> fragmentation inutile du monde du Libre. Alors que Wayland semblait
> être la solution consensuelle sur laquelle tout le monde allait se
> rallier, l’apparition d’un projet concurrent, s’appuyant sur des
> justifications techniques douteuses et étant financé par une seule
> société, ne peut que diviser les forces. Suite à une discussion sur
> IRC entre un développeur de Mir et les développeurs de Wayland, le
> wiki sur Mir a été modifié, ce qui devrait apaiser les tensions :
> Kristian Høgsberg, s’il regrette le manque de discussion préalable,
> était surtout irrité par les critiques infondées listées sur le wiki
> de Mir. Nous verrons dans les prochains mois si le projet de Mark
> Shuttleworth se révèle être une bonne idée. Dans l’intervalle, on peut
> sortir le pop?corn et regarder les trolls se déchaîner? !
> </p>

<p>
Les reactions s’enchainent, sur ce site mais pas seulement, sur tout les
sites linuxiens et meme sur ubuntu.fr, on s’interroge ou on critique !
Alors je vais faire l’avocat du diable, car plusieurs points n’ont pas
été pris en compte.  
Deja ubuntu va etre porté sur tv, téléphone, ordi et tablette, le tout
pour eviter la surcharge de travail, doit etre homogéne et donc etre le
« meme produit » sur toute ses surface.  
Canonical doit donc etre « maitre » de ses faits et gestes or si les
échanges avec Wayland se passe comme avec l’équipe gnome, rien de bon en
sortira ! Ensuite un concurrent a Wayland est plutot rassurant, les deux
vont vouloir etre le meilleur, et cette concurrence est bonne pour
l’utilisateur final !

</div>

Voir en ligne : [X Mir, un serveur d’affichage de
trop? ?](http://linuxfr.org/news/mir-un-serveur-d-affichage-de-trop){.spip_out}

</div>
