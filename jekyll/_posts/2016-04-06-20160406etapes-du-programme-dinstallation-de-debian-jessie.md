---
title: Étapes du programme d'installation de Debian Jessie
date: 2016-04-06 19:46
layout: post
---

<div>

<div>

### 4.2.1. Exécution du programme d'installation

</div>

<div>

Dès que le BIOS a lancé l'amorçage sur le CD-Rom (ou le DVD-Rom), le
menu du chargeur d'amorçage Isolinux apparaît. À ce stade, le noyau
Linux n'est pas encore chargé ; ce menu permet justement de choisir le
noyau à démarrer et de saisir d'éventuelles options à lui passer.

</div>

<div>

Pour une installation standard, il suffit de sélectionner (avec les
touches flèches) Install ou Graphical install, puis d'appuyer sur la
touche Entrée pour enchaîner sur la suite de l'installation. Si le
DVD-Rom est de layout « Multi-arch » et si la machine dispose d'un
processeur 64 bits de Intel ou AMD, des entrées de menu 64 bit install
et 64 bit graphical install permettent d'installer la variante 64 bits
(amd64) au lieu de celle par défaut (i386 en 32 bits). Dans la pratique,
la variante 64 bits peut être utilisée de manière quasi systématique :
les processeurs récents fonctionnent tous en 64 bits et cette variante
gère mieux les grosses quantités de mémoire vive dont disposent les
ordinateurs récents.

</div>

<div>

<div>

POUR ALLER PLUS LOIN 32 ou 64 bits ?

</div>

 

<div>

La différence fondamentale entre les systèmes 32 et 64 bits est la
taille des adresses mémoire. En théorie, un système 32 bits ne peut
exploiter plus de 4 Go de mémoire vive (232 octets). En pratique, il est
possible de contourner cette limite en utilisant la variante 686-pae du
noyau à condition que le processeur gère la fonctionnalité PAE (Physical
Address Extension). Son usage a toutefois un impact non négligeable sur
les performances du système. C'est pourquoi un serveur disposant d'une
grande quantité de mémoire vive a tout intérêt à exploiter le mode 64
bits.

</div>

<div>

Pour un poste bureautique (où quelques pour cent de performance sont
négligeables), on sera plus sensible au fait que certains logiciels
propriétaires ne sont pas disponibles en version 64 bits (Skype par
exemple). Il est techniquement possible de les faire fonctionner sur le
système 64 bits, mais il faudra installer les versions 32 bits de toutes
les bibliothèques nécessaires (voir [Section 5.4.5, « Support
multi-architecture »](https://debian-handbook.info/browse/fr-FR/stable/sect.manipulating-packages-with-dpkg.html#sect.multi-arch))
et éventuellement faire usage de setarch ou linux32 (dans le paquet
util-linux) pour tromper les applications sur la nature du système.
[](){#idm140363015746304} [](){#idm140363015745504}

</div>

</div>

<div>

<div>

EN PRATIQUE Installation à côté d'un Windows existant

</div>

 

<div>

Si l'ordinateur fonctionne déjà sous Windows, il n'est pas nécessaire de
supprimer ce système pour installer Debian. On peut en effet disposer
des deux systèmes à la fois, chacun installé sur un disque ou une
partition, et choisir lequel lancer au démarrage de l'ordinateur. Cette
configuration est souvent appelée dual boot et le système d'installation
de Debian peut tout à fait la mettre en place. Elle intervient lors de
la phase de partitionnement du disque dur et lors de la mise en place du
chargeur de démarrage (voir les encadrés [EN PRATIQUE Réduire une
partition
Windows](https://debian-handbook.info/browse/fr-FR/stable/sect.installation-steps.html#sidebar.shrinking-partition)
et [ATTENTION Chargeur d'amorçage et
dual boot](https://debian-handbook.info/browse/fr-FR/stable/sect.installation-steps.html#sidebar.bootloader-dual-boot)).

</div>

<div>

Si l'on a déjà un Windows fonctionnel, on pourra même se passer de la
récupération des CD-Rom ; Debian propose un programme Windows permettant
de télécharger un installateur Debian allégé et de le mettre en place
sur le disque dur. Il suffit alors de redémarrer l'ordinateur pour
choisir entre le lancement normal de Windows et celui du programme
d'installation. On le trouve également sur un site web dédié au nom
plutôt explicite…
<div>

? <http://ftp.fr.debian.org/debian/tools/win32-loader/stable/>

</div>

<div>

? <http://www.goodbye-microsoft.com/>

</div>

</div>

</div>

<div>

<div>

B.A.-BA Chargeur d'amorçage

</div>

 

<div>

Le chargeur d'amorçage (ou de démarrage), bootloader en anglais, est un
programme de bas niveau chargé de démarrer le noyau Linux juste après
que le BIOS lui a passé la main. Pour mener cette mission à bien, il
doit être capable de « retrouver » sur le disque le noyau Linux à
démarrer. Sur les architecture amd64 et i386, les deux programmes les
plus employés pour effectuer cette tâche sont LILO, le plus ancien, et
GRUB, son successeur plus moderne. Isolinux et Syslinux sont des
alternatives souvent employées pour démarrer depuis des supports
amovibles.

</div>

</div>

<div>

Derrière chaque entrée de menu se cache une ligne de commande de
démarrage spécifique que l'on peut personnaliser au besoin en appuyant
sur TAB avant de valider et démarrer. L'entrée de menu Help fait
apparaître l'ancienne interface en ligne de commande où les touches F1 à
F10 affichent différents écrans d'aide détaillant les options possibles
à l'invite. Sauf exceptions, vous n'aurez normalement pas besoin de vous
servir de cette possibilité.

</div>

<div>

Le mode « expert » (accessible dans le menu Advanced options, « Options
avancées ») détaille toutes les options possibles au cours de
l'installation et permet de naviguer entre les différentes étapes sans
qu'elles s'enchaînent automatiquement. Attention, ce mode très verbeux
pourra dérouter par la multitude des choix de configuration qu'il
propose.

</div>

<div>

 
<div>

<div>

![Écran de
démarrage](https://debian-handbook.info/browse/fr-FR/stable/images/inst-boot.png)

</div>

</div>

Figure 4.1. Écran de démarrage

</div>

<div>

Une fois démarré, le programme d'installation nous guide d'étape en
étape tout au long du processus. Cette section détaille chacune d'entre
elles, leurs tenants et leurs aboutissants. Nous suivons le déroulement
correspondant à un DVD-Rom Multi-Arch (plus précisément, la version
beta4 de l'installateur de Jessie) ; les autres layouts d'installations
(netinst notamment) peuvent varier quelque peu. Nous allons également
nous concentrer sur l'installation en mode graphique, mais elle ne
diffère de l'installation « classique » que par l'aspect visuel.

</div>

</div>

<!--more-->  
<!--more-->

<div>

<div>

### [](){#sect.install-lang}4.2.2. Choix de la langue

</div>

 

<div>

Le programme d'installation débute en anglais mais la toute première
étape consiste à choisir la langue utilisée par la suite. Opter pour le
français fournira une installation entièrement traduite (et un système
configuré en français à l'issue du processus). Cela permettra également
de proposer des choix par défaut plus pertinents lors des étapes
suivantes (la disposition du clavier notamment).

</div>

<div>

<div>

B.A.-BA Naviguer grâce au clavier

</div>

<div>

Certaines étapes du processus d'installation nécessitent une saisie
d'informations. Ces écrans disposent alors de plusieurs zones qui
peuvent « avoir le focus » (zone de saisie de texte, cases à cocher,
liste de choix, boutons OK et Annuler), et la touche Tabulation permet
de circuler entre elles.

</div>

<div>

En mode graphique, on utilise la souris comme on l'utiliserait sur un
bureau graphique fonctionnel.

</div>

</div>

<div>

 
<div>

<div>

![Choix de la
langue](https://debian-handbook.info/browse/fr-FR/stable/images/inst-lang.png)

</div>

<div>

![Choix de la
langue](https://debian-handbook.info/browse/fr-FR/stable/images/inst-lang-txt.png)

</div>

</div>

Figure 4.2. Choix de la langue

</div>

</div>

<div>

<div>

### [](){#sect.install-country}4.2.3. Choix du pays

</div>

 

<div>

La deuxième étape consiste à choisir le pays. Combinée à la langue,
cette information permettra de proposer une disposition de clavier
encore plus adaptée. Elle influera aussi sur la configuration du fuseau
horaire. Dans le cas de la France, un clavier de layout AZERTY sera
proposé et le fuseau horaire sera Europe/Paris

</div>

<div>

 
<div>

<div>

![Choix du
pays](https://debian-handbook.info/browse/fr-FR/stable/images/inst-country.png)

</div>

<div>

![Choix du
pays](https://debian-handbook.info/browse/fr-FR/stable/images/inst-country-txt.png)

</div>

</div>

Figure 4.3. Choix du pays

</div>

</div>

<div>

<div>

### [](){#sect.install-keyboard}4.2.4. Choix de la disposition du clavier

</div>

 

<div>

Le clavier Français proposé convient pour les claviers AZERTY
traditionnels. Il prend en charge le symbole euro.

</div>

<div>

 
<div>

<div>

![Choix du
clavier](https://debian-handbook.info/browse/fr-FR/stable/images/inst-keyboard.png)

</div>

<div>

![Choix du
clavier](https://debian-handbook.info/browse/fr-FR/stable/images/inst-keyboard-txt.png)

</div>

</div>

Figure 4.4. Choix du clavier

</div>

</div>

<div>

<div>

### [](){#sect.install-detect-hardware}4.2.5. Détection du matériel

</div>

<div>

Cette étape est entièrement automatique dans la plupart des cas.
L'installateur détecte le matériel et cherche notamment à identifier le
lecteur de CD-Rom employé afin de pouvoir accéder à son contenu. Il
charge les modules correspondant aux différents éléments détectés, puis
« monte » le CD-Rom afin de pouvoir le lire. Les étapes précédentes
étaient entièrement contenues dans l'image de démarrage intégrée au
CD-Rom, fichier de taille limitée et chargé en mémoire par le BIOS lors
de l'amorçage du CD-Rom.

</div>

<div>

L'installateur gère l'immense majorité des lecteurs, en particulier les
périphériques ATAPI (parfois appelés IDE ou EIDE) standards. Toutefois,
si la détection du lecteur de CD-Rom échoue, l'installateur propose de
charger (par exemple depuis une clé USB) un module noyau correspondant
au pilote du CD-Rom.

</div>

</div>

<div>

<div>

### [](){#sect.install-load-components}4.2.6. Chargement des composants

</div>

<div>

Le contenu du CD-Rom désormais accessible, l'installateur rapatrie tous
les fichiers nécessaires à la poursuite de sa tâche. Cela comprend des
pilotes supplémentaires pour le reste du matériel (et notamment la carte
réseau) ainsi que tous les composants du programme d'installation.

</div>

</div>

<div>

<div>

### [](){#sect.install-detect-network}4.2.7. Détection du matériel réseau

</div>

<div>

Cette étape automatique cherche à identifier la carte réseau et à
charger le module correspondant. À défaut de reconnaissance automatique,
il est possible de sélectionner manuellement le module à charger. Si
aucun module ne fonctionne, il est possible de charger un module
spécifique depuis un périphérique amovible. Cette dernière solution ne
sert réellement que si le pilote adéquat n'est pas intégré au noyau
Linux standard s'il est disponible par ailleurs, par exemple sur le site
du fabricant.

</div>

<div>

Cette étape doit absolument réussir pour les installations de layout
netinst puisque les paquets Debian doivent y être chargés sur le réseau.

</div>

</div>

<div>

<div>

### [](){#sect.install-network-config}4.2.8. Configuration du réseau

</div>

 

<div>

Soucieux d'automatiser au maximum le processus, l'installateur tente une
configuration automatique du réseau par DHCP (pour IPv4) et par
découverte du réseau IPv6. Si celle-ci échoue, il propose plusieurs
choix : réessayer une configuration DHCP normale, effectuer une
configuration DHCP en annonçant un nom de machine, ou mettre en place
une configuration statique du réseau.

</div>

<div>

Cette dernière demande successivement une adresse IP, un masque de
sous-réseau, une adresse IP pour une éventuelle passerelle, un nom de
machine et un nom de domaine.

</div>

<div>

<div>

ASTUCE Configuration sans DHCP

</div>

<div>

Si le réseau local est équipé d'un serveur DHCP que vous ne souhaitez
pas utiliser car vous préférez définir une adresse IP statique pour la
machine en cours d'installation, vous pourrez lors du démarrage sur le
CD-Rom ajouter l'option netcfg/use\_dhcp=false. Il suffit de se placer
sur l'entrée de menu désirée, d'appuyer sur TAB et d'ajouter l'option
ci-dessus avant de valider par Entrée.

</div>

</div>

<div>

<div>

ATTENTION Ne pas improviser

</div>

<div>

Beaucoup de réseaux locaux reposant sur une confiance concédée a priori
à toutes les machines, une configuration inadéquate d'un ordinateur y
cause souvent des dysfonctionnements. Par conséquent, ne connectez pas
votre machine à un réseau sans convenir au préalable avec son
administrateur des modalités correspondantes (par exemple le numéro IP,
le masque réseau, l'adresse de broadcast...).

</div>

</div>

</div>

<div>

<div>

### [](){#idm140363027993472}4.2.9. Mot de passe administrateur

</div>

 

<div>

Le compte super-utilisateur root, réservé à l'administrateur de la
machine, est automatiquement créé lors de l'installation : c'est
pourquoi un mot de passe est demandé. Une confirmation (ou deuxième
saisie identique) évitera toute erreur de saisie, difficile à retrouver
ensuite !

</div>

<div>

 
<div>

<div>

![Mot de passe
administrateur](https://debian-handbook.info/browse/fr-FR/stable/images/inst-rootpw.png)

</div>

</div>

Figure 4.5. Mot de passe administrateur

</div>

<div>

<div>

SÉCURITÉ Mot de passe administrateur

</div>

<div>

Le mot de passe de l'utilisateur root doit être long (8 caractères ou
plus) et impossible à deviner. En effet, tout ordinateur (et a fortiori
tout serveur) connecté à Internet fait régulièrement l'objet de
tentatives de connexions automatisées avec les mots de passe les plus
évidents. Parfois, il fera même l'objet d'attaques au dictionnaire, où
diverses combinaisons de mots et de chiffres sont testées en tant que
mots de passe. Évitez aussi les noms des enfants ou parents et autres
dates de naissance : de nombreux collègues les connaissent et il est
rare que l'on souhaite leur donner libre accès à l'ordinateur concerné.

</div>

<div>

Ces remarques valent également pour les mots de passe des autres
utilisateurs, mais les conséquences d'une compromission sont moindres
dans le cas d'un utilisateur sans droits particuliers.

</div>

<div>

Si l'inspiration vient à manquer, il ne faut pas hésiter à utiliser des
générateurs de mot de passe comme pwgen (dans le paquet de même nom).

</div>

</div>

</div>

<div>

<div>

### [](){#idm140363027982480}4.2.10. Création du premier utilisateur

</div>

<div>

Debian impose également de créer un compte utilisateur standard pour que
l'administrateur ne prenne pas la mauvaise habitude de travailler en
tant que root. Le principe de précaution veut en effet que chaque tâche
soit effectuée avec le minimum de droits nécessaires, pour limiter
l'impact d'une mauvaise manipulation. C'est pourquoi l'installateur vous
demandera successivement le nom complet de ce premier utilisateur, son
identifiant et son mot de passe (deux fois, pour limiter les risques
d'erreur de saisie).

</div>

<div>

 
<div>

<div>

![Nom du premier
utilisateur](https://debian-handbook.info/browse/fr-FR/stable/images/inst-username.png)

</div>

</div>

Figure 4.6. Nom du premier utilisateur

</div>

</div>

<div>

<div>

### [](){#sect.install-clock-config}4.2.11. Configuration de l'horloge

</div>

<div>

Si le réseau est disponible, l'horloge interne du système est mise à
jour (de façon ponctuelle et instantanée) à l'aide d'un serveur NTP. Les
horodatages des logs seront ainsi précis dès le premier démarrage. Pour
qu'ils restent précis dans la durée, il faudra tout de même mettre en
place un démon NTP après l'installation initiale (voir [Section 8.9.2,
« Synchronisation
horaire »](https://debian-handbook.info/browse/fr-FR/stable/sect.config-misc.html#sect.time-synchronization)).

</div>

</div>

<div>

<div>

### [](){#sect.install-detect-disks}4.2.12. Détection des disques et autres périphériques

</div>

<div>

Cette étape automatique détecte les disques susceptibles d'accueillir
Debian. Ils seront proposés dans l'étape suivante : le partitionnement.

</div>

</div>

<div>

<div>

### [](){#sect.install-partman}4.2.13. Démarrage de l'outil de partitionnement

</div>

 

<div>

<div>

CULTURE Utilité du partitionnement

</div>

<div>

Le partitionnement, étape indispensable de l'installation, consiste à
diviser l'espace disponible sur les disques durs (chaque sous-partie
étant alors appelée une « partition ») en fonction des données à stocker
et de l'usage prévu de l'ordinateur. Cette étape intègre aussi le choix
des systèmes de fichiers employés. Toutes ces décisions ont une
influence en termes de performances, de sécurité des données et
d'administration du serveur.

</div>

</div>

<div>

L'étape du partitionnement est traditionnellement difficile pour les
utilisateurs débutants. Il faut en effet définir les différentes
portions des disques (ou « partitions ») qui accueilleront le système de
fichiers de Linux et sa mémoire virtuelle (swap). La tâche se complique
si un autre système d'exploitation existe déjà et si on souhaite le
conserver. En effet, il faudra alors veiller à ne pas altérer ses
partitions (ou à les redimensionner de manière indolore).

</div>

<div>

Fort heureusement, le logiciel de partitionnement dispose d'un mode
« assisté » qui propose à l'utilisateur les partitions à créer. Dans la
majorité des cas, il suffit de valider ses propositions.

</div>

<div>

 
<div>

<div>

![Choix du mode de
partitionnement](https://debian-handbook.info/browse/fr-FR/stable/images/inst-partman.png)

</div>

</div>

Figure 4.7. Choix du mode de partitionnement

</div>

<div>

Le premier écran de l'utilitaire de partitionnement propose d'employer
un disque complet pour créer les diverses partitions. Pour un ordinateur
(neuf) qui sera dédié à Linux, cette option est vraisemblablement la
plus simple et l'on choisira donc l'option Assisté - utiliser un disque
entier. Si l'ordinateur compte deux disques pour deux systèmes
d'exploitation, consacrer un disque à chacun est également une solution
facilitant le partitionnement. Dans ces deux cas, l'écran suivant permet
de choisir le disque à consacrer à Linux en validant l'option
correspondante (par exemple, SCSI1 (0,0,0) (sda) - 12.9 GB ATA VBOX
HARDDISK pour installer Debian sur le premier disque). Vous débutez
alors un partitionnement assisté.

</div>

<div>

 
<div>

<div>

![Disque à utiliser pour le partitionnement
assisté](https://debian-handbook.info/browse/fr-FR/stable/images/inst-partman-disk.png)

</div>

</div>

Figure 4.8. Disque à utiliser pour le partitionnement assisté

</div>

<div>

Le partitionnement assisté est également capable de mettre en place des
volumes logiques LVM au lieu de partitions (voir plus bas). Le reste du
fonctionnement restant le même, nous ne détaillerons pas les options
Assisté - utiliser tout un disque avec LVM (chiffré ou non).

</div>

<div>

Dans les autres cas, quand Linux doit cohabiter avec des partitions déjà
présentes, il faudra opter pour un partitionnement manuel.

</div>

<div>

<div>

#### [](){#sect.install-autopartman-mode}4.2.13.1. Partitionnement assisté

</div>

 

<div>

L'outil de partitionnement assisté propose trois méthodes de
partitionnement, qui correspondent à des usages différents.

</div>

<div>

 
<div>

<div>

![Partitionnement
assisté](https://debian-handbook.info/browse/fr-FR/stable/images/inst-autopartman-mode.png)

</div>

</div>

Figure 4.9. Partitionnement assisté

</div>

<div>

La première méthode s'intitule Tout dans une seule partition. Toute
l'arborescence du système Linux est stockée dans un seul système de
fichiers, correspondant à la racine /. Ce partitionnement simple et
robuste convient parfaitement pour des ordinateurs personnels ou
mono-utilisateurs. En réalité, deux partitions verront le jour : la
première abritera le système complet ; la seconde, la mémoire virtuelle.

</div>

<div>

La deuxième méthode, Partition /home séparée, est similaire mais découpe
l'arborescence en deux : une partie contient le système Linux (/) et la
seconde les répertoires personnels (c'est-à-dire les données des
utilisateurs, dans les fichiers placés sous /home/).

</div>

<div>

La dernière méthode de partitionnement, intitulée Partitions /home, /var
et /tmp séparées, convient pour les serveurs et les systèmes
multi-utilisateurs. Elle découpe l'arborescence en de nombreuses
partitions : en plus de la racine (/) et des comptes utilisateurs
(/home/), elle prévoit des partitions pour les données des logiciels
serveurs (/var/) et pour les fichiers temporaires (/tmp/). Ces divisions
ont plusieurs avantages. Les utilisateurs ne pourront pas bloquer le
serveur en consommant tout l'espace disque disponible (ils ne pourront
remplir que /tmp/ et /home/). Les données des démons (et notamment les
logs) ne pourront pas non plus bloquer le reste du système.

</div>

<div>

<div>

B.A.-BA Choisir un système de fichiers

</div>

 

<div>

Un système de fichiers définit la manière d'organiser les données sur un
disque. Chaque système de fichiers existant a ses mérites et ses
limitations. Certains sont plus robustes, d'autres plus efficaces : si
l'on connaît bien ses besoins, le choix d'un système de fichiers plus
adapté est possible. De nombreuses comparaisons ont déjà été réalisées ;
il semblerait que ReiserFS soit particulièrement efficace pour la
lecture de nombreux petits fichiers ; XFS, quant à lui, est plus véloce
avec de gros fichiers. Ext4, le système employé par défaut chez Debian,
est un bon compromis, par ailleurs basé sur les trois précédentes
versions du système de fichiers historiquement utilisé par Linux (ext,
ext2, et ext3). Ext4 corrige certaines limitations de ext3 et est
particulièrement adapté aux disques de très grande capacité. Une autre
possibilité est d'expérimenter le très prometteur btrfs qui intègre de
nombreuses fonctionnalités qui nécessitaient jusqu'à présent l'usage de
LVM et/ou RAID.

</div>

<div>

Un système de fichiers journalisé (comme ext3, ext4, btrfs, reiserfs ou
xfs) prend des dispositions particulières afin qu'en cas d'interruption
brutale, il soit toujours possible de revenir dans un état cohérent sans
être contraint à une analyse complète du disque (comme c'était le cas
avec le système ext2). Cette fonctionnalité est obtenue en remplissant
un journal décrivant les opérations à effectuer avant de les exécuter
réellement. Si une opération est interrompue, il sera possible de la
« rejouer » à partir du journal. Inversement, si une interruption a lieu
en cours de mise à jour du journal, le dernier changement demandé est
simplement ignoré : les données en cours d'écriture sont peut-être
perdues, mais les données sur le disque n'ayant pas changé, elles sont
restées cohérentes. Il s'agit ni plus ni moins d'un mécanisme
transactionnel appliqué au système de fichiers.

</div>

</div>

<div>

Après le choix du layout de partitionnement, le logiciel calcule une
proposition, qu'il détaille à l'écran et que l'on peut au besoin
modifier. On peut notamment choisir un autre système de fichiers si le
choix standard (ext4) ne convient pas. Dans la plupart des cas, il
suffit cependant d'accepter la proposition de partitionnement en
validant l'option Terminer le partitionnement et appliquer les
changements.

</div>

<div>

 
<div>

<div>

![Valider le
partitionnement](https://debian-handbook.info/browse/fr-FR/stable/images/inst-partman-validation.png)

</div>

</div>

Figure 4.10. Valider le partitionnement

</div>

</div>

<div>

<div>

#### [](){#sect.manual-partitioning}4.2.13.2. Partitionnement manuel

</div>

 

<div>

Le partitionnement manuel offre plus de souplesse et permet de choisir
le rôle et la taille de chaque partition. Par ailleurs, ce mode est
inévitable pour employer le RAID logiciel.

</div>

<div>

 
<div>

EN PRATIQUE Réduire une partition Windows

</div>

 

<div>

Pour installer Debian à côté d'un système existant (Windows ou autre),
il faut disposer d'un espace sur le disque qui ne soit pas utilisé par
cet autre système, de manière à pouvoir y créer les partitions dédiées à
Debian. Dans la majorité des cas, cela impliquera de réduire la
partition Windows et de réutiliser l'espace ainsi libéré.

</div>

<div>

L'installateur Debian permet d'effectuer cette opération, à condition de
l'utiliser en manuel. Il suffit alors de sélectionner la partition
Windows et de saisir sa nouvelle taille (cela fonctionne aussi bien avec
les partitions FAT que NTFS).

</div>

</div>

<div>

Le premier écran affiche les disques, les partitions qui les composent
et tout éventuel espace libre non encore partitionné. On peut
sélectionner chaque élément affiché ; une pression sur la touche Entrée
donne alors une liste d'actions possibles.

</div>

<div>

On peut effacer toutes les partitions d'un disque en sélectionnant
celui-ci.

</div>

<div>

En sélectionnant un espace libre d'un disque, on peut créer manuellement
une nouvelle partition. Il est également possible d'y effectuer un
partitionnement assisté, solution intéressante pour un disque contenant
déjà un système d'exploitation mais que l'on souhaite partitionner pour
Linux de manière standard. Reportez-vous à la [Section 4.2.13.1,
« Partitionnement
assisté »](https://debian-handbook.info/browse/fr-FR/stable/sect.installation-steps.html#sect.install-autopartman-mode)
pour plus de détails sur le partitionnement assisté.

</div>

<div>

<div>

B.A.-BA Point de montage

</div>

 

<div>

Le point de montage est le répertoire de l'arborescence qui abritera le
contenu du système de fichiers de la partition sélectionnée. Ainsi, une
partition montée sur /home/ est traditionnellement prévue pour contenir
les données des utilisateurs.

</div>

<div>

Si ce répertoire se nomme « / », on parle alors de la racine de
l'arborescence, donc de la partition qui va réellement accueillir le
système Debian.

</div>

</div>

<div>

<div>

<div>

<div>

B.A.-BA Mémoire virtuelle, swap

</div>

</div>

</div>

 

<div>

La mémoire virtuelle permet au noyau Linux en manque de mémoire vive
(RAM) de libérer un peu de place en stockant sur la partition d'échange,
donc sur le disque dur, une partie du contenu de la RAM restée inactive
un certain temps.

</div>

<div>

Pour simuler la mémoire supplémentaire, Windows emploie un fichier
d'échange contenu directement sur un système de fichiers. À l'inverse,
Linux emploie une partition dédiée à cet usage, d'où le terme de
« partition d'échange ».

</div>

</div>

<div>

En sélectionnant une partition, on peut indiquer la manière dont on va
l'utiliser :

</div>

<div>

-   <div>

    la formater et l'intégrer à l'arborescence en choisissant un point
    de montage ;

    </div>

-   <div>

    l'employer comme partition d'échange (swap) ;

    </div>

-   <div>

    en faire un volume physique pour chiffrement (pour protéger la
    confidentialité des données de certaines partitions, voir plus
    loin) ;

    </div>

-   <div>

    en faire un volume physique pour LVM (notion détaillée plus loin
    dans ce chapitre) ;

    </div>

-   <div>

    l'utiliser comme périphérique RAID (voir plus loin dans ce
    chapitre) ;

    </div>

-   <div>

    ou ne pas l'exploiter et la laisser inchangée.

    </div>

</div>

</div>

<div>

<div>

#### [](){#sect.install-software-raid}4.2.13.3. Emploi du RAID logiciel

</div>

 

<div>

Certains layouts de RAID permettent de dupliquer les informations stockées
sur des disques durs pour éviter toute perte de données en cas de
problème matériel condamnant l'un d'entre eux. Le RAID de niveau 1
maintient une simple copie fidèle (miroir) d'un disque sur un autre,
alors que le RAID de niveau 5 répartit sur plusieurs disques des
informations redondantes qui permettront de reconstituer intégralement
un disque défaillant.

</div>

<div>

Nous traiterons ici du RAID de niveau 1, le plus simple à mettre en
œuvre. La première étape est de créer deux partitions de taille
identique situées sur deux disques différents et de les étiqueter volume
physique pour RAID.

</div>

<div>

Il faut ensuite choisir dans l'outil de partitionnement l'élément
Configurer le RAID avec gestion logicielle pour transformer ces deux
partitions en un nouveau disque virtuel et sélectionner Créer un
périphérique multidisque dans cet écran de configuration. Suit alors une
série de questions concernant ce nouveau périphérique. La première
s'enquiert du niveau de RAID à employer — RAID1 dans notre cas. La
deuxième demande le nombre de périphériques actifs — deux ici, soit le
nombre de partitions à intégrer dans ce périphérique RAID logiciel. La
troisième question concerne le nombre de périphériques de réserve —
zéro ; on n'a prévu aucun disque supplémentaire pour prendre
immédiatement la relève d'un éventuel disque défectueux. La dernière
question demande de choisir les partitions retenues pour le périphérique
RAID — soit les deux qu'on a prévues à cet usage (on veillera bien à ne
sélectionner que des partitions mentionnant explicitement raid).

</div>

<div>

Au retour dans le menu principal, un nouveau disque virtuel RAID
apparaît. Ce disque est présenté avec une unique partition qu'on ne peut
pas supprimer mais que l'on peut affecter à l'usage de son choix (comme
n'importe quelle autre partition).

</div>

<div>

Pour plus de détails sur le fonctionnement du RAID, on se reportera à la
[Section 12.1.1, « RAID
logiciel »](https://debian-handbook.info/browse/fr-FR/stable/advanced-administration.html#sect.raid-soft).

</div>

</div>

<div>

<div>

#### [](){#sect.install-lvm}4.2.13.4. Emploi de LVM (Logical Volume Manager)

</div>

 

<div>

LVM permet de créer des partitions « virtuelles » s'étendant sur
plusieurs disques. L'intérêt est double : les tailles des partitions ne
sont plus limitées par celles des disques individuels mais par leur
volume cumulé et on peut à tout moment augmenter la taille d'une
partition existante, en ajoutant au besoin un disque supplémentaire.

</div>

<div>

LVM emploie une terminologie particulière : une partition virtuelle est
un « volume logique », lui-même compris dans un « groupe de volumes »,
ou association de plusieurs « volumes physiques ». Chacun de ces
derniers correspond en fait à une partition « réelle » (ou à une
partition RAID logicielle).

</div>

 

<div>

Cette technique fonctionne assez simplement : chaque volume, physique ou
logique, est découpé en blocs de même taille, que LVM fait correspondre
entre eux. L'ajout d'un nouveau disque entraîne la création d'un nouveau
volume physique et ses nouveaux blocs pourront être associés à n'importe
quel groupe de volumes. Toutes les partitions du groupe de volumes ainsi
agrandi disposeront alors d'espace supplémentaire pour s'étendre.

</div>

<div>

L'outil de partitionnement configure LVM en plusieurs étapes. Il faut
d'abord créer sur les disques existants des partitions qui seront les
volumes physiques LVM. Pour activer LVM, on choisira Configurer le
gestionnaire de volumes logiques (LVM), puis dans cet écran de
configuration, Créer un groupe de volumes — auquel on associera les
volumes physiques existants. Enfin, on pourra créer des volumes logiques
au sein de ce groupe de volumes. On notera que le système de
partitionnement automatique est capable de faire toute cette mise en
place.

</div>

<div>

Dans le menu du partitionneur, chaque volume logique apparaît comme un
disque avec une seule partition que l'on ne peut pas supprimer mais que
l'on peut affecter à l'usage de son choix.

</div>

<div>

Le fonctionnement de LVM est détaillé dans la [Section 12.1.2,
« LVM »](https://debian-handbook.info/browse/fr-FR/stable/advanced-administration.html#sect.lvm).

</div>

</div>

<div>

<div>

#### [](){#idm140363028617168}4.2.13.5. Chiffrement de partitions

</div>

 

<div>

Pour garantir la confidentialité de vos données, par exemple en cas de
perte ou de vol de votre ordinateur ou d'un disque dur, il est possible
de chiffrer les données de partitions. Cette fonctionnalité peut se
greffer très facilement en amont de n'importe quel système de fichiers
puisque, comme pour LVM, Linux (et plus particulièrement le pilote
dm-crypt) utilise le Device Mapper pour créer une partition virtuelle
(dont le contenu sera protégé) en s'appuyant sur une partition
sous-jacente qui stockera les données sous une forme chiffrée (grâce à
LUKS — Linux Unified Key Setup soit « Configuration de clés unifiée pour
Linux » — un format standard permettant de stocker les données chiffrées
mais aussi des méta-informations indiquant les algorithmes de
chiffrement employés).

</div>

<div>

 
<div>

SÉCURITÉ Partition d'échange chiffrée

</div>

<div>

Lorsqu'une partition chiffrée est employée, la clé de chiffrement est
stockée en mémoire vive. Obtenir cette clé permet également de
déchiffrer les données. Il est donc vital de ne pas en laisser de copie
accessible à l'éventuel voleur de l'ordinateur ou du disque, ou à un
technicien de maintenance. C'est pourtant quelque chose qui peut
facilement arriver avec un portable, puisque, lors d'une mise en veille
prolongée, le contenu de la mémoire vive est stockée sur la partition
d'échange. Si celle-ci n'est pas elle-même chiffrée, le voleur peut la
récupérer et l'utiliser pour déchiffrer les données des partitions
chiffrées. C'est pourquoi, lorsque vous employez des partitions
chiffrées, il est impératif de chiffrer également la partition
d'échange !

</div>

<div>

L'installateur Debian prévient l'utilisateur lorsqu'il essaye de créer
une partition chiffrée et que la partition d'échange ne l'est pas.

</div>

</div>

<div>

Pour créer une partition chiffrée, il faut d'abord attribuer une
partition disponible à cet usage. Pour cela, il convient de la
sélectionner et d'indiquer qu'elle sera utilisée comme volume physique
pour chiffrement. Ensuite, et après que le partitionnement du disque
contenant ce volume physique a été effectué, vous devrez sélectionner
Configurer les volumes chiffrés. Il sera alors proposé d'initialiser le
volume physique avec des données aléatoires (rendant plus difficile la
localisation des données réelles) puis de saisir une phrase secrète de
chiffrement qu'il vous faudra saisir à chaque démarrage de votre
ordinateur afin d'accéder au contenu de votre partition chiffrée. Une
fois cette étape terminée et de retour au menu de l'outil de
partitionnement, une nouvelle partition est disponible dans un volume
chiffré et vous pouvez désormais la configurer comme n'importe quelle
autre partition. Le plus souvent, cette partition sera utilisée comme
volume physique pour LVM afin de pouvoir protéger plusieurs partitions
(volumes logiques LVM) avec la même clé de chiffrement, dont notamment
la partition d'échange (voir encadré [SÉCURITÉ Partition d'échange
chiffrée](https://debian-handbook.info/browse/fr-FR/stable/sect.installation-steps.html#sidebar.encrypted-swap-partition)).

</div>

</div>

</div>

<div>

<div>

### [](){#idm140363028598960}4.2.14. Installation du système de base Debian

</div>

 

<div>

Cette étape, qui ne demande pas d'interaction de la part de
l'utilisateur, installe les paquets du « système de base » de Debian.
Celui-ci comprend les outils dpkg et apt, qui gèrent les paquets Debian,
ainsi que les utilitaires nécessaires pour démarrer le système et
commencer à l'exploiter.

</div>

<div>

 
<div>

<div>

![Installation du système de
base](https://debian-handbook.info/browse/fr-FR/stable/images/inst-basesystem.png)

</div>

</div>

Figure 4.11. Installation du système de base

</div>

</div>

<div>

<div>

### [](){#idm140363028591488}4.2.15. Configuration de l'outil de gestion des paquets (apt)

</div>

 

<div>

Pour que l'on puisse installer des logiciels supplémentaires, il est
nécessaire de configurer APT, en lui indiquant où trouver les paquets
Debian. Cette étape est aussi automatisée que possible. Elle commence
par une question demandant s'il faut utiliser une source de paquets sur
le réseau, ou s'il faut se contenter des seuls paquets présents sur le
CD-Rom.

</div>

<div>

<div>

NOTE CD-Rom Debian dans le lecteur

</div>

<div>

Si l'installateur détecte un disque d'installation Debian dans le
lecteur de CD-Rom, il n'est pas toujours nécessaire de configurer APT
pour aller chercher des paquets sur le réseau : il est automatiquement
configuré pour lire les paquets depuis ce lecteur. Si le disque fait
partie d'un jeu de plusieurs, il proposera cependant d'« explorer »
d'autres disques afin de référencer tous les paquets qu'ils stockent.

</div>

</div>

<div>

S'il faut utiliser des paquets en provenance du réseau, les deux
questions suivantes permettent de sélectionner un serveur sur lequel
aller chercher ces paquets, en choisissant d'abord un pays, puis un
miroir disponible dans ce pays (il s'agit d'un serveur public qui met à
disposition une copie de tous les fichiers du serveur de Debian).

</div>

<div>

 
<div>

<div>

![Choix d'un miroir
Debian](https://debian-handbook.info/browse/fr-FR/stable/images/inst-mirror.png)

</div>

</div>

Figure 4.12. Choix d'un miroir Debian

</div>

<div>

Enfin, le programme propose de recourir à un mandataire (proxy) HTTP. En
son absence, l'accès à Internet sera direct. Si l'on tape
http://proxy.falcot.com:3128, APT fera appel au proxy/cache de Falcot,
un programme « Squid ». Il est possible de retrouver ces paramètres en
consultant la configuration d'un navigateur web sur une autre machine
connectée au même réseau.

</div>

<div>

Les fichiers Packages.gz et Sources.gz sont ensuite automatiquement
téléchargés pour mettre à jour la liste des paquets reconnus par APT.

</div>

<div>

<div>

B.A.-BA Mandataire HTTP, proxy

</div>

 

<div>

Un mandataire (ou proxy) HTTP est un serveur effectuant une requête HTTP
pour le compte des utilisateurs du réseau. Il permet parfois d'accélérer
les téléchargements en gardant une copie des fichiers ayant transité par
son biais (on parle alors de proxy/cache). Dans certains cas, c'est le
seul moyen d'accéder à un serveur web externe ; il est alors
indispensable de renseigner la question correspondante de l'installation
pour que le programme puisse récupérer les paquets Debian par son
intermédiaire.

</div>

<div>

Squid est le nom du logiciel serveur employé par Falcot SA pour offrir
ce service.

</div>

</div>

</div>

<div>

<div>

### [](){#idm140363028569456}4.2.16. Concours de popularité des paquets

</div>

<div>

Le système Debian contient un paquet popularity-contest, dont le but est
de compiler des statistiques d'utilisation des paquets. Ce programme
collecte chaque semaine des informations sur les paquets installés et
ceux utilisés récemment et les envoie de manière anonyme aux serveurs du
projet Debian. Le projet peut alors tirer parti de ces informations pour
déterminer l'importance relative de chaque paquet, ce qui influe sur la
priorité qui lui sera accordée. En particulier, les paquets les plus
« populaires » se retrouveront sur le premier CD-Rom d'installation, ce
qui en facilitera l'accès pour les utilisateurs ne souhaitant pas
télécharger ou acheter le jeu complet.

</div>

<div>

Ce paquet n'est activé que sur demande, par respect pour la
confidentialité des usages des utilisateurs.

</div>

</div>

<div>

<div>

### [](){#idm140363028566096}4.2.17. Sélection des paquets à installer

</div>

<div>

L'étape suivante permet de choisir de manière très grossière le layout
d'utilisation de la machine ; les dix tâches présentées correspondent à
des listes de paquets à installer. La liste des paquets réellement
installés sera affinée et complétée par la suite, mais cette étape donne
une bonne base très simplement.

</div>

<div>

Certains paquets sont par ailleurs automatiquement installés en fonction
du matériel détecté (grâce au programme discover-pkginstall du paquet
discover). Ainsi, s'il détecte une machine virtuelle VirtualBox, il
installera le paquet virtualbox-guest-dkms permettant une meilleure
intégration de la machine virtuelle avec son système hôte.

</div>

<div>

 
<div>

<div>

![Choix des
tâches](https://debian-handbook.info/browse/fr-FR/stable/images/inst-tasksel.png)

</div>

</div>

Figure 4.13. Choix des tâches

</div>

</div>

<div>

<div>

### [](){#sect.installing-grub}4.2.18. Installation du chargeur d'amorçage GRUB

</div>

 

<div>

Le chargeur d'amorçage est le premier programme démarré par le BIOS. Ce
programme charge en mémoire le noyau Linux puis l'exécute. Souvent, il
propose un menu permettant de choisir le noyau à charger et/ou le
système d'exploitation à démarrer.

</div>

<div>

 
<div>

<div>

<div>

ATTENTION Chargeur d'amorçage et dual boot

</div>

</div>

</div>

 

<div>

Cette phase du programme d'installation Debian détecte les systèmes
d'exploitation déjà installés sur l'ordinateur et ajoute automatiquement
des choix correspondants dans le menu de démarrage ; mais tous les
programmes d'installation ne font pas de même.

</div>

<div>

En particulier, si l'on installe (ou réinstalle) Windows par la suite,
le chargeur de démarrage sera écrasé. Debian sera alors toujours présent
sur le disque dur, mais plus accessible par le menu de démarrage. Il
faudra alors démarrer sur le système d'installation de Debian en mode
rescue pour remettre en place un chargeur de démarrage moins exclusif.
L'opération est décrite en détail dans le manuel d'installation.
<div>

? <http://www.debian.org/releases/stable/amd64/ch08s07.html>

</div>

</div>

</div>

<div>

Le menu proposé par GRUB contient par défaut tous les noyaux Linux
installés ainsi que tous les autres systèmes d'exploitation détectés.
C'est pourquoi on acceptera la proposition de l'installer dans le Master
Boot Record (MBR). Puisque garder les anciennes versions préserve la
capacité à amorcer le système même si le dernier noyau installé est
défectueux ou mal adapté au matériel, il est judicieux de conserver
quelques anciennes versions de noyau.

</div>

<div>

GRUB est le chargeur d'amorçage installé en standard par Debian, en
raison de sa supériorité technique : il traite la plupart des systèmes
de fichiers et n'a donc pas besoin d'être mis à jour à chaque
installation d'un nouveau noyau car, lors de l'amorçage, il lit sa
configuration et retrouve la position exacte du nouveau noyau. Sa
version 1 (désormais connue sous le nom « Grub Legacy ») ne gérait pas
toutes les combinaisons de LVM et de RAID logiciel ; la version 2,
installée par défaut, est plus complète. Il peut rester des situations
où il faut recommander LILO (autre chargeur d'amorçage) ; l'installateur
le proposera automatiquement.

</div>

<div>

Pour plus d'informations sur la configuration de GRUB, vous pouvez
consulter la [Section 8.8.3, « Configuration de
GRUB 2 »](https://debian-handbook.info/browse/fr-FR/stable/sect.config-bootloader.html#sect.config-grub).

</div>

<div>

<div>

ATTENTION Chargeurs d'amorçage et architectures

</div>

<div>

LILO et GRUB, mentionnés dans ce chapitre, sont des chargeurs d'amorçage
pour les architectures i386 et amd64. Si vous installez Debian sur une
autre architecture, c'est un autre chargeur qui sera employé. Citons
entre autres yaboot ou quik pour powerpc, silo pour sparc, aboot pour
alpha, arcboot pour mips.

</div>

</div>

</div>

<div>

<div>

### [](){#idm140363028536048}4.2.19. Terminer l'installation et redémarrer

</div>

<div>

L'installation étant maintenant terminée, le programme vous invite à
sortir le CD-Rom de son lecteur, puis à redémarrer le PC.

</div>

<div>

Voir en ligne : [Le cahier de l’administrateur Debian - 4.2. Étapes du
programme
d’installation](https://debian-handbook.info/browse/fr-FR/stable/sect.installation-steps.html)

</div>

</div>
