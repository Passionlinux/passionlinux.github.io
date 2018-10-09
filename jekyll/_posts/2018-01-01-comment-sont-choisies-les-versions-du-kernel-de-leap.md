---
title: "Comment sont choisies les versions du kernel de Leap?"
date: 2018-04-06T18:41:18+02:00
layout: post
---

Je me posais un peu la question dernièrement puisque je trouvait étrange que la future Leap se coltine une version 4.12 du kernel, Sogal nous a fait parvenir une superbe explication directement de l’intéressé:

![1521209313](https://www.alionet.org/attachment.php?attachmentid=4019&d=1521209313)

La prochaine version d'openSUSE Leap, numérotée 15, pointe son nez et on sait d'ores et déjà qu'elle bénéficiera du noyau Linux en version 4.12.
Cela pourrait en étonner plus d'un et on serait en droit de se demander pourquoi un tel choix alors que la version courante du noyau est 4.15 ou si, au court de sa vie, le noyau de Leap 15 pourra être mis à jour afin de ne pas rester avec un noyau jugé trop ancien.

Cette question a été posée sur la liste de diffusion [opensuse-factory](https://lists.opensuse.org/opensuse-factory/2018-03/msg00133.html) et un des participants très informé à bien voulu prendre le temps de donner une réponse claire et complète qu'il paraît important de retransmettre. Le texte qui suit en est donc une traduction et une adaptation au format « article » libres.

## Pourquoi Leap 15 aura le noyau 4.12 au lieu de la version 4.14 (ou ultérieure) ? (par Peter Linnell) ##

Il faut tout d'abord rappeler que la distribution openSUSE Leap bénéficie d'une base de code partagée avec la version professionnelle SLE (Suse Linux Enterprise), base dont le noyau fait partie. À cet égard, il faut beaucoup de temps pour que le noyau obtienne les certifications requises pour fonctionner sur les matériels des clients de Suse et avec les logiciels d'autres éditeurs professionnels. Toutes les étapes permettant une telle certification pour le noyau 4.12 auraient dû être retardées ou bien recommencées pour la version 4.14 si celle-ci avait été choisie en finalité.
Le travail à fournir afin d'obtenir une telle certification est colossal et coûteux, il nécessite la mobilisation de nombreux ingénieurs et requiert d'avoir à disposition les différents matériels pour lesquels la distribution doit être certifiée.

L'auteur de la réponse initiale rapporte l'exemple du processus de certification d'un serveur layout « lame » et d'une armoire de stockage. Il a fallu pour cela mobiliser 3 ingénieurs durant plusieurs jours, assurer le déplacement au travers des États-Unis de 2 experts SUSE (dont l'auteur) pour un total estimé à plus de 10 000 $. Le tout pour certifier un seul layout de matériel !

Les membres de la communauté openSUSE ne sont sûrement pas tous conscients du genre de matériel pour lequel est certifiée la SLE (SUSE Linux Enterprise) (ndt: et donc le noyau de la Leap) mais il s'en trouve parmi eux de très exotiques et très chers.
On peut citer deux exemples :

1. Les serveurs SAP HANA qui tournent quasi exclusivement sous SLES (SUSE Linux Enterprise Server). Une image système de 32 To peut absorber jusqu'à 5 ou 6 fois ce volume de données compressées et les contenir en mémoire. Nous parlons là de 150 à 180 To de données disponibles en RAM afin de réaliser des analyses en temps réel !
Pratiquer des tests sur ce genre de monstres nécessite d'une part des semaines d’ingénierie et d'autre part que le fabriquant mette à disposition une machine de plusieurs millions de dollars.
https://www.hpe.com/us/en/solutions/sap-hana.html

2. Les systèmes SGI, une entreprise rachetée par HPE. Il s'agît de systèmes NUMA (« non uniform memory architecture » ou architecture mémoire non uniforme) pouvant théoriquement gérer jusqu'à 64 To de RAM avec un seul noyau Linux.
https://www.hpcwire.com/2016/05/11/t...life-sciences/

En ce qui concerne les logiciels, certaines piles logicielles éditées par les fabricants peuvent prendre des semaines pour être certifiées. Les fabricants eux-mêmes peuvent réaliser des tests de résistance ou des contrôles qualité afin de s'assurer que tout est conforme. Après tout, les éditeurs de logiciels fournissent un certain niveau de garantie à leurs clients en ce qui concerne la compatibilité et la stabilité qu'ils se doivent de maintenir. Un problème dans leurs logiciels pourrait entraîner un manque à gagner considérable pour leurs clients.

Donc, du point de vue de l'entreprise, la décision que telle version du noyau sera utilisée met en branle une machinerie complexe, requérant une grande coordination, en interne mais aussi avec les clients et partenaires. Ce genre de décision n'est donc pas pris à la légère.

En tant que membres de la communauté openSUSE, nous avons donc de la chance de bénéficier d'une telle ingénierie. Ce sont littéralement des millions de dollars d'investissement qui, non seulement sont mis à disposition dans Leap, mais qui démontre bien la volonté affirmée de SUSE de voir openSUSE réussir et de l'intérêt que l'entreprise porte à notre communauté.

Pour conclure, il faut rappeler, si besoin, que le noyau, bien qu'en version 4.12 bénéficiera des rétro-portages (« backports ») tout au long de sa durée de vie en vue d'apporter des correctifs et d'améliorer la prise en charge matérielle et logicielle.

Source: https://www.alionet.org/content.php?813-Comment-sont-choisies-les-versions-du-kernel-de-Leap
