---
title: Handylinux; Debian plus simple qu'Ubuntu ! L'installation d'HandyLinux.
date: 2016-05-01 20:03
layout: post
---

<div class="chapo surlignable">

Dans le [précédent
article](http://passiongnulinux.tuxfamily.org/?p=13){.ref-post}, je
découvrais avec vous une distribution, la Handylinux, qui favorise
**l’accessibilité** pour tous et la **liberté** pour chacun
**d’évoluer** à son gré. Basée sur **Debian GNU/Linux** avec **XFCE**,
un environnement de bureau rapide, léger et stable. Aujourd’hui, nous
verrons ensemble son installation. Une grosse partie si ce n’est la
totalité est pompé directement dans la documentation de cette
distribution.  
<!--more-->
</p>
<div class="texte surlignable">

### Installateur Live comme la cousine Ubuntu {#outil_sommaire_0 .spip}

Le dvd d’installation de cette distribution est un live dvd, qui permet
d’utiliser/tester une distribution sur un ordinateur sans risques pour
vos données personnelles et qui permet aussi de tester la compatibilité
de votre matériel. HandyLinux est “compressée” dans un fichier spécial
(le squashfs.filesystem) et intégrée dans l’image ISO que vous avez
téléchargée. C’est ce fichier spécial qui est “décompressé” lors de
l’utilisation en Live qui sera copié sur votre disque dur lors de
l’installation. C’est au boot du dvd que l’on peut choisir entre tester
et installer Handylinux :

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L640xH480/syslinux_liv013e-9dc0a.png?1465243402){width="640"
height="480"}

Si on décide de lancer le live, notez que HandyLinux fonctionne plus
lentement en session Live qu’après installation. Que ce soit en live ou
apres installation nous avons droit a un joli accueil :

![](http://passiongnulinux.tuxfamily.org/spip/local/cache-vignettes/L500xH375/welcomepngw5d56f-b99cc.png?1465243402){width="500"
height="375"}

Peu importe, on verra ça plus tard, parlons plutôt de son installation,
pas grand-chose a dire, c’est du connue, c’est simple et efficace.  

### Installer HandyLinux en single-boot {#outil_sommaire_1 .spip}

<div>

Une [vidéo complète
d’installation](https://player.vimeo.com/video/122423367){.spip_out} est
disponible pour un aperçu d’une installation de base d’HandyLinux, ** 1
– Lorsque vous lancez handylinux depuis un DVD ou une clé USB,
choisissez “Installer Handylinux” depuis le menu d'accueil** :
<div>

[![menu de démarrage
handylinux](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/syslinux_install.png?w=600&tok=36a27b "menu de démarrage handylinux"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/syslinux_install.png?id=fr%3Ainstall "fr:install:syslinux_install.png"){.media}
**2 – L'installation démarre avec le choix du clavier, la détection du
support et du matériel. Vous n'avez rien à faire jusqu'à l'écran de
choix du nom de votre ordinateur** : [![choix du
clavier](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-01-clavier.png?w=600&tok=e343c3 "choix du clavier"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-01-clavier.png?id=fr%3Ainstall "fr:install:handy_install-01-clavier.png"){.media}
[![détection du
matériel](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-02-composants.png?w=600&tok=ebea80 "détection du matériel"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-02-composants.png?id=fr%3Ainstall "fr:install:handy_install-02-composants.png"){.media}
[![choix du nom
d'hôte](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-03-hostname.png?w=600&tok=ea779d "choix du nom d'hôte"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-03-hostname.png?id=fr%3Ainstall "fr:install:handy_install-03-hostname.png"){.media}
**3 – Puis renseignez votre nom complet et votre identifiant** (le nom
que vous utilisez pour vous connecter à votre système) : [![nom complet
de votre
utilisateur](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-04-username.png?w=600&tok=b35ab8 "nom complet de votre utilisateur"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-04-username.png?id=fr%3Ainstall "fr:install:handy_install-04-username.png"){.media}
[![identifiant utilisé pour vous
connecter](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-05-login.png?w=600&tok=ce23a2 "identifiant utilisé pour vous connecter"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-05-login.png?id=fr%3Ainstall "fr:install:handy_install-05-login.png"){.media}
**4 – Et votre mot de passe** (deux fois pour confirmer) : [![mot de
passe](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-06-password.png?w=600&tok=f2295a "mot de passe"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-06-password.png?id=fr%3Ainstall "fr:install:handy_install-06-password.png"){.media}
**5 – Démarrent ensuite la détection des disques durs et la phase de
partitionnement. Si vous débutez, je vous conseille le “*partitionnement
assisté*” qui va automatiquement utiliser la totalité de votre disque.
Si vous désirez préserver une partition de données ou utiliser plusieurs
systèmes d'exploitation, choisissez “*manuel*” et suivez la procédure
décrite dans le chapitre <span
class="curid">[multi-boot](https://handylinux.org/wiki/doku.php/fr/install#installer_handylinux_en_multi-boot "fr:install"){.wikilink1}</span>**
: [![schéma de
partitionnement](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-07-partition-methode.png?w=600&tok=8028a3 "schéma de partitionnement"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-07-partition-methode.png?id=fr%3Ainstall "fr:install:handy_install-07-partition-methode.png"){.media}
**6 – L'installeur vous demande de choisir le disque dur sur lequel sera
installé HandyLinux** : [![choix du disque
interne](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-08-partition-disque.png?w=600&tok=03dde6 "choix du disque interne"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-08-partition-disque.png?id=fr%3Ainstall "fr:install:handy_install-08-partition-disque.png"){.media}
**7 – L'écran de vérification des partitions s'affiche alors, vous
offrant la chance de modifier le partitionnement assisté** :
[![vérification des
partitions](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-09-partition-schema.png?w=600&tok=d63cf0 "vérification des partitions"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-09-partition-schema.png?id=fr%3Ainstall "fr:install:handy_install-09-partition-schema.png"){.media}
**8 – Puis s'affiche le dernier écran de confirmation avant le
partitionnement du disque sélectionné. <span class="wrap_em">*ATTENTION*
!! après cette étape, les données présentes sur le disque seront
effacées !!</span>** **Si vous souhaitez poursuivre l'installation, clic
sur “Oui” puis “Continuer”** : [![confirmation du
partitionnement](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-10-partition-confirm.png?w=600&tok=9c7d78 "confirmation du partitionnement"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-10-partition-confirm.png?id=fr%3Ainstall "fr:install:handy_install-10-partition-confirm.png"){.media}
**9 – Si vous avez confirmé l'étape précédente, le partitionnement est
appliqué et le système s'installe sur le disque** : [![installation -
copie des
données](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-11-copie_datas.png?w=600&tok=12851d "installation - copie des données"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-11-copie_datas.png?id=fr%3Ainstall "fr:install:handy_install-11-copie_datas.png"){.media}
**10 – Configuration du système après la copie des données. Vous n'avez
rien à faire** : [![gestion des
paquets](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-12-config.png?w=600&tok=baeacf "gestion des paquets"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-12-config.png?id=fr%3Ainstall "fr:install:handy_install-12-config.png"){.media}
**11 – L'installation de GRUB : choisissez le périphérique
d'installation** : [![installation de
GRUB](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-13-grub.png?w=600&tok=971b4c "installation de GRUB"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-13-grub.png?id=fr%3Ainstall "fr:install:handy_install-13-grub.png"){.media}
**12 – C'est alors la fin de l'installation avec la mise en place des
utilisateurs, des mots de passe et l'exécution du script de
post-installation** : [![message de fin
d'installation](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-14-finish.png?w=600&tok=b1186e "message de fin d'installation"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-14-finish.png?id=fr%3Ainstall "fr:install:handy_install-14-finish.png"){.media}
[![fin de
l'installation](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/handy_install-15-end.png?w=600&tok=680037 "fin de l'installation"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/handy_install-15-end.png?id=fr%3Ainstall "fr:install:handy_install-15-end.png"){.media}
**13 – Une fois l'installation terminée, votre ordinateur redémarre
automatiquement sur votre nouveau système HandyLinux et l'écran de GRUB
s'affiche** : [![redémarrage et
GRUB](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/grub.png?w=600&tok=35d05a "redémarrage et GRUB"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/grub.png?id=fr%3Ainstall "fr:install:grub.png"){.media}
**14 – HandyLinux se lance alors et vous parvenez à l'écran de connexion
géré par LightDM. Entrez votre identifiant et votre mot de passe** :
[![identifiant de
connexion](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/lightdm-identifiant.png?w=600&tok=da9460 "identifiant de connexion"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/lightdm-identifiant.png?id=fr%3Ainstall "fr:install:lightdm-identifiant.png"){.media}
[![mot de
passe](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/lightdm-password.png?w=600&tok=95e5f6 "mot de passe"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/lightdm-password.png?id=fr%3Ainstall "fr:install:lightdm-password.png"){.media}
<div class="wrap_center wrap_centeralign wrap_info plugin_wrap"
style="width: 90%;">

Avant la version 2.3 , la connexion était gérée par **slim** et
ressemblait à ça :

</div>

[![identifiant de
connexion](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/slim-identifiant.png?w=600&tok=2f0638 "identifiant de connexion"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/slim-identifiant.png?id=fr%3Ainstall "fr:install:slim-identifiant.png"){.media}
[![mot de
passe](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/slim-password.png?w=600&tok=d94273 "mot de passe"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/slim-password.png?id=fr%3Ainstall "fr:install:slim-password.png"){.media}
**15 – Et c'est parti pour votre aventure sur GNU/Linux !** :
[![Bienvenue sur
HandyLinux](https://handylinux.org/wiki/lib/exe/fetch.php/fr/install/welcome.png?w=600&tok=ac3a0d "Bienvenue sur HandyLinux"){.mediacenter
width="600"}](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/welcome.png?id=fr%3Ainstall "fr:install:welcome.png"){.media}
[Une fois authentifié, votre bureau s’affiche et la fenêtre de
présentation se
lance](https://handylinux.org/wiki/lib/exe/detail.php/fr/install/welcome.png?id=fr%3Abegin){.spip_out}.

-   **Si vous êtes débutant**, prenez dix secondes pour la lire car elle
    liste les principaux outils d’HandyLinux.
-   **Si vous êtes un grand débutant**, cliquez sur le bouton “je
    débute...” situé en bas de la fenêtre, en pressant le bouton gauche
    de votre souris. Votre navigateur internet ira ouvrir [une page
    d’initiation](https://handylinux.org/wiki/doku.php/fr/initiation){.spip_out}
    depuis votre système (pas besoin d’internet). Laissez-lui quelques
    secondes au premier lancement
    ![:)](http://passiongnulinux.tuxfamily.org/plugins/auto/couteau_suisse/v1.9.10/img/smileys/sourire.png ":)"){.no_image_filtrer
    .format_png width="19" height="19"} .

<div>

<div class="texte surlignable">

 Comme on peut voire, Handylinux est très simple et bien documenté. De
plus tout est fait pour aider le débutant comme des documents en ligne,
une documentation disponible dans le dossier documents de l’utilisateur,
un forum avec un fonctionnement inédit et aussi un développement
collégiale c’est a dire ce n’est pas uniquement les développeurs qui
décident mais tous les utilisateurs décident et votent pour
l’intégration d’une fonctionnalité. [Dans le prochain
article](http://passiongnulinux.tuxfamily.org/?p=59){.ref-post}, je
parlerais du pourquoi et du comment j’ai découvert ou plutôt j’ai décidé
de mettre une handylinux.  
Il y aura d’autres articles sur cette distribution.

</div>

Voir en ligne :
[install](https://handylinux.org/wiki/doku.php/fr/install){.spip_out}

</div>

</div>

</div>

</div>

</div>

 
