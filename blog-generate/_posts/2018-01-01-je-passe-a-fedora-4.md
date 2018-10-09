---
title: "Je passe à Fedora 4"
date: 2018-03-08T09:23:27+01:00
layout: post
---
J'ai donc suivi les conseilles que Fred m'a donné, ça m'a bien aidé mais j'ai vu que sous Fedora, le groupe de paquets GNOME est déjà installé et que donc, pour le reste, il faut se le taper à la main. Hier soir je m'étais mis tôt au lit avec ce portable pour "travailler" dessus et aussi pour "arranger" l'installation par défaut de Fedora qui me déçois beaucoup, oui une installation avec des logiciels populaires comme Libreoffice en anglais sans les traductions français m'agace un peu mais ce n'est qu'une goutte dans l'océan, j'ai aussi pour moi, un gros manque de logiciels ou si on veut le dire autrement une installation vraiment minimale de GNOME. Non le soucis pour moi, encore une fois pour moi, vient de DNF, il n'est pas au point, comme quand on fait une recherche, est il obligé de nous balancer les paquets dans un ordre non alphabétique? Il ne serait pas mieux de faire lister les paquets sans les "correspond à votre recherche" et "contient X"? Il ne serait pas mieux de signaler comme cela se fait ailleurs, les paquets qui sont déjà installés sur le système?

Mais ce n'est qu'un soucis parmi tant d'autres, j'ai par exemple suivit la page du [wiki](https://doc.fedora-fr.org/wiki/Dépôt_RPM_Fusion) pour ajouter les dépôts de RPMfusion, mais j'ai préféré faire comme dit sur le site des [dépôts en question](https://rpmfusion.org/Configuration) en prenant la méthode automatique et graphique via le navigateur Firefox, ça m'a ouvert Logithèque de GNOME et installer [rpmfusion-free-release-27.noarch.rpm](https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-27.noarch.rpm) et [rpmfusion-nonfree-release-27.noarch.rpm](https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-27.noarch.rpm), puis un upgrade plus tard j'ai installé des paquets, la-dessus il m'a demandé de valider la clé de RPMfusion ce que j'ai empressé de faire. En faite comme dit la traduction de google translate:

>Once you clicked on above link Firefox will ask you how to Open the file. Here you can simply use the default and open the file with the default application Package Installer. Then Firefox will call Package Kit, which asks Do you want to install this file ?. Click OK to begin install; Package Kit then will complain about a Missing security signature; once you tell Package Kit to install the package nevertheless it will move on and install it. That's all.

>Une fois que vous avez cliqué sur le lien ci-dessus, Firefox vous demandera comment ouvrir le fichier. Ici, vous pouvez simplement utiliser la valeur par défaut et ouvrir le fichier avec l'application par défaut Package Installer. Ensuite, Firefox appellera Package Kit, qui demande si vous voulez installer ce fichier. Cliquez sur OK pour commencer l'installation. Le kit de colis va alors se plaindre d'une signature de sécurité manquante; Une fois que vous avez dit à Package Kit d'installer le paquet, il va continuer et l'installer. C'est tout.

Ce qui m’embête, c'est le simple fait qu'hier j'ai donc voulu installer des paquets venant de ces dépôts et qu'il m'a redemandé de valider la clé, je trouve ça étrange, ai-je mal fait un truc?

Je n'ai pas cherché longtemps pour essayer de trouver un endroit qui liste les paquets de Fedora et où l'on peut faire des recherches de paquets, un peu comme sous [Gentoo](https://packages.gentoo.org/), [Debian](https://www.debian.org/distrib/packages), [Mageia](https://madb.mageia.org/) ou encore [openSUSE](https://software.opensuse.org/search) pour ne citer qu'elles, mais sous Fedora je n'ai pas su, non rien sur leur site ou sinon j'ai pas les yeux en face des trous. Je suis donc passé par [pkgs.org](https://pkgs.org/).

Ceci étant dit, j'ai donc utilisé le PC sous Fedora hier, j'ai été accueilli par une centaine de mises-à-jour, un peu étonné qu'en deux jours il y en ait autant. Puis j'ai installé la traduction de Libreoffice, installer des paquets comme VLC, Smplayer, Amule, MlDonhey, Deluge, Filezilla, ... En faite, les paquets dont j'ai l'habitude d'utiliser sur mon propre système. J'ai installé aussi des paquets dont je n'ai pas l'habitude d'installer car normalement déjà présent comme Brasero. Oui je fais parti comme je l'ai précédemment dit, de ces utilisateurs qui ont connu l'informatique avec les supports en durs et non volatiles comme de nos jours. J'ai connu les disquettes des Commodore, Amiga et Amstrad mais pas que, j'ai connu le Windows 3.1 et ses disquettes puis l'arrivé du CD-rom et enfin du DVD... J'ai donc naturellement l'habitude de graver sur des supports réelles mes différentes sauvegardes. Je mens puisque depuis au bas mot 10 ans, je fais des sauvegardes uniquement sur des disques durs externes ou des grosses clé. Mais il est hors de question que je sauvegarde dans le cloud ou le nuage, je suis resté avec une amère expérience, celle de Ubuntu-ONE, vous savez le nuage de chez Ubuntu, j'avais bien aimé ce conforts de disposer peu importe l’outil utilisé que ça soit le smartphone ou un PC, de ses données. Et puis un jour, on nous dit que ça va s’arrêter et qu'il fallait récupérer ses données. Sans s’arrêter sur cette histoire, on doit payer pour un service qui en faite aura la main mise sur nos données, alors on fait des scandales sur Windows, sur Google et autre Facebook mais sur le cloud on ne dit rien ou presque.

J'ai aussi un mauvais souvenir de gamers avec ma PS3 et des jeux installés, disque durs de la PS3 grillé, remplacement de la console et quand j'ai retourné sur le playstore pour télécharger les jeux, certains n'étaient simplement plus disponibles... Donc pour moi, le support non palpable n'est pas adapté.
Aussi, j'ai une voiture, des voitures on va dire, chacune ayant un poste radio, sur chaque poste radio j'écoute fréquemment des CD enregistrés ou des clés USB.

Tout ça pour dire que se trouver sur un OS sans logiciels de gravure me parait étrange...

Donc voila où j'en suis, Fedora est une bien belle distribution, je compte toujours la garder au moins pour voir comment se passe un saut de version. Puis apres cela, si je n'arrive pas à m'adapter à elle-ci, j'irais mettre une Leap ou remettre une Debian, bien que je n'aime pas la monoculture.