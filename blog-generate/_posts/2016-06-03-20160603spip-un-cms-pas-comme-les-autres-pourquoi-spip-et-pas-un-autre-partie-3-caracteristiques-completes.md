---
title: SPIP, un cms pas comme les autres... Pourquoi SPIP et pas un autre ? 3, Caractéristiques complètes
date: 2016-06-03 11:37
layout: post
---

<div class="texte surlignable">

### Installation {#outil_sommaire_0 .spip}

L’installation de SPIP est particulièrement simplifiée par rapport à
d’autres systèmes :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Aucune connaissance technique particulière n’est
nécessaire (ni PHP, ni MySQL) pour procéder à son installation.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} La configuration se fait directement en ligne, au
travers d’une interface graphique très simple (il n’est pas nécessaire,
en particulier, d’aller modifier un fichier de configuration avec des
codes abscons).
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Nous distribuons une version unique de SPIP ;
celle-ci peut évoluer au cours du temps en fonction des améliorations,
mais nous faisons très attention à ne pas compliquer en développant des
« patches » qu’il faudrait aller chercher à droite ou à gauche (pour
adapter SPIP à tel hébergeur par exemple).

![](http://www.spip.net/local/cache-vignettes/L520xH303/31-install_droits-acces-dd7d7.png)

![](http://www.spip.net/local/cache-vignettes/L520xH374/41-install-connexion-sqlite-da180.png)

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L520xH627/51-install-c71df-a8cd0.png?1464953422){width="520"
height="627"}

[voir Installation de
SPIP](http://passiongnulinux.tuxfamily.org/spip/spip.php?article213){.spip_in}
et [Installation de
SPIP3](http://passiongnulinux.tuxfamily.org/spip/spip.php?article216){.spip_in}  
<!--more-->

### Site public {#outil_sommaire_1 .spip}

Le site public fabriqué à partir de SPIP offre les caractéristiques
suivantes :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Interface entièrement adaptable par le webmestre
sans connaissances de PHP ni de MySQL ; l’interface de SPIP se programme
en HTML, auquel nous avons ajouté un langage relativement simple ; SPIP
n’impose donc pas une mise en page rigide.  

> L’interface en HTML classique n’est pas la seule forme de navigation
> que l’on peut présenter aux visiteurs du site. Les mêmes informations
> (le même contenu) peuvent être présentées dans des formats très
> différents. On peut par exemple fournir, en plus de la navigation Web
> classique :
> ![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
> width="8" height="11"} des fils de syndication au format XML/RSS,
> ![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
> width="8" height="11"} un calendrier au format iCalendar,  
> et tout autre format que l’on se donnera le mal de maîtriser (XML,
> JSON, YAML...).
> </p>

![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} SPIP intègre un système de cache pour chaque page
individuelle : les pages sont calculées (à partir des informations de la
base de données) individuellement, et stockées dans un fichier de
cache ; ainsi le serveur n’est pas ralenti par un trop grand nombre
d’appels MySQL, et le site est toujours accessible même en cas de panne
du serveur de bases de données.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} SPIP intègre un petit moteur de recherche basé
sur un système d’indexation par mots.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} SPIP dispose d’un module de compression des
scripts javascript et feuilles de style CSS qui permettent d’optimiser
la vitesse de rendu de la page.  

### La structure du site {#outil_sommaire_2 .spip}

La structure d’un site sous SPIP est construite sur une hiérarchie de
rubriques. Il n’y a virtuellement pas de limite au nombre de rubriques :
une rubrique peut contenir autant de sous-rubriques que nécessaires, qui
elles-mêmes contiennent des sous-rubriques, etc. On construit ainsi la
structure de son site en imbriquant des rubriques et des
sous-rubriques.  

### Les articles {#outil_sommaire_3 .spip}

L’objet principal permettant de publier des informations sous SPIP est
l’article. On peut placer autant d’articles que nécessaire, dans
n’importe quelle rubrique.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} La rédaction des articles est très simple, elle
se déroule via une interface graphique sur le Web.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Un article est constitué de plusieurs éléments
qui permettent de le structurer : titre, surtitre, soustitre,
descriptif, chapeau, texte principal, post-scriptum.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Les règles de base de la typographie française
sont appliquées automatiquement (espaces insécables avant les points
d’interrogation, d’exclamation, etc.).
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Des raccourcis mnémotechniques facilitent
l’enrichissement typographique, la création de liens hypertexte, de
notes de bas de page... mettre en page un article sous SPIP est aussi
facile que d’écrire un email.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} L’interface graphique permet d’inclure simplement
des images dans les articles, et chaque article peut être signalé par
son propre logo.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} On peut indiquer, pour chaque article, un ou
plusieurs mots-clés.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} La date de mise en ligne se gère automatiquement
(on peut cependant la modifier si nécessaire) ; une seconde date peut
être associée à un article, par exemple pour indiquer une date de
publication originale (par exemple, un article publié antérieurement
dans un magazine papier).
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Redirections (articles « fantômes ») : SPIP
permet de fabriquer des articles-fantômes, intégrés dans la structure du
site et affichés dans le contenu des rubriques, mais qui en réalité
renvoient vers une page dont l’adresse est spécifiée par le rédacteur
(sur le même site, ou même sur un autre site). Cette fonction facilite
le passage d’un site déjà existant vers SPIP, par l’intégration de
contenus statiques préexistants.  

### Les forums {#outil_sommaire_4 .spip}

SPIP intègre un système de forums.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Les forums peuvent être associés aux articles (un
forum par article), aux rubriques ou aux brèves. Le webmestre pourra
programmer son interface pour que chaque article dispose de son propre
forum, ou pour que plusieurs articles d’une même rubrique partagent le
même forum, etc.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} SPIP permet de choisir entre plusieurs layouts de
forums : les forums « libres » (modérés à postériori, les contributions
apparaissent immédiatement, les administrateurs peuvent éventuellement
supprimer ensuite un message indésirable) ; les forums modérés à priori
(les contributions n’apparaissent qu’après avoir été validées par un
administrateur du site) ; les forums sur abonnement (chaque intervenant
doit, pour pouvoir poster, d’abord indiquer son adresse email pour
recevoir un mot de passe lui permettant de poster ses contributions).
SPIP intègre également un système de forums privés, consacré à la
discussion entre les différents rédacteurs du site, et cela dans
l’espace privé.  

### Les pétitions {#outil_sommaire_5 .spip}

Un article peut être transformé en pétition en ligne en quelques clics.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Les pétitions de SPIP sont validées par email
automatiquement : un signataire reçoit un message de confirmation qui
permet de vérifier la validité des signatures.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} On peut configurer très simplement le layout de
pétition : ainsi imposer une seule signature par adresse email, imposer
qu’un site Web soit indiqué dans la pétition (dans ce cas, la validité
de l’URL est vérifiée automatiquement), accepter ou non des messages
accompagnant les signatures.  

### Les statistiques {#outil_sommaire_6 .spip}

SPIP intègre un système très simplifié de statistiques, permettant
d’évaluer la popularité des articles et des rubriques.  

### Les rédacteurs/administrateurs {#outil_sommaire_7 .spip}

Un site sous SPIP peut être géré par une seule personne, ou être réalisé
par un groupe de rédacteurs.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} SPIP propose deux niveaux d’accès : les
administrateurs, qui gèrent notamment la structure du site et la
validation des articles, et les rédacteurs, qui proposent des articles.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Le nombre de rédacteurs et d’administrateurs est
illimité.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} On peut décider d’offrir aux utilisateurs du site
public de s’inscrire pour devenir rédacteur (la procédure d’inscription
est alors gérée automatiquement par SPIP).
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Chaque auteur peut se voir associer un logo
personnel téléchargeable depuis l’interface (par exemple une photo
d’identité).  

### Syndication {#outil_sommaire_8 .spip}

Les sites réalisés sous SPIP, wordpress, ou d’autres systèmes,
fournissent un fichier dynamique indiquant leurs dernières publications.
SPIP peut analyser de tels fichiers et ainsi indiquer les nouveautés
d’autres sites :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} on peut ajouter autant de sites syndiqués que
l’on veut ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} les sites syndiqués sont associés aux rubriques
de son propre site ; ainsi, on peut associer à une rubrique thématique
les liens vers des sites traitant du thème précis de la rubrique.  

### Interface graphique du site public {#outil_sommaire_9 .spip}

L’interface graphique du site public est très souple. Grâce à un langage
très simple (mais propre à SPIP), on peut réaliser à peu près n’importe
quelle interface graphique. Il n’est en particulier pas nécessaire de
connaître PHP et MySQL pour réaliser une interface graphique originale
sous SPIP.  

### Interface du site privé {#outil_sommaire_10 .spip}

La partie privée qui permet de gérer le site dispose d’une interface
graphique complète, très simple d’utilisation.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Cette interface s’adapte en fonction des
activités de chaque rédacteur ou administrateur, et en fonction de
l’activité du site. Ainsi chaque auteur a-t-il accès rapidement à ses
propres articles, et les articles proposés à la publication sont
signalés à tous les utilisateurs. De même l’interface est différente
selon que l’on est rédacteur ou administrateur.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Chaque utilisateur peut personnaliser son
interface. Il peut choisir entre une interface simplifiée, qui n’offre
que les fonctions principales, et une interface complète. Il peut
également modifier quelque peu l’habillage graphique de l’interface.
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} Lorsqu’un site accueille plusieurs rédacteurs,
SPIP devient un outil de travail coopératif : débats autour des
articles, système de validation, travail à plusieurs sur un même
article...  

### Paramétrage du site {#outil_sommaire_11 .spip}

Si l’interface graphique du site public et la gestion du contenu sont,
dans SPIP, strictement séparées (par exemple, on ne fixe pas la couleur
du fond d’écran du site public dans l’espace privé), il est cependant
possible de configurer certains comportements du site dans l’espace
privé :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} accepter ou refuser certains éléments du contenu
des articles : ainsi on peut décider d’interdire l’utilisation des
surtitre, soustitre, descriptif, chapeau ou post-scriptum, ou la date de
publication antérieure et les mots-clés ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} configurer (ou désactiver) les forums publics ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} indiquer si l’on publie les articles avant la
date de publication qu’on leur a fixé (cette option permet par exemple
de partir en vacances, le site publiant des articles pendant cette
absence) ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} désactiver le système de brèves (en effet,
certains sites n’en ont pas l’usage ; les désactiver permet de
simplifier l’interface pour les rédacteurs) ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} activer ou désactiver les statistiques ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} activer ou désactiver le moteur de recherche.  

### Suivi éditorial {#outil_sommaire_12 .spip}

Afin de faciliter le suivi éditorial du site, plusieurs options sont
offertes :
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} envoi des contributions des forums aux auteurs
des articles ; lorsqu’un visiteur du site poste un message sous un
article, l’auteur de cet article en est informé par mail, ce qui lui
permet de suivre l’activité de son article par mail ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} suivi de l’activité éditoriale ; si le site est
le fruit d’une équipe de rédacteurs, on peut signaler automatiquement
les annonces importantes de l’activité éditoriale à une adresse email
(dans l’idéal, une liste de de diffusion) ; ainsi, lorsqu’un article est
publié ou proposé à la publication, cette liste en est informée ;
![-](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L8xH11/puce-32883.gif?1464929828){.puce
width="8" height="11"} annonce des nouveautés ; SPIP peut envoyer
automatiquement, selon une fréquence fixée par les administrateurs, un
courrier électronique recensant les dernières publications sur le site.  

### Sauvegarde et exportation de la base de données {#outil_sommaire_13 .spip}

Le webmestre du site peut réaliser une sauvegarde de sa base de données
(un fichier est alors créé) ; si le serveur le permet, cette sauvegarde
sera réalisée dans un fichier compressé, facilitant ainsi sa
récupération par FTP. SPIP intègre bien entendu la fonction qui permet
d’importer un tel fichier.  

### Plugins {#outil_sommaire_14 .spip}

Les fonctions de SPIP peut être étendus par des plugins. Les
installations et mises à jour de ces plugins se fait directement depuis
l’espace privé. Il est aussi possible d’écrire assez simplement ses
propres plugins pour ajouter des objets éditoriaux à son site.  

### Révisions {#outil_sommaire_15 .spip}

SPIP dispose d’un module de révisions qui permet de consulter
l’historique des modifications d’un objet éditorial. On peut donc
facilement visualiser les ajouts, retraits et contributions des
rédacteurs sur un article ou tout autre objet éditable.  

### Choix des URLs {#outil_sommaire_16 .spip}

Sur les serveurs compatibles, SPIP permet de choisir le format des
adresses du site public. Ces URLs peuvent être éditables ou
personnalisées.  

### Captures d’écran {#outil_sommaire_17 .spip}

Voici quelques captures d’écran de l’espace privé de SPIP pour avoir un
aperçu des fonctionnalités. Les couleurs sont modifiables. **La page de
suivi du site**

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L520xH838/spip_page_sua992-a89f4.png?1464953422){width="520"
height="838"}

**L’interface d’édition d’un article**

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L520xH859/spip_page_ed7ae0-42950.png?1464953422){width="520"
height="859"}

**Le forum interne**

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L520xH528/spip_page_fo42ff-46f4f.png?1464953422){width="520"
height="528"}

**La comparaison des versions d’un article**

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L520xH564/spip_page_re56c8-74f80.png?1464953422){width="520"
height="564"}

**Le moteur de recherche**

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L520xH498/spip_page_re962e-a4a30.png?1464953422){width="520"
height="498"}

**Les statistiques**

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L520xH720/spip_page_st80be-71d4c.png?1464953422){width="520"
height="720"}

**La navigation dans le site**

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L520xH360/toutsite-a30e5ce-7968d.png?1464953422){width="520"
height="360"}

**Le mode texte**

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L279xH367/mode-texte-75923-3c065.png?1464953422){width="279"
height="367"}

</div>

Voir en ligne : [Caractéristiques
complètes](http://www.spip.net/fr_article890.html){.spip_out}
