---
title: "Comment participer à openSUSE pour faire des paquets avec OBS"
date: 2018-04-11T13:45:58+02:00
layout: post
---
Pour empaqueter et surtout participer à openSUSE, on doit passer par OBS d'openSUSE qui vient avec un client web et par son client en ligne de commande OSC.

La doc, un grand merci à [Sogal](https://www.alionet.org/showthread.php?33627-packaging-S-aider-pour-faire-des-RPM-de-qualit%E9-pour-notre-openSUSE) est en anglais, je vais donc m’efforcer à faire un tuto simple, clair et qui va à l'essentiel.

On commence par ce faire un compte chez [openSUSE Build Service](https://build.opensuse.org/), et ensuite on s'installe *OSC* sur notre distribution, alors vu que openSUSE font tout pour partager leurs connaissances, acquis et progrès, nous trouverons un paquet pour la plupart des grosses écuries comme Archlinux, Debian, Fedora, Mageia... Dans mon cas je ferais seulement pour openSUSE et peut être Debian par la suite.

Une fois qu'on a son compte sur le [openSUSE Build Service](https://build.opensuse.org/), on se met dans une console (terminal, konsole, ect...) et on va suivre [cette page](https://en.opensuse.org/openSUSE:Build_Service_Tutorial) que je retransmets sur cette page la méthode.

1. On configure sudo pour qu'on ait les droits d'utiliser les différents programmes:

    sudo /usr/sbin/visudo
    
2. Ajoutez la ligne suivante et remplacez l'espace réservé LOGIN avec votre nom de connexion:

    LOGIN    ALL = NOPASSWD: /usr/bin/build
    LOGIN    ALL = NOPASSWD: /usr/bin/osc

### Connexion et configuration ponctuelle du projet local ###

Au début, vous devez installer le client en ligne de commande sur votre machine. Vous pouvez trouver des paquets *osc* pour différentes distributions dans le dépôt de téléchargement de logiciels openSUSE-Tools (oui: il s'agit également d'un projet Build Service). Utilisez votre gestionnaire de paquets favori pour installer le paquet *osc*.

En supposant que vous utilisez openSUSE Leap, l'installation du paquet *osc* ressemble à:

    zypper in osc
    
Ou si vous préférer une version plus récente:

     zypper ar -r http://download.opensuse.org/repositories/openSUSE:/Tools/openSUSE_42.3/openSUSE:Tools.repo
     zypper in osc
     
Ensuite on va aller avec l'aide de `cd` dans le répertoire que vous souhaitez utiliser pour vos fichiers de projet. Ça sera votre *racine* de votre projet.

    cd <directory_to_contain_project_root>
    osc checkout home:<username>
    cd home:<username> 

Remplacez juste *username* par votre login.

- Vous serez invité à saisir votre nom d'utilisateur et votre mot de passe - ensuite, osc essaiera de récupérer les paquets dans votre projet home et de créer un nouveau répertoire appelé home: <nom d'utilisateur>.
- Vous pouvez éditer vos paramètres dans le fichier ~/.oscrc ou ~/.config/osc/oscrc.
- Si vous entrez un mauvais mot de passe, vous devez supprimer toute la section api pour le service avec un mot de passe erroné pour osc pour demander à nouveau le mot de passe.
- Si vous définissez plaintext_passwd = 0 et supprimez la section api, osc demande de nouveau le nom d'utilisateur et le mot de passe et stocke le mot de passe encodé en base64. Il peut être décodé facilement mais n'est pas vu en un coup d'œil.
- Si vous souhaitez utiliser plusieurs services de build (ou un service autre que https://api.opensuse.org), utilisez l'option -A. Vous pouvez raccourcir l'argument -A en définissant l'option aliases dans la section api. Vous pouvez également écrire un script my_buildservice en disant quelque chose comme exec osc -A https://api.my.build.server "$ @"

### Créer et télécharger des paquets ###

Vous pouvez utiliser votre projet home comme un "terrain de jeu" pour tester des paquets qui seront transférés à d'autres projets plus visibles si tout va bien.

Client Web: Sur le côté droit, cliquez sur "Home Project" pour ouvrir votre projet home, puis cliquez sur "Users" puis sur "Add user" pour vous ajouter en tant que responsable. Après cela, cliquez sur "créer un nouveau paquet" dans l'onglet des paquets. Vous devez remplir les trois champs de texte suivants: "Nom" (obligatoire), "Titre" et "Description". Utilisez simplement le nom du paquet comme "Nom", le résumé du paquet comme "Titre" et la description du paquet comme "Description".

Une fois le package créé, accédez à l'onglet "Sources" pour ajouter les fichiers de votre package. Vous devez télécharger le code source de votre package et au moins un fichier spec (voir également les instructions d'emballage).

Avec le client *OSC*, on lance une simple commande:

    osc meta pkg -e home:<utilisateur> <nomDuPaquet>
    
osc ouvre un modèle de fichier xml dans votre éditeur favori (basé sur la variable d'environnement EDITOR, mais traditionnellement "vi") et vous pouvez simplement ajouter les même renseignements (Nom, Titre, Description) décrits plus haut.

Maintenant tapez

    osc up

et vous obtiendrez un nouveau répertoire du nom de votre paquet. Pour ajouter des fichiers via la ligne de commande, 'cd' dans le nouveau répertoire, copiez les fichiers concernés (typiquement un fichier .tar.gz et les fichiers de support) et layoutz

    osc add *

cela va marquer les fichiers dans le répertoire pour le prochain envoi (submit). Pour envoyer les fichiers, tapez

    osc commit

    
### compiler votre paquet ###

Normalement votre paquet est programmé pour être compilé après qu'il soit envoyé ou que des fichiers aient changé. Si un paquet requis est recompilé, votre paquet est automatiquement recompilé, cela va de soit. Vous pouvez aussi enclencher manuellement une recompilation si vous en avez le besoin (mais s'il-vous-plaît ne le faites pas trop souvent au risque de consommer de l'énergie à d'autres paquets):

    osc rebuildpac <project> <package> [<repo> [<arch>]]

    
### Compiler votre paquet localement ###

Parfois il peut être plus rapide de compiler votre paquet sur votre machine locale que d'attendre les résultat de Build Service. osc supporte les compilations locales de votre paquet, pour autant que votre matériel le supporte (sur x86_64 on peut compiler pour i586 et x86_64, mais sur i586 seul i586 est possible).

    osc build <platform> <arch> <specfile> [--clean|--noinit]
    
Si vous démarrez la compilation en tant qu'utilisateur normal (bonne idée !), il vous sera demandé votre mot de passe root de la machine locale. Vous pouvez éviter cela si vous ajoutez votre utilisateur à '/etc/sudoers (voir plus haut).

pour exemple:

    ~/obs/home:user/project # osc build openSUSE_Leap_42.1 x86_64 project.spec
    
osc se connecte au serveur de référentiel OBS et télécharge tous les RPM nécessaires dans /var/tmp/osbuild-packagecache/plattform/repository/arch en tant que répertoire cache. Si vous voulez éviter le trafic réseau, il est possible de remplir préalablement le cache avec rpms à partir d'un DVD ou d'un iso. Pour cela, copiez le fichier rpms du DVD dans le répertoire cache.

osc créera un environnement chroot dans /var/tmp/build-root/ et démarrera la construction de votre paquet. Si vous n'avez que des modifications mineures, vous pouvez éviter la recréation de l'environnement de construction avec l'option --noinit. Si vous pensez que votre environnement chroot est endommagé, vous pouvez déclencher une reconstruction complète avec l'option --clean. Vous pouvez configurer le répertoire chroot; voir les commentaires dans votre fichier ~/.oscrc ou ~/.config/osc/oscrc.

osc refusera d'installer des paquets de projets sur lesquels votre système ne fait pas confiance. Cela peut se produire lorsque votre package est lié à un projet de développement et que votre système n'est pas configuré pour utiliser ce référentiel. Vous pouvez obtenir la clé GPG nécessaire en exécutant:

    sudo rpm --import - <<_END_KEY
    $(osc signkey offending-project)
    _END_KEY

Une fois que vos paquets sont construits dans cet environnement chroot, vous pouvez trouver les paquets résultants dans /var/tmp/build-root/home/abuild/rpmbuild/RPMS/ (anciennes versions de rpmbuild /usr/src/packages/RPMS/.

Si votre package utilise un service de téléchargement d'URL, vous devrez peut-être exécuter la commande suivante en premier:

    zypper ar -r http://download.opensuse.org/repositories/openSUSE:/Tools/openSUSE_42.3/openSUSE:Tools.repo

Le fichier journal complet de votre build local est stocké dans /var/tmp/build-root/.build.log.

### Corriger les erreurs dans le processus de construction local ###

#### Dépendances ####

Si vous obtenez une erreur de dépendance pendant votre construction, ajoutez une ligne contenant les dépendances de construction, comme:

    BuildRequires: cmake libkde4-devel

Dans ce cas, cmake et libkde4-devel seront installés avant la construction de votre paquet.

#### Installer les privilèges ####

Si vous obtenez un message d'erreur comme celui-ci:

    error: Bad exit status from /var/tmp/rpm-tmp.qrRAn2 (%install)
    
cela signifie que votre étape% d'installation a échoué (et que tous les autres se sont bien passés). Cela peut être dû à des privilèges d'écriture manquants si vous essayez d'installer au mauvais endroit (ce qui m'arrive fréquemment). Dans ce cas, ajoutez la commande make install suivante à votre fichier spec:

    make install DESTDIR=%buildroot
    
### Soumettez votre travail à OBS ###

Une fois que vous avez votre répertoire <package> comme vous le souhaitez, utilisez les commandes ci-dessous pour soumettre votre travail à OBS.

ajouter un nouveau fichier au package:
    
    osc add
    
retirer un fichier du paquet:

    osc rm
    
mettre à jour le journal des modifications (par exemple. * .changes):

    osc vc
    
envoyez vos fichiers mis à jour à OBS:

    osc commit
    
Sources: https://fr.opensuse.org/Build_Service/Tutoriel
https://en.opensuse.org/openSUSE:Build_Service_Tutorial
https://www.alionet.org/showthread.php?33627-packaging-S-aider-pour-faire-des-RPM-de-qualit%E9-pour-notre-openSUSE
