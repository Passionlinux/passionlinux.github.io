---
title: Debian; Cycle de vie d'une release
date: 2016-04-01 19:42
layout: post
---

<div>

<div>

Le projet dispose à tout instant de trois à six versions différentes de
chaque logiciel, nommées Experimental, Unstable, Testing, Stable,
Oldstable, et même Oldoldstable. Chacune correspond à un stade différent
du développement. Pour bien les comprendre, suivons le parcours d'un
programme, de sa première mise en paquet à son intégration dans une
version stable de Debian.

</div>

<div>

</div>

<div>

<div>

<div>

<div>

VOCABULAIRE Release Le terme « release » désigne chez Debian une version
particulière d'une distribution (ex : « the unstable release » signifie
« la version instable »). Il désigne aussi l'annonce publique de toute
nouvelle version (stable).

</div>

</div>

</div>

</div>

![](http://download.tuxfamily.org/passionlinux/images/infographic_debian-v2.1.en.png){width="919"
height="642"}  
<!--more-->

<div>

<div>

<div>

<div>

### 1.6.1. Le statut Experimental

</div>

</div>

</div>

<div>

Traitons d'abord le cas particulier de la distribution Experimental :
c'est un ensemble de paquets Debian correspondant à des logiciels en
cours de développement et pas forcément finalisés — d'où son nom. Tout
ne transite pas par cette étape ; certains développeurs y créent des
paquets pour obtenir un premier retour des utilisateurs les plus
expérimentés (ou les plus courageux).

</div>

<div>

Par ailleurs, cette distribution abrite fréquemment des modifications
importantes portant sur des paquets de base et dont l'intégration dans
Unstable avec des bogues gênants aurait des répercussions trop
importantes et bloquantes. C'est donc une distribution totalement
isolée, dont les paquets ne migrent jamais vers une autre (sauf
intervention expresse du mainteneur ou des ftpmasters). Elle n'est
également pas utilisable de manière indépendante : seul un sous-ensemble
des paquets existants est présent dans Experimental et elle ne contient
généralement pas le système de base. Cette distribution est donc
exploitable seulement en combinaison avec une autre distribution
indépendante, comme Unstable.

</div>

</div>

<div>

<div>

<div>

<div>

### 1.6.2. Le statut Unstable

</div>

</div>

</div>

<div>

Revenons au cas d'un paquet layout. Le mainteneur crée un premier paquet,
qu'il compile pour Unstable et place sur le serveur
ftp-master.debian.org. Cette première manifestation implique inspection
et validation par les ftpmasters. Le logiciel est alors disponible dans
Unstable, la distribution la plus à jour choisie par des utilisateurs
préférant le dernier cri à l'assurance de l'absence de bogues graves.
Ceux-ci découvrent alors le programme et le testent.

</div>

<div>

S'ils y découvrent des bogues, ils les décrivent à son mainteneur. Ce
dernier prépare alors régulièrement des versions corrigées, qu'il place
sur le serveur.

</div>

<div>

Toute nouvelle mise en ligne est répercutée sur tous les miroirs Debian
du monde dans les 6 heures. Les utilisateurs valident alors la
correction et cherchent d'autres problèmes, consécutifs aux
modifications. Plusieurs mises à jour peuvent ainsi s'enchaîner
rapidement. Pendant ce temps, les robots autobuilders sont entrés en
action. Le plus souvent, le mainteneur ne dispose que d'un PC
traditionnel et aura compilé son paquet pour architecture amd64 (ou
i386) ; les autobuilders ont donc pris le relais et compilé
automatiquement des versions pour toutes les autres architectures.
Certaines compilations pourront échouer ; le mainteneur recevra alors un
rapport de bogue signalant le problème, à corriger dans les prochaines
versions. Lorsque le bogue est découvert par un spécialiste de
l'architecture concernée, il arrive que ce rapport soit accompagné d'un
correctif prêt à l'emploi.

</div>

<div>

<div>

<div>

![Compilation d'un paquet par les
autobuilders](https://debian-handbook.info/browse/fr-FR/stable/images/autobuilder.png)

</div>

</div>

Figure 1.2. Compilation d'un paquet par les autobuilders

</div>

<div>

<div>

<div>

<div>

DÉCOUVERTE buildd, le recompilateur de paquet Debian

</div>

</div>

</div>

<div>

buildd est l'abréviation de build daemon. Ce logiciel recompile
automatiquement les nouvelles versions des paquets Debian sur
l'architecture qui l'accueille (la compilation croisée — crosscompiling
— est évitée dans la mesure du possible).

</div>

<div>

Ainsi, pour produire des binaires destinés à l'architecture arm64, le
projet dispose de machines arm64. Le programme buildd y fonctionne en
permanence afin de créer des paquets binaires pour arm64 à partir des
paquets sources expédiés par les développeurs Debian.

</div>

<div>

Ce logiciel est employé sur tous les ordinateurs servant d'autobuilders
à Debian. Par extension, le terme buildd désigne souvent ces machines,
en général réservées à cet usage.

</div>

</div>

</div>

<div>

<div>

<div>

<div>

### 1.6.3. La migration vers Testing

</div>

</div>

</div>

<div>

Un peu plus tard, le paquet aura mûri ; compilé sur toutes les
architectures, il n'aura pas connu de modifications récentes. C'est
alors un candidat pour l'intégration dans la distribution Testing —
ensemble de paquets Unstable sélectionnés sur quelques critères
quantifiables. Chaque jour, un programme choisit automatiquement les
paquets à intégrer à Testing, selon des éléments garantissant une
certaine qualité :

</div>

<div>

1.  <div>

    absence de bogues critiques, ou tout du moins nombre inférieur à
    celui de la version actuellement intégrée dans Testing ;

    </div>

2.  <div>

    villégiature minimale de 10 jours dans Unstable, ce qui laisse assez
    de temps pour trouver et signaler les problèmes graves ;

    </div>

3.  <div>

    compilation réussie sur toutes les architectures officiellement
    prises en charge ;

    </div>

4.  <div>

    dépendances pouvant toutes être satisfaites dans Testing, ou qui
    peuvent du moins y progresser de concert avec le paquet.

    </div>

</div>

<div>

Ce système n'est évidemment pas infaillible ; on trouve régulièrement
des bogues critiques dans un paquet intégré à Testing. Il est pourtant
globalement efficace et Testing pose beaucoup moins de problèmes
qu'Unstable, représentant pour beaucoup un bon compromis entre la
stabilité et la soif de nouveauté.

</div>

<div>

<div>

<div>

<div>

NOTE Limitations de Testing

</div>

</div>

</div>

<div>

Bien que très intéressante dans son principe, Testing rencontre quelques
problèmes pratiques : l'enchevêtrement des dépendances croisées entre
paquets est tel qu'un paquet ne peut que rarement y progresser tout
seul. Les paquets dépendant tous les uns des autres, il est parfois
nécessaire d'y faire progresser simultanément un grand nombre d'entre
eux, ce qui est impossible tant que certains subissent des mises à jour
régulières. Par ailleurs, le script identifiant les familles de paquets
ainsi solidarisés peine beaucoup à les constituer (il s'agirait d'un
problème NP-complet, pour lequel nous connaissons heureusement quelques
bonnes heuristiques). C'est pourquoi on peut intervenir manuellement et
conseiller ce script en lui suggérant des ensembles de paquets ou en
imposant l'inclusion de certains d'entre eux — quitte à casser
temporairement quelques dépendances. Cette fonctionnalité est accessible
aux Release Managers et à leurs assistants.

</div>

<div>

Rappelons qu'un problème NP-complet est de complexité algorithmique
exponentielle en fonction de la taille des données, c'est-à-dire la
longueur du codage (le nombre de chiffres) des éléments concernés. La
seule manière de le résoudre est souvent d'examiner toutes les
configurations possibles, ce qui requiert parfois d'énormes moyens. Une
heuristique en est une solution approchée et satisfaisante.

</div>

</div>

<div>

<div>

<div>

<div>

COMMUNAUTÉ Le Release Manager

</div>

</div>

</div>

<div>

Release Manager (gestionnaire de versions) est un titre important,
associé à de lourdes responsabilités. Son porteur doit en effet gérer la
sortie de la nouvelle version stable de Debian et définir le processus
d'évolution de Testing tant qu'elle ne répond pas aux critères de
qualité de Stable. Il définit également un calendrier prévisionnel (pas
toujours respecté).

</div>

<div>

On trouve aussi des Stable Release Managers (gestionnaires de la version
stable), souvent abrégé SRM, qui gèrent et sélectionnent les mises à
jour de la version stable de Debian. Ils y incluent systématiquement les
correctifs de sécurité et examinent au cas par cas toutes les autres
propositions d'inclusion émises par des développeurs Debian soucieux de
mettre à jour un de leurs paquets dans la version stable.

</div>

</div>

</div>

<div>

<div>

<div>

<div>

### 1.6.4. La promotion de Testing en Stable

</div>

</div>

</div>

<div>

Supposons notre paquet désormais intégré à Testing. Tant qu'il est
perfectible, son responsable doit persister à l'améliorer et recommencer
le processus depuis Unstable (mais ces inclusions ultérieures dans
Testing sont en général plus rapides : à moins d'avoir changé de manière
significative, toutes les dépendances sont déjà présentes). Quand il
atteint la perfection, son mainteneur a fini son travail et la prochaine
étape est l'inclusion dans la distribution Stable, en réalité une simple
copie de Testing à un moment choisi par le Release Manager. L'idéal est
de prendre cette décision quand l'installateur est prêt et quand plus
aucun programme de Testing n'a de bogue critique répertorié.

</div>

<div>

Étant donné que ce moment ne survient jamais dans la pratique, Debian
doit faire des compromis : supprimer des paquets dont le mainteneur n'a
pas réussi à corriger les bogues à temps ou accepter de livrer une
distribution comptant quelques bogues pour des milliers de logiciels. Le
Release Manager aura préalablement prononcé une période de freeze (gel),
où il devra approuver chaque mise à jour de Testing. Le but est
d'empêcher toute nouvelle version (et ses nouveaux bogues) et de
n'approuver que des mises à jours correctives.

</div>

<div>

<div>

![Parcours d'un paquet au sein des différentes versions de
Debian](https://debian-handbook.info/browse/fr-FR/stable/images/release-cycle.png)

</div>

Figure 1.3. Parcours d'un paquet au sein des différentes versions de
Debian

</div>

<div>

<div>

<div>

<div>

VOCABULAIRE Freeze : la dernière ligne droite

</div>

</div>

</div>

<div>

Pendant la période de freeze, l'évolution du contenu de la distribution
Testing est bloquée : plus aucune mise à jour automatique n'a lieu.
Seuls les Release Managers sont alors habilités à y changer des paquets,
selon leurs propres critères. L'objectif est d'éviter l'apparition de
nouveaux bogues par l'introduction de nouvelles versions ; seules les
mises à jour bien examinées sont acceptées lorsqu'elles corrigent des
bogues importants.

</div>

</div>

<div>

Après la sortie de la nouvelle version stable, le Stable Release Manager
en gère les évolutions ultérieures (appelées « révisions », par ex. :
7.1, 7.2, 7.3 pour la version 7). Ces mises à jour intègrent
systématiquement tous les correctifs de sécurité. On y trouve également
les corrections les plus importantes (le mainteneur du paquet doit
prouver la gravité du problème qu'il souhaite corriger pour faire
intégrer sa mise à jour).

</div>

<div>

À la fin du voyage, notre hypothétique paquet est désormais intégré à la
distribution stable. Ce trajet, non dépourvu de difficultés, explique
les délais importants séparant les versions stables de Debian. Il
contribue surtout à sa réputation de qualité. De plus, la majorité des
utilisateurs est satisfaite par l'emploi de l'une des trois
distributions disponibles en parallèle. Les administrateurs systèmes,
soucieux avant tout de la stabilité de leurs serveurs, se moquent de la
dernière version de GNOME ; ils opteront pour Debian Stable et en seront
satisfaits. Les utilisateurs finaux, plus intéressés par la dernière
version de GNOME ou de KDE que par une stabilité irréprochable,
trouveront en Debian Testing un bon compromis entre absence de problèmes
graves et logiciels relativement à jour. Enfin, les développeurs et
utilisateurs les plus expérimentés pourront ouvrir la voie en testant
toutes les nouveautés de Debian Unstable dès leur sortie, au risque de
subir les affres et bogues inhérents à toute nouvelle version de
logiciel. À chaque public sa Debian !

</div>

<div>

<div>

<div>

<div>

CULTURE GNOME et KDE, les bureaux graphiques

</div>

</div>

</div>

<div>

GNOME (GNU Network Object Model Environment, ou environnement réseau de
modèle objet de GNU) et KDE (K Desktop Environment, ou environnement de
bureau K) sont les deux « bureaux graphiques » les plus populaires dans
le milieu du logiciel libre. On entend par là un ensemble de logiciels
de bureautique permettant d'effectuer aisément les opérations les plus
courantes au travers d'une interface graphique. Ils comportent notamment
un gestionnaire de fichiers, une suite bureautique, un navigateur web,
un logiciel de courrier électronique, des accessoires multimédias, etc.
Leur différence la plus visible réside dans le choix de la bibliothèque
graphique employée : GNOME a choisi GTK+ (logiciel libre sous licence
LGPL) et KDE a opté pour Qt (un logiciel libre appartenant à une
entreprise, disponible sous licence GPL et sous licence commerciale).
<div>

? <http://www.gnome.org/>

</div>

<div>

? <http://www.kde.org/>

</div>

</div>

</div>

<div>

<div>

<div>

![Parcours chronologique d'un paquet logiciel empaqueté par
Debian](https://debian-handbook.info/browse/fr-FR/stable/images/package-lifecycle.png)

</div>

</div>

Figure 1.4. Parcours chronologique d'un paquet logiciel empaqueté par
Debian

</div>

</div>

<div>

<div>

<div>

<div>

### 1.6.5. Le statut de Oldstable et Oldoldstable

</div>

</div>

</div>

<div>

Chaque version Stable a une durée de vie prévue d'environ 5 ans ; étant
donné que les versions stables se succèdent au rythme approximatif d'une
tous les 2 ans, il peut y avoir jusqu'à 3 versions supportées à un
instant donné. Lorsqu'une nouvelle version stable est publiée, la
précédente devient Oldstable et celle d'encore avant devient
Oldoldstable.

</div>

<div>

Le support à long terme (Long Term Support, LTS) des versions de Debian
est une initiative récente : des contributeurs individuels et des
sociétés joignent leurs forces pour créer l'équipe Debian LTS. Les
anciennes versions qui ne sont plus officiellement supportées par
l'équipe de sécurité de Debian deviennent la responsabilité de cette
nouvelle équipe.

</div>

<div>

L'équipe de sécurité de Debian s'occupe du support de sécurité de la
version actuellement Stable ; elle s'occupe aussi de Oldstable, mais
seulement pendant la durée nécessaire pour assurer qu'il y a au moins un
an de chevauchement avec la version actuellement stable. Cela correspond
approximativement à trois ans de support effectif pour chaque version.
L'équipe Debian LTS prend alors la main pour assurer les deux dernières
années de support de sécurité, de sorte que chaque version bénéficie
d'au moins 5 ans de support et que les utilisateurs puissent migrer
d'une version N à la version N+2.
<div>

? <https://wiki.debian.org/LTS>

</div>

</div>

<div>

<div>

<div>

<div>

COMMUNITY Les sociétés qui parrainent l'effort LTS

</div>

</div>

</div>

<div>

Le support à long terme est une lourde responsabilité, parce que les
volontaires ont tendance à éviter le travail perçu comme non
enthousiasmant. Or, la fourniture de support de sécurité pour des
logiciels vieux de 5 ans est, pour de nombreux contributeurs, nettement
moins enthousiasmant que la mise en paquet de nouvelles versions amont
ou le développement de nouvelles fonctionnalités.

</div>

<div>

Pour que ce projet prenne vie, il a donc fallu compter sur le fait que
le support à long terme est particulièrement important pour les
sociétés, et qu'elles seraient d'accord pour mutualiser le coût de ce
support de sécurité.

</div>

<div>

Le projet a commencé en juin 2014 : certaines organisations ont permis à
leurs employés de contribuer à temps partiel à Debian LTS, et d'autres
ont préféré apporter leur soutien financier afin que des contributeurs
Debian puissent être payés pour faire le travail qu'ils ne feraient pas
gratuitement. La plupart des contributeurs Debian qui se sont impliqués
dans le projet LTS se sont rejoints pour mettre en place une offre de
financement claire gérée par Freexian (la société de Raphaël Hertzog) :
<div>

? <http://www.freexian.com/services/debian-lts.html>

</div>

</div>

<div>

L'équipe LTS n'est pas encore en mesure de supporter correctement tous
les paquets de Debian, de sorte que les volontaires travaillent sur les
paquets qui les intéressent alors que les contributeurs payés donnent la
priorité aux paquets qui intéressent particulièrement leurs parrains.

</div>

<div>

Le projet est toujours à la recherche de nouveaux parrains : et si
c'était votre société ? Pouvez-vous libérer une partie du temps d'un
employé pour travailler sur le support à long terme ? Pouvez-vous
allouer un petit budget pour le support de sécurité ?
<div>

? <https://wiki.debian.org/LTS/Funding>

</div>

</div>

</div>

</div>

 

<div>

<div>

<div>

<div>

Voir en ligne : [1.6. Cycle de vie d’une
release](https://debian-handbook.info/browse/fr-FR/stable/sect.release-lifecycle.html)

</div>

</div>

</div>

</div>

</div>

 
