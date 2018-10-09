---
title: Firmware manquant pendant l'installation de debian.
date: 2016-06-03 12:37
layout: post
---

Le mot firmware, qui peut être traduit par le terme microcode (ou
microprogramme), fait référence à un programme intégré qui contrôle des
périphériques électroniques. Il n'y a pas de frontières précises entre
microprogramme et programme dans la mesure où les deux termes recouvrent
parfois des codes similaires. Habituellement, le terme microcode
(firmware) désigne un programme qui se charge des opérations de bas
niveau dans un périphérique, sans lesquels le périphérique ne pourrait
fonctionner... <small>(pour en savoir plus
[Wikipedia](https://en.wikipedia.org/wiki/fr%3AFirmware "WikiPedia"){.interwiki})</small>.  

Microcodes, Périphériques et Pilotes {#Microcodes.2C_P.2BAOk-riph.2BAOk-riques_et_Pilotes}
------------------------------------

 

De nombreux périphériques ont besoin d'un microcode pour fonctionner.
Historiquement, les microcodes étaient incorporés à la ROM ou à la
mémoire flash des périphériques, mais, de plus en plus souvent, ils
doivent être chargés dans le périphérique par le pilote au moment de
leur mise en route. <span id="line-15" class="anchor"></span>Certains de
ces microcodes sont libres et open-source, mais d'autres non ce qui fait
que vous devez ajouter les sources `non-free` et `contrib` à votre
fichier `/etc/apt/sources.list` ; voir
[sources.list(5)](http://manpages.debian.org/man/5/sources.list "DebianMan"){.interwiki}
et [Debian archive
basics](http://www.debian.org/doc/manuals/debian-reference/ch02#_debian_archive_basics){.http}
(Debian Reference) pour des informations complémentaires. <span
id="line-16" class="anchor"></span><span id="line-17"
class="anchor"></span>

<!--more-->

### le Firmware pendant l'installation {#le_Firmware_pendant_l.27installation}

 

Dans certains cas, le programme d'installation de Debian détecte la
nécessité de charger un microcode non-libre et demande à l'utilisateur
de charger le microcode afin de pouvoir achever l'installation, comme
par exemple les périphériques
[ipw2200](https://wiki.debian.org/ipw2200). <span id="line-20"
class="anchor"></span><span id="line-21" class="anchor"></span>

Avant de débuter l'installation d'un matériel qui ne vous est pas
familier, nous vous suggérons de télécharger l'archive compressée
([tarball](https://wiki.debian.org/tarball)) du microcode nécessaire à
l'installation et de le décompresser dans une répertoire nommé «
firmware » placé à la racine d'un support amovible. Quand l'installateur
démarre, il trouve automatiquement cette archive sur le support amovible
et installe le microcode de votre matériel s'il y en a besoin. Le lien
de téléchargement des microcodes correspondant à votre distribution
Debian est le suivant :
<http://cdimage.debian.org/cdimage/unofficial/non-free/firmware/>. <span
id="line-22" class="anchor"></span><span id="line-23"
class="anchor"></span>

Le microcode fourni sur le support amovible peut, dans certains cas, ne
pas être détecté (par exemple
[740503](https://bugs.debian.org/740503 "Open: #740503: debian-installer: check-missing-firmware does not work with a USB drive that contains a partition table"){.interwiki
.open-bug}). Pour corriger le problème, allez sur la console et montez
manuellement le support sur /media. <span id="line-24"
class="anchor"></span><span id="line-25" class="anchor"></span>

Autrement, il existe maintenant des versions d'Images CD « netinst » qui
incluent directement l'ensemble des paquets de microcodes non-libres :
voir
<http://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/>
<span id="line-26" class="anchor"></span><span id="line-27"
class="anchor"></span>

-   [NetbootFirmware](https://wiki.debian.org/DebianInstaller/NetbootFirmware) -
    Microcodes pour le Netbooting. <span id="line-28"
    class="anchor"></span>

Une fois que le réseau est configuré, le programme d'installation de
Debian peut aller chercher les microcodes dans les dépôts Debian. <span
id="line-29" class="anchor"></span><span id="line-30"
class="anchor"></span>

### Localisation des microcodes {#Localisation_des_microcodes}

 

#### Debian 8 « Jessie », Debian 7 « Wheezy », Debian 6.0 « Squeeze » {#Debian_8_.2BAKs_Jessie_.2BALs.2C_Debian_7_.2BAKs_Wheezy_.2BALs.2C_Debian_6.0_.2BAKs_Squeeze_.2BALs-}

 

Les microcodes proviennent des emplacements suivants (voir les fichiers
`/lib/udev/hotplug.functions` et `/lib/udev/firmware.agent`
d'[udev](https://packages.debian.org/udev "DebianPkg"){.interwiki}).
<span id="line-34" class="anchor"></span>

1.  `/lib/firmware/$(uname -r)` - Microcodes fournis par un paquet,
    spécifiques à un noyau. <span id="line-35" class="anchor"></span>

2.  `/lib/firmware/` - Microcodes fournis par un paquet, valides pour
    tous les noyaux. <span id="line-36" class="anchor"></span>

3.  `/usr/local/lib/firmware` - Emplacement des microcodes
    installés manuellement. <span id="line-37" class="anchor"></span>

4.  `/usr/lib/hotplug/firmware` - Microcodes fournis par un paquet,
    valides pour tous les noyaux. <span id="line-38"
    class="anchor"></span><span id="line-39" class="anchor"></span>

### Liste des microcodes du noyau Linux {#Liste_des_microcodes_du_noyau_Linux}

 

<div class="note">

<span id="line-1-1" class="anchor"></span>
Pour trouver le paquet qui fournit le fichier d'un microcode donné,
rendez-vous sur cette page : <span id="line-2-1"
class="anchor"></span><http://www.debian.org/distrib/packages#search_contents>

</div>

 

Voici la liste, générée automatiquement par le noyau linux
**3.2.0-4-686-pae** (Debian 3.2.41-2) de
[Wheezy](https://wiki.debian.org/DebianWheezy), des modules Linux qui
ont besoin d'un microcode pour fonctionner. Certains des microcodes ont
été empaquetés pour Debian (par exemple dans le paquet
[firmware-linux-nonfree](https://packages.debian.org/firmware-linux-nonfree "DebianPkg"){.interwiki}).
<span id="line-46" class="anchor"></span><span id="line-47"
class="anchor"></span>

Attention : cette liste peut ne pas être complète parce que le nom des
microcode ne peut pas toujours être extrait de façon fiable. <span
id="line-48" class="anchor"></span><span id="line-49"
class="anchor"></span>

<div id="Firmware-1.content" dir="ltr" lang="en">

<span id="Firmware-1.top" class="anchor"></span><span
id="Firmware-1.line-1" class="anchor"></span><span
id="Firmware-1.line-2" class="anchor"></span>
<div>

+--------------------------+--------------------------+--------------------------+
| 3c359.ko                 | *3Com 3C359 Velocity XL  | [3com/3C359.bin](https:/ |
|                          | Token Ring Adapter       | /packages.debian.org/fil |
|                          | Driver*                  | e%3A3com/3C359.bin "Debi |
|                          |                          | anPkg"){.interwiki}      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[AceNIC/3C985/GA620     | [acenic/tg1.bin](https:/ |
| id="Firmware-1.line-3"   | Gigabit Ethernet         | /wiki.debian.org/acenic) |
| class="anchor"></span>   | driver](https://wiki.deb | [acenic/tg2.bin](https:/ |
| acenic.ko                | ian.org/acenic)*         | /wiki.debian.org/acenic) |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [advansys/3550.bin](http |
| id="Firmware-1.line-4"   |                          | s://packages.debian.org/ |
| class="anchor"></span>   |                          | file%3Aadvansys/3550.bin |
| advansys.ko              |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [advansys/38C0800.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aadvansys/38C08 |
|                          |                          | 00.bin "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [advansys/38C1600.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aadvansys/38C16 |
|                          |                          | 00.bin "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [advansys/mcode.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Aadvansys/mcode.b |
|                          |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Adaptec aic94xx         | [aic94xx-seq.fw](https:/ |
| id="Firmware-1.line-5"   | SAS/SATA driver*         | /packages.debian.org/fil |
| class="anchor"></span>   |                          | e%3Aaic94xx-seq.fw "Debi |
| aic94xx.ko               |                          | anPkg"){.interwiki}      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Madge ATM Ambassador    | [atmsar11.fw](https://pa |
| id="Firmware-1.line-6"   | driver*                  | ckages.debian.org/file%3 |
| class="anchor"></span>   |                          | Aatmsar11.fw "DebianPkg" |
| ambassador.ko            |                          | ){.interwiki}            |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Atmel at76x USB        | [atmel\_at76c503-i3861.b |
| id="Firmware-1.line-7"   | Wireless LAN             | in](https://packages.deb |
| class="anchor"></span>   | Driver](https://wiki.deb | ian.org/file%3Aatmel_at7 |
| at76c50x-usb.ko          | ian.org/at76_usb)*       | 6c503-i3861.bin "DebianP |
|                          |                          | kg"){.interwiki}         |
|                          |                          | [atmel\_at76c503-i3863.b |
|                          |                          | in](https://packages.deb |
|                          |                          | ian.org/file%3Aatmel_at7 |
|                          |                          | 6c503-i3863.bin "DebianP |
|                          |                          | kg"){.interwiki}         |
|                          |                          | [atmel\_at76c503-rfmd-ac |
|                          |                          | c.bin](https://packages. |
|                          |                          | debian.org/file%3Aatmel_ |
|                          |                          | at76c503-rfmd-acc.bin "D |
|                          |                          | ebianPkg"){.interwiki}   |
|                          |                          | [atmel\_at76c503-rfmd.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Aatmel_at76 |
|                          |                          | c503-rfmd.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
|                          |                          | [atmel\_at76c505amx-rfmd |
|                          |                          | .bin](https://packages.d |
|                          |                          | ebian.org/file%3Aatmel_a |
|                          |                          | t76c505amx-rfmd.bin "Deb |
|                          |                          | ianPkg"){.interwiki}     |
|                          |                          | [atmel\_at76c505a-rfmd29 |
|                          |                          | 58.bin](https://packages |
|                          |                          | .debian.org/file%3Aatmel |
|                          |                          | _at76c505a-rfmd2958.bin  |
|                          |                          | "DebianPkg"){.interwiki} |
|                          |                          | [atmel\_at76c505-rfmd295 |
|                          |                          | 8.bin](https://packages. |
|                          |                          | debian.org/file%3Aatmel_ |
|                          |                          | at76c505-rfmd2958.bin "D |
|                          |                          | ebianPkg"){.interwiki}   |
|                          |                          | [atmel\_at76c505-rfmd.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Aatmel_at76 |
|                          |                          | c505-rfmd.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Atheros AR30xx firmware | [ath3k-1.fw](https://pac |
| id="Firmware-1.line-8"   | driver*                  | kages.debian.org/file%3A |
| class="anchor"></span>   |                          | ath3k-1.fw "DebianPkg"){ |
| ath3k.ko                 |                          | .interwiki}              |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Atheros driver 802.11n | [htc\_7010.fw](https://p |
| id="Firmware-1.line-9"   | HTC based wireless       | ackages.debian.org/file% |
| class="anchor"></span>   | devices](https://wiki.de | 3Ahtc_7010.fw "DebianPkg |
| ath9k\_htc.ko            | bian.org/ath9k_htc)*     | "){.interwiki}           |
|                          |                          | [htc\_9271.fw](https://p |
|                          |                          | ackages.debian.org/file% |
|                          |                          | 3Ahtc_9271.fw "DebianPkg |
|                          |                          | "){.interwiki}           |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Support for Atmel      | [atmel\_at76c502\_3com.b |
| id="Firmware-1.line-10"  | at76c50x 802.11 wireless | in](https://packages.deb |
| class="anchor"></span>   | ethernet                 | ian.org/file%3Aatmel_at7 |
| atmel.ko                 | cards.](https://wiki.deb | 6c502_3com.bin "DebianPk |
|                          | ian.org/atmel_cs)*       | g"){.interwiki}          |
|                          |                          | [atmel\_at76c502\_3com-w |
|                          |                          | pa.bin](https://packages |
|                          |                          | .debian.org/file%3Aatmel |
|                          |                          | _at76c502_3com-wpa.bin " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [atmel\_at76c502.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aatmel_at76c502. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [atmel\_at76c502d.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aatmel_at76c502 |
|                          |                          | d.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [atmel\_at76c502d-wpa.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Aatmel_at76 |
|                          |                          | c502d-wpa.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
|                          |                          | [atmel\_at76c502e.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aatmel_at76c502 |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [atmel\_at76c502e-wpa.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Aatmel_at76 |
|                          |                          | c502e-wpa.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
|                          |                          | [atmel\_at76c502-wpa.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aatmel_at76c |
|                          |                          | 502-wpa.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [atmel\_at76c504\_2958.b |
|                          |                          | in](https://packages.deb |
|                          |                          | ian.org/file%3Aatmel_at7 |
|                          |                          | 6c504_2958.bin "DebianPk |
|                          |                          | g"){.interwiki}          |
|                          |                          | [atmel\_at76c504\_2958-w |
|                          |                          | pa.bin](https://packages |
|                          |                          | .debian.org/file%3Aatmel |
|                          |                          | _at76c504_2958-wpa.bin " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [atmel\_at76c504a\_2958. |
|                          |                          | bin](https://packages.de |
|                          |                          | bian.org/file%3Aatmel_at |
|                          |                          | 76c504a_2958.bin "Debian |
|                          |                          | Pkg"){.interwiki}        |
|                          |                          | [atmel\_at76c504a\_2958- |
|                          |                          | wpa.bin](https://package |
|                          |                          | s.debian.org/file%3Aatme |
|                          |                          | l_at76c504a_2958-wpa.bin |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [atmel\_at76c504.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aatmel_at76c504. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [atmel\_at76c504-wpa.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aatmel_at76c |
|                          |                          | 504-wpa.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [atmel\_at76c506.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aatmel_at76c506. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [atmel\_at76c506-wpa.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aatmel_at76c |
|                          |                          | 506-wpa.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Broadcom B43 wireless  | [b43/ucode11.fw](https:/ |
| id="Firmware-1.line-11"  | driver](https://wiki.deb | /wiki.debian.org/bcm43xx |
| class="anchor"></span>   | ian.org/bcm43xx)*        | )                        |
| b43.ko                   |                          | [b43/ucode13.fw](https:/ |
|                          |                          | /wiki.debian.org/bcm43xx |
|                          |                          | )                        |
|                          |                          | [b43/ucode14.fw](https:/ |
|                          |                          | /wiki.debian.org/bcm43xx |
|                          |                          | )                        |
|                          |                          | [b43/ucode15.fw](https:/ |
|                          |                          | /wiki.debian.org/bcm43xx |
|                          |                          | )                        |
|                          |                          | [b43/ucode16\_mimo.fw](h |
|                          |                          | ttps://wiki.debian.org/b |
|                          |                          | cm43xx)                  |
|                          |                          | [b43/ucode5.fw](https:// |
|                          |                          | wiki.debian.org/bcm43xx) |
|                          |                          | [b43/ucode9.fw](https:// |
|                          |                          | wiki.debian.org/bcm43xx) |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Broadcom B43legacy     | [b43legacy/ucode2.fw](ht |
| id="Firmware-1.line-12"  | wireless                 | tps://wiki.debian.org/bc |
| class="anchor"></span>   | driver](https://wiki.deb | m43xx)                   |
| b43legacy.ko             | ian.org/bcm43xx)*        | [b43legacy/ucode4.fw](ht |
|                          |                          | tps://wiki.debian.org/bc |
|                          |                          | m43xx)                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Broadcom Blutonium      | [BCM2033-FW.bin](https:/ |
| id="Firmware-1.line-13"  | firmware driver ver 1.2* | /packages.debian.org/fil |
| class="anchor"></span>   |                          | e%3ABCM2033-FW.bin "Debi |
| bcm203x.ko               |                          | anPkg"){.interwiki}      |
|                          |                          | [BCM2033-MD.hex](https:/ |
|                          |                          | /packages.debian.org/fil |
|                          |                          | e%3ABCM2033-MD.hex "Debi |
|                          |                          | anPkg"){.interwiki}      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Brocade Fibre Channel   | [cbfw.bin](https://packa |
| id="Firmware-1.line-14"  | HBA Driver fcpim*        | ges.debian.org/file%3Acb |
| class="anchor"></span>   |                          | fw.bin "DebianPkg"){.int |
| bfa.ko                   |                          | erwiki}                  |
|                          |                          | [ct2fw.bin](https://pack |
|                          |                          | ages.debian.org/file%3Ac |
|                          |                          | t2fw.bin "DebianPkg"){.i |
|                          |                          | nterwiki}                |
|                          |                          | [ctfw.bin](https://packa |
|                          |                          | ges.debian.org/file%3Act |
|                          |                          | fw.bin "DebianPkg"){.int |
|                          |                          | erwiki}                  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *BlueFRITZ! USB driver   | [bfubase.frm](https://pa |
| id="Firmware-1.line-15"  | ver 1.2*                 | ckages.debian.org/file%3 |
| class="anchor"></span>   |                          | Abfubase.frm "DebianPkg" |
| bfusb.ko                 |                          | ){.interwiki}            |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Brocade 10G PCIe        | [ct2fw.bin](https://pack |
| id="Firmware-1.line-16"  | Ethernet driver*         | ages.debian.org/file%3Ac |
| class="anchor"></span>   |                          | t2fw.bin "DebianPkg"){.i |
| bna.ko                   |                          | nterwiki}                |
|                          |                          | [ctfw.bin](https://packa |
|                          |                          | ges.debian.org/file%3Act |
|                          |                          | fw.bin "DebianPkg"){.int |
|                          |                          | erwiki}                  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Broadcom NetXtreme II   | [bnx2/bnx2-mips-06-6.2.1 |
| id="Firmware-1.line-17"  | BCM5706/5708/5709/5716   | .fw](https://packages.de |
| class="anchor"></span>   | Driver*                  | bian.org/file%3Abnx2/bnx |
| bnx2.ko                  |                          | 2-mips-06-6.2.1.fw "Debi |
|                          |                          | anPkg"){.interwiki}      |
|                          |                          | [bnx2/bnx2-mips-09-6.2.1 |
|                          |                          | a.fw](https://packages.d |
|                          |                          | ebian.org/file%3Abnx2/bn |
|                          |                          | x2-mips-09-6.2.1a.fw "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [bnx2/bnx2-rv2p-06-6.0.1 |
|                          |                          | 5.fw](https://packages.d |
|                          |                          | ebian.org/file%3Abnx2/bn |
|                          |                          | x2-rv2p-06-6.0.15.fw "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [bnx2/bnx2-rv2p-09-6.0.1 |
|                          |                          | 7.fw](https://packages.d |
|                          |                          | ebian.org/file%3Abnx2/bn |
|                          |                          | x2-rv2p-09-6.0.17.fw "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [bnx2/bnx2-rv2p-09ax-6.0 |
|                          |                          | .17.fw](https://packages |
|                          |                          | .debian.org/file%3Abnx2/ |
|                          |                          | bnx2-rv2p-09ax-6.0.17.fw |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Broadcom NetXtreme II   | [bnx2x/bnx2x-e1-7.0.29.0 |
| id="Firmware-1.line-18"  | BCM57710/57711/57711E/57 | .fw](https://packages.de |
| class="anchor"></span>   | 712/57712\_MF/57800/5780 | bian.org/file%3Abnx2x/bn |
| bnx2x.ko                 | 0\_MF/57810/57810\_MF/57 | x2x-e1-7.0.29.0.fw "Debi |
|                          | 840/57840\_MF            | anPkg"){.interwiki}      |
|                          | Driver*                  | [bnx2x/bnx2x-e1h-7.0.29. |
|                          |                          | 0.fw](https://packages.d |
|                          |                          | ebian.org/file%3Abnx2x/b |
|                          |                          | nx2x-e1h-7.0.29.0.fw "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [bnx2x/bnx2x-e2-7.0.29.0 |
|                          |                          | .fw](https://packages.de |
|                          |                          | bian.org/file%3Abnx2x/bn |
|                          |                          | x2x-e2-7.0.29.0.fw "Debi |
|                          |                          | anPkg"){.interwiki}      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Bluetooth driver for    | [BT3CPCC.bin](https://pa |
| id="Firmware-1.line-19"  | the 3Com Bluetooth       | ckages.debian.org/file%3 |
| class="anchor"></span>   | PCMCIA card*             | ABT3CPCC.bin "DebianPkg" |
| bt3c\_cs.ko              |                          | ){.interwiki}            |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Marvell BT-over-SDIO    | [mrvl/sd8787\_uapsta.bin |
| id="Firmware-1.line-20"  | driver ver 1.0*          | ](https://packages.debia |
| class="anchor"></span>   |                          | n.org/file%3Amrvl/sd8787 |
| btmrvl\_sdio.ko          |                          | _uapsta.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [mrvl/sd8797\_uapsta.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Amrvl/sd8797 |
|                          |                          | _uapsta.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [sd8688.bin](https://pac |
|                          |                          | kages.debian.org/file%3A |
|                          |                          | sd8688.bin "DebianPkg"){ |
|                          |                          | .interwiki}              |
|                          |                          | [sd8688\_helper.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Asd8688_helper.bi |
|                          |                          | n "DebianPkg"){.interwik |
|                          |                          | i}                       |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Atheros AR9170 802.11n | [carl9170-1.fw](https:// |
| id="Firmware-1.line-21"  | USB                      | packages.debian.org/file |
| class="anchor"></span>   | wireless](https://wiki.d | %3Acarl9170-1.fw "Debian |
| carl9170.ko              | ebian.org/carl9170)*     | Pkg"){.interwiki}        |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Sun Cassini(+) ethernet | [sun/cassini.bin](https: |
| id="Firmware-1.line-22"  | driver*                  | //packages.debian.org/fi |
| class="anchor"></span>   |                          | le%3Asun/cassini.bin "De |
| cassini.ko               |                          | bianPkg"){.interwiki}    |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Chelsio T3 Network      | [cxgb3/ael2005\_opt\_edc |
| id="Firmware-1.line-23"  | Driver*                  | .bin](https://packages.d |
| class="anchor"></span>   |                          | ebian.org/file%3Acxgb3/a |
| cxgb3.ko                 |                          | el2005_opt_edc.bin "Debi |
|                          |                          | anPkg"){.interwiki}      |
|                          |                          | [cxgb3/ael2005\_twx\_edc |
|                          |                          | .bin](https://packages.d |
|                          |                          | ebian.org/file%3Acxgb3/a |
|                          |                          | el2005_twx_edc.bin "Debi |
|                          |                          | anPkg"){.interwiki}      |
|                          |                          | [cxgb3/ael2020\_twx\_edc |
|                          |                          | .bin](https://packages.d |
|                          |                          | ebian.org/file%3Acxgb3/a |
|                          |                          | el2020_twx_edc.bin "Debi |
|                          |                          | anPkg"){.interwiki}      |
|                          |                          | [cxgb3/t3b\_psram-1.1.0. |
|                          |                          | bin](https://packages.de |
|                          |                          | bian.org/file%3Acxgb3/t3 |
|                          |                          | b_psram-1.1.0.bin "Debia |
|                          |                          | nPkg"){.interwiki}       |
|                          |                          | [cxgb3/t3c\_psram-1.1.0. |
|                          |                          | bin](https://packages.de |
|                          |                          | bian.org/file%3Acxgb3/t3 |
|                          |                          | c_psram-1.1.0.bin "Debia |
|                          |                          | nPkg"){.interwiki}       |
|                          |                          | [cxgb3/t3fw-7.10.0.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Acxgb3/t3fw-7. |
|                          |                          | 10.0.bin "DebianPkg"){.i |
|                          |                          | nterwiki}                |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Chelsio T4 Network      | [cxgb4/t4fw.bin](https:/ |
| id="Firmware-1.line-24"  | Driver*                  | /packages.debian.org/fil |
| class="anchor"></span>   |                          | e%3Acxgb4/t4fw.bin "Debi |
| cxgb4.ko                 |                          | anPkg"){.interwiki}      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [cyzfirm.bin](https://pa |
| id="Firmware-1.line-25"  |                          | ckages.debian.org/file%3 |
| class="anchor"></span>   |                          | Acyzfirm.bin "DebianPkg" |
| cyclades.ko              |                          | ){.interwiki}            |
+--------------------------+--------------------------+--------------------------+
| <span                    | *driver for the SAA7146  | [av7110/bootcode.bin](ht |
| id="Firmware-1.line-26"  | based AV110 PCI DVB      | tps://packages.debian.or |
| class="anchor"></span>   | cards by Siemens,        | g/file%3Aav7110/bootcode |
| dvb-ttpci.ko             | Technotrend, Hauppauge*  | .bin "DebianPkg"){.inter |
|                          |                          | wiki}                    |
+--------------------------+--------------------------+--------------------------+
| <span                    | *TTUSB DVB Driver*       | [ttusb-budget/dspbootcod |
| id="Firmware-1.line-27"  |                          | e.bin](https://packages. |
| class="anchor"></span>   |                          | debian.org/file%3Attusb- |
| dvb-ttusb-budget.ko      |                          | budget/dspbootcode.bin " |
|                          |                          | DebianPkg"){.interwiki}  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Intel(R) PRO/100        | [e100/d101m\_ucode.bin]( |
| id="Firmware-1.line-28"  | Network Driver*          | https://packages.debian. |
| class="anchor"></span>   |                          | org/file%3Ae100/d101m_uc |
| e100.ko                  |                          | ode.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [e100/d101s\_ucode.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Ae100/d101s_uc |
|                          |                          | ode.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [e100/d102e\_ucode.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Ae100/d102e_uc |
|                          |                          | ode.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Emagic EMI 2|6 firmware | [emi26/bitstream.fw](htt |
| id="Firmware-1.line-29"  | loader.*                 | ps://packages.debian.org |
| class="anchor"></span>   |                          | /file%3Aemi26/bitstream. |
| emi26.ko                 |                          | fw "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [emi26/firmware.fw](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Aemi26/firmware.fw |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [emi26/loader.fw](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Aemi26/loader.fw "De |
|                          |                          | bianPkg"){.interwiki}    |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Emagic EMI 6|2m         | [emi62/bitstream.fw](htt |
| id="Firmware-1.line-30"  | firmware loader.*        | ps://packages.debian.org |
| class="anchor"></span>   |                          | /file%3Aemi62/bitstream. |
| emi62.ko                 |                          | fw "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [emi62/loader.fw](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Aemi62/loader.fw "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [emi62/spdif.fw](https:/ |
|                          |                          | /packages.debian.org/fil |
|                          |                          | e%3Aemi62/spdif.fw "Debi |
|                          |                          | anPkg"){.interwiki}      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *FORE Systems            | [pca200e\_ecd.bin2](http |
| id="Firmware-1.line-31"  | 200E-series ATM driver - | s://packages.debian.org/ |
| class="anchor"></span>   | version 0.3e*            | file%3Apca200e_ecd.bin2  |
| fore\_200e.ko            |                          | "DebianPkg"){.interwiki} |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Intel Wireless UWB Link | [i1480-phy-0.0.bin](http |
| id="Firmware-1.line-32"  | 1480 firmware uploader   | s://packages.debian.org/ |
| class="anchor"></span>   | for USB*                 | file%3Ai1480-phy-0.0.bin |
| i1480-dfu-usb.ko         |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [i1480-pre-phy-0.0.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Ai1480-pre-phy |
|                          |                          | -0.0.bin "DebianPkg"){.i |
|                          |                          | nterwiki}                |
|                          |                          | [i1480-usb-0.0.bin](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Ai1480-usb-0.0.bin |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Driver for USB based    | [i2400m-fw-usb-1.5.sbcf] |
| id="Firmware-1.line-33"  | Intel Wireless WiMAX     | (https://packages.debian |
| class="anchor"></span>   | Connection 2400M (5x50 & | .org/file%3Ai2400m-fw-us |
| i2400m-usb.ko            | 6050)*                   | b-1.5.sbcf "DebianPkg"){ |
|                          |                          | .interwiki}              |
|                          |                          | [i6050-fw-usb-1.5.sbcf]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Ai6050-fw-usb- |
|                          |                          | 1.5.sbcf "DebianPkg"){.i |
|                          |                          | nterwiki}                |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Edgeport USB Serial     | [edgeport/boot2.fw](http |
| id="Firmware-1.line-34"  | Driver*                  | s://packages.debian.org/ |
| class="anchor"></span>   |                          | file%3Aedgeport/boot2.fw |
| io\_edgeport.ko          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [edgeport/boot.fw](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Aedgeport/boot.fw " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [edgeport/down2.fw](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Aedgeport/down2.fw |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [edgeport/down.fw](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Aedgeport/down.fw " |
|                          |                          | DebianPkg"){.interwiki}  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Edgeport USB Serial     | [edgeport/down3.bin](htt |
| id="Firmware-1.line-35"  | Driver*                  | ps://packages.debian.org |
| class="anchor"></span>   |                          | /file%3Aedgeport/down3.b |
| io\_ti.ko                |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Intel(R) PRO/Wireless  | [ipw2100-1.3.fw](https:/ |
| id="Firmware-1.line-36"  | 2100 Network             | /packages.debian.org/fil |
| class="anchor"></span>   | Driver](https://wiki.deb | e%3Aipw2100-1.3.fw "Debi |
| ipw2100.ko               | ian.org/ipw2200)*        | anPkg"){.interwiki}      |
|                          |                          | [ipw2100-1.3-i.fw](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Aipw2100-1.3-i.fw " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [ipw2100-1.3-p.fw](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Aipw2100-1.3-p.fw " |
|                          |                          | DebianPkg"){.interwiki}  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Intel(R) PRO/Wireless  | [ipw2200-bss.fw](https:/ |
| id="Firmware-1.line-37"  | 2200/2915 Network        | /packages.debian.org/fil |
| class="anchor"></span>   | Driver](https://wiki.deb | e%3Aipw2200-bss.fw "Debi |
| ipw2200.ko               | ian.org/ipw2200)*        | anPkg"){.interwiki}      |
|                          |                          | [ipw2200-ibss.fw](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Aipw2200-ibss.fw "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [ipw2200-sniffer.fw](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Aipw2200-sniffer. |
|                          |                          | fw "DebianPkg"){.interwi |
|                          |                          | ki}                      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [isci/isci\_firmware.bin |
| id="Firmware-1.line-38"  |                          | ](https://packages.debia |
| class="anchor"></span>   |                          | n.org/file%3Aisci/isci_f |
| isci.ko                  |                          | irmware.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [isight.fw](https://pack |
| id="Firmware-1.line-39"  |                          | ages.debian.org/file%3Ai |
| class="anchor"></span>   |                          | sight.fw "DebianPkg"){.i |
| isight\_firmware.ko      |                          | nterwiki}                |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Intel(R) PRO/Wireless  | [iwlwifi-3945-2.ucode](h |
| id="Firmware-1.line-40"  | 3945ABG/BG Network       | ttps://packages.debian.o |
| class="anchor"></span>   | Connection driver for    | rg/file%3Aiwlwifi-3945-2 |
| iwl3945.ko               | Linux](https://wiki.debi | .ucode "DebianPkg"){.int |
|                          | an.org/iwlegacy)*        | erwiki}                  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Intel(R) Wireless WiFi | [iwlwifi-4965-2.ucode](h |
| id="Firmware-1.line-41"  | 4965 driver for          | ttps://packages.debian.o |
| class="anchor"></span>   | Linux](https://wiki.debi | rg/file%3Aiwlwifi-4965-2 |
| iwl4965.ko               | an.org/iwlegacy)*        | .ucode "DebianPkg"){.int |
|                          |                          | erwiki}                  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Intel(R) Wireless WiFi | [iwlwifi-1000-5.ucode](h |
| id="Firmware-1.line-42"  | Link AGN driver for      | ttps://packages.debian.o |
| class="anchor"></span>   | Linux](https://wiki.debi | rg/file%3Aiwlwifi-1000-5 |
| iwlwifi.ko               | an.org/iwlwifi)*         | .ucode "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [iwlwifi-100-5.ucode](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aiwlwifi-100-5.u |
|                          |                          | code "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [iwlwifi-105-6.ucode](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aiwlwifi-105-6.u |
|                          |                          | code "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [iwlwifi-135-6.ucode](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aiwlwifi-135-6.u |
|                          |                          | code "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [iwlwifi-2000-6.ucode](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aiwlwifi-2000-6 |
|                          |                          | .ucode "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [iwlwifi-2030-6.ucode](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aiwlwifi-2030-6 |
|                          |                          | .ucode "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [iwlwifi-5000-5.ucode](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aiwlwifi-5000-5 |
|                          |                          | .ucode "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [iwlwifi-5150-2.ucode](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aiwlwifi-5150-2 |
|                          |                          | .ucode "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [iwlwifi-6000-4.ucode](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aiwlwifi-6000-4 |
|                          |                          | .ucode "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [iwlwifi-6000g2a-5.ucode |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aiwlwifi-600 |
|                          |                          | 0g2a-5.ucode "DebianPkg" |
|                          |                          | ){.interwiki}            |
|                          |                          | [iwlwifi-6000g2b-6.ucode |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aiwlwifi-600 |
|                          |                          | 0g2b-6.ucode "DebianPkg" |
|                          |                          | ){.interwiki}            |
|                          |                          | [iwlwifi-6050-5.ucode](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aiwlwifi-6050-5 |
|                          |                          | .ucode "DebianPkg"){.int |
|                          |                          | erwiki}                  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Intel(R) IWMC 3200 Top  | [iwmc3200top.1.fw](https |
| id="Firmware-1.line-43"  | Driver*                  | ://packages.debian.org/f |
| class="anchor"></span>   |                          | ile%3Aiwmc3200top.1.fw " |
| iwmc3200top.ko           |                          | DebianPkg"){.interwiki}  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [iwmc3200wifi-calib-sdio |
| id="Firmware-1.line-44"  |                          | .bin](https://packages.d |
| class="anchor"></span>   |                          | ebian.org/file%3Aiwmc320 |
| iwmc3200wifi.ko          |                          | 0wifi-calib-sdio.bin "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [iwmc3200wifi-lmac-sdio. |
|                          |                          | bin](https://packages.de |
|                          |                          | bian.org/file%3Aiwmc3200 |
|                          |                          | wifi-lmac-sdio.bin "Debi |
|                          |                          | anPkg"){.interwiki}      |
|                          |                          | [iwmc3200wifi-umac-sdio. |
|                          |                          | bin](https://packages.de |
|                          |                          | bian.org/file%3Aiwmc3200 |
|                          |                          | wifi-umac-sdio.bin "Debi |
|                          |                          | anPkg"){.interwiki}      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Comedi low-level        | [comedi/jr3pci.idm](http |
| id="Firmware-1.line-45"  | driver*                  | s://packages.debian.org/ |
| class="anchor"></span>   |                          | file%3Acomedi/jr3pci.idm |
| jr3\_pci.ko              |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
+--------------------------+--------------------------+--------------------------+
| <span                    | *KL5USB101 USB Ethernet  | [kaweth/new\_code.bin](h |
| id="Firmware-1.line-46"  | driver*                  | ttps://packages.debian.o |
| class="anchor"></span>   |                          | rg/file%3Akaweth/new_cod |
| kaweth.ko                |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [kaweth/new\_code\_fix.b |
|                          |                          | in](https://packages.deb |
|                          |                          | ian.org/file%3Akaweth/ne |
|                          |                          | w_code_fix.bin "DebianPk |
|                          |                          | g"){.interwiki}          |
|                          |                          | [kaweth/trigger\_code.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Akaweth/tri |
|                          |                          | gger_code.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
|                          |                          | [kaweth/trigger\_code\_f |
|                          |                          | ix.bin](https://packages |
|                          |                          | .debian.org/file%3Akawet |
|                          |                          | h/trigger_code_fix.bin " |
|                          |                          | DebianPkg"){.interwiki}  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Keyspan USB to Serial   | [keyspan/mpr.fw](https:/ |
| id="Firmware-1.line-47"  | Converter Driver*        | /packages.debian.org/fil |
| class="anchor"></span>   |                          | e%3Akeyspan/mpr.fw "Debi |
| keyspan.ko               |                          | anPkg"){.interwiki}      |
|                          |                          | [keyspan/usa18x.fw](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Akeyspan/usa18x.fw |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [keyspan/usa19.fw](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Akeyspan/usa19.fw " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [keyspan/usa19qi.fw](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Akeyspan/usa19qi. |
|                          |                          | fw "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [keyspan/usa19qw.fw](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Akeyspan/usa19qw. |
|                          |                          | fw "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [keyspan/usa19w.fw](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Akeyspan/usa19w.fw |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [keyspan/usa28.fw](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Akeyspan/usa28.fw " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [keyspan/usa28xa.fw](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Akeyspan/usa28xa. |
|                          |                          | fw "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [keyspan/usa28xb.fw](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Akeyspan/usa28xb. |
|                          |                          | fw "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [keyspan/usa28x.fw](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Akeyspan/usa28x.fw |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [keyspan/usa49w.fw](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Akeyspan/usa49w.fw |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [keyspan/usa49wlc.fw](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Akeyspan/usa49wl |
|                          |                          | c.fw "DebianPkg"){.inter |
|                          |                          | wiki}                    |
+--------------------------+--------------------------+--------------------------+
| <span                    | *USB Keyspan PDA         | [keyspan\_pda/keyspan\_p |
| id="Firmware-1.line-48"  | Converter driver*        | da.fw](https://packages. |
| class="anchor"></span>   |                          | debian.org/file%3Akeyspa |
| keyspan\_pda.ko          |                          | n_pda/keyspan_pda.fw "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [keyspan\_pda/xircom\_pg |
|                          |                          | s.fw](https://packages.d |
|                          |                          | ebian.org/file%3Akeyspan |
|                          |                          | _pda/xircom_pgs.fw "Debi |
|                          |                          | anPkg"){.interwiki}      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Driver for Marvell     | [libertas/cf8305.bin](ht |
| id="Firmware-1.line-49"  | 83xx compact flash WLAN  | tps://packages.debian.or |
| class="anchor"></span>   | cards](https://wiki.debi | g/file%3Alibertas/cf8305 |
| libertas\_cs.ko          | an.org/libertas)*        | .bin "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [libertas/cf8381.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Alibertas/cf8381 |
|                          |                          | .bin "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [libertas/cf8381\_helper |
|                          |                          | .bin](https://packages.d |
|                          |                          | ebian.org/file%3Aliberta |
|                          |                          | s/cf8381_helper.bin "Deb |
|                          |                          | ianPkg"){.interwiki}     |
|                          |                          | [libertas/cf8385.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Alibertas/cf8385 |
|                          |                          | .bin "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [libertas/cf8385\_helper |
|                          |                          | .bin](https://packages.d |
|                          |                          | ebian.org/file%3Aliberta |
|                          |                          | s/cf8385_helper.bin "Deb |
|                          |                          | ianPkg"){.interwiki}     |
|                          |                          | [libertas\_cs.fw](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Alibertas_cs.fw "Deb |
|                          |                          | ianPkg"){.interwiki}     |
|                          |                          | [libertas\_cs\_helper.fw |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Alibertas_cs |
|                          |                          | _helper.fw "DebianPkg"){ |
|                          |                          | .interwiki}              |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Libertas SDIO WLAN     | [libertas/sd8385.bin](ht |
| id="Firmware-1.line-50"  | Driver](https://wiki.deb | tps://packages.debian.or |
| class="anchor"></span>   | ian.org/libertas)*       | g/file%3Alibertas/sd8385 |
| libertas\_sdio.ko        |                          | .bin "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [libertas/sd8385\_helper |
|                          |                          | .bin](https://packages.d |
|                          |                          | ebian.org/file%3Aliberta |
|                          |                          | s/sd8385_helper.bin "Deb |
|                          |                          | ianPkg"){.interwiki}     |
|                          |                          | [libertas/sd8686\_v8.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Alibertas/sd |
|                          |                          | 8686_v8.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [libertas/sd8686\_v8\_he |
|                          |                          | lper.bin](https://packag |
|                          |                          | es.debian.org/file%3Alib |
|                          |                          | ertas/sd8686_v8_helper.b |
|                          |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [libertas/sd8686\_v9.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Alibertas/sd |
|                          |                          | 8686_v9.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [libertas/sd8686\_v9\_he |
|                          |                          | lper.bin](https://packag |
|                          |                          | es.debian.org/file%3Alib |
|                          |                          | ertas/sd8686_v9_helper.b |
|                          |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [libertas/sd8688.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Alibertas/sd8688 |
|                          |                          | .bin "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [libertas/sd8688\_helper |
|                          |                          | .bin](https://packages.d |
|                          |                          | ebian.org/file%3Aliberta |
|                          |                          | s/sd8688_helper.bin "Deb |
|                          |                          | ianPkg"){.interwiki}     |
|                          |                          | [sd8385.bin](https://pac |
|                          |                          | kages.debian.org/file%3A |
|                          |                          | sd8385.bin "DebianPkg"){ |
|                          |                          | .interwiki}              |
|                          |                          | [sd8385\_helper.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Asd8385_helper.bi |
|                          |                          | n "DebianPkg"){.interwik |
|                          |                          | i}                       |
|                          |                          | [sd8686.bin](https://pac |
|                          |                          | kages.debian.org/file%3A |
|                          |                          | sd8686.bin "DebianPkg"){ |
|                          |                          | .interwiki}              |
|                          |                          | [sd8686\_helper.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Asd8686_helper.bi |
|                          |                          | n "DebianPkg"){.interwik |
|                          |                          | i}                       |
|                          |                          | [sd8688.bin](https://pac |
|                          |                          | kages.debian.org/file%3A |
|                          |                          | sd8688.bin "DebianPkg"){ |
|                          |                          | .interwiki}              |
|                          |                          | [sd8688\_helper.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Asd8688_helper.bi |
|                          |                          | n "DebianPkg"){.interwik |
|                          |                          | i}                       |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Libertas SPI WLAN      | [libertas/gspi8385.bin]( |
| id="Firmware-1.line-51"  | Driver](https://wiki.deb | https://packages.debian. |
| class="anchor"></span>   | ian.org/libertas)*       | org/file%3Alibertas/gspi |
| libertas\_spi.ko         |                          | 8385.bin "DebianPkg"){.i |
|                          |                          | nterwiki}                |
|                          |                          | [libertas/gspi8385\_help |
|                          |                          | er.bin](https://packages |
|                          |                          | .debian.org/file%3Aliber |
|                          |                          | tas/gspi8385_helper.bin  |
|                          |                          | "DebianPkg"){.interwiki} |
|                          |                          | [libertas/gspi8385\_hlp. |
|                          |                          | bin](https://packages.de |
|                          |                          | bian.org/file%3Alibertas |
|                          |                          | /gspi8385_hlp.bin "Debia |
|                          |                          | nPkg"){.interwiki}       |
|                          |                          | [libertas/gspi8686.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Alibertas/gspi |
|                          |                          | 8686.bin "DebianPkg"){.i |
|                          |                          | nterwiki}                |
|                          |                          | [libertas/gspi8686\_hlp. |
|                          |                          | bin](https://packages.de |
|                          |                          | bian.org/file%3Alibertas |
|                          |                          | /gspi8686_hlp.bin "Debia |
|                          |                          | nPkg"){.interwiki}       |
|                          |                          | [libertas/gspi8686\_v9.b |
|                          |                          | in](https://packages.deb |
|                          |                          | ian.org/file%3Alibertas/ |
|                          |                          | gspi8686_v9.bin "DebianP |
|                          |                          | kg"){.interwiki}         |
|                          |                          | [libertas/gspi8686\_v9\_ |
|                          |                          | helper.bin](https://pack |
|                          |                          | ages.debian.org/file%3Al |
|                          |                          | ibertas/gspi8686_v9_help |
|                          |                          | er.bin "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [libertas/gspi8688.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Alibertas/gspi |
|                          |                          | 8688.bin "DebianPkg"){.i |
|                          |                          | nterwiki}                |
|                          |                          | [libertas/gspi8688\_help |
|                          |                          | er.bin](https://packages |
|                          |                          | .debian.org/file%3Aliber |
|                          |                          | tas/gspi8688_helper.bin  |
|                          |                          | "DebianPkg"){.interwiki} |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[8388 USB WLAN Thinfirm | [lbtf\_usb.bin](https:// |
| id="Firmware-1.line-52"  | Driver](https://wiki.deb | packages.debian.org/file |
| class="anchor"></span>   | ian.org/libertas)*       | %3Albtf_usb.bin "DebianP |
| libertas\_tf\_usb.ko     |                          | kg"){.interwiki}         |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Matrox G200/G400*       | [matrox/g200\_warp.fw](h |
| id="Firmware-1.line-53"  |                          | ttps://packages.debian.o |
| class="anchor"></span>   |                          | rg/file%3Amatrox/g200_wa |
| mga.ko                   |                          | rp.fw "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [matrox/g400\_warp.fw](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Amatrox/g400_wa |
|                          |                          | rp.fw "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Marvell WiFi-Ex         | [mrvl/pcie8766\_uapsta.b |
| id="Firmware-1.line-54"  | PCI-Express Driver       | in](https://packages.deb |
| class="anchor"></span>   | version 1.0*             | ian.org/file%3Amrvl/pcie |
| mwifiex\_pcie.ko         |                          | 8766_uapsta.bin "DebianP |
|                          |                          | kg"){.interwiki}         |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Marvell WiFi-Ex SDIO    | [mrvl/sd8787\_uapsta.bin |
| id="Firmware-1.line-55"  | Driver version 1.0*      | ](https://packages.debia |
| class="anchor"></span>   |                          | n.org/file%3Amrvl/sd8787 |
| mwifiex\_sdio.ko         |                          | _uapsta.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Marvell TOPDOG(R)      | [mwl8k/fmimage\_8363.fw] |
| id="Firmware-1.line-56"  | 802.11 Wireless Network  | (https://wiki.debian.org |
| class="anchor"></span>   | Driver](https://wiki.deb | /mwl8k)                  |
| mwl8k.ko                 | ian.org/mwl8k)*          | [mwl8k/fmimage\_8366\_ap |
|                          |                          | -2.fw](https://wiki.debi |
|                          |                          | an.org/mwl8k)            |
|                          |                          | [mwl8k/fmimage\_8366.fw] |
|                          |                          | (https://wiki.debian.org |
|                          |                          | /mwl8k)                  |
|                          |                          | [mwl8k/fmimage\_8687.fw] |
|                          |                          | (https://wiki.debian.org |
|                          |                          | /mwl8k)                  |
|                          |                          | [mwl8k/helper\_8363.fw]( |
|                          |                          | https://wiki.debian.org/ |
|                          |                          | mwl8k)                   |
|                          |                          | [mwl8k/helper\_8366.fw]( |
|                          |                          | https://wiki.debian.org/ |
|                          |                          | mwl8k)                   |
|                          |                          | [mwl8k/helper\_8687.fw]( |
|                          |                          | https://wiki.debian.org/ |
|                          |                          | mwl8k)                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Myricom 10G driver      | [myri10ge\_ethp\_z8e.dat |
| id="Firmware-1.line-57"  | (10GbE)*                 | ](https://packages.debia |
| class="anchor"></span>   |                          | n.org/file%3Amyri10ge_et |
| myri10ge.ko              |                          | hp_z8e.dat "DebianPkg"){ |
|                          |                          | .interwiki}              |
|                          |                          | [myri10ge\_eth\_z8e.dat] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Amyri10ge_eth |
|                          |                          | _z8e.dat "DebianPkg"){.i |
|                          |                          | nterwiki}                |
|                          |                          | [myri10ge\_rss\_ethp\_z8 |
|                          |                          | e.dat](https://packages. |
|                          |                          | debian.org/file%3Amyri10 |
|                          |                          | ge_rss_ethp_z8e.dat "Deb |
|                          |                          | ianPkg"){.interwiki}     |
|                          |                          | [myri10ge\_rss\_eth\_z8e |
|                          |                          | .dat](https://packages.d |
|                          |                          | ebian.org/file%3Amyri10g |
|                          |                          | e_rss_eth_z8e.dat "Debia |
|                          |                          | nPkg"){.interwiki}       |
+--------------------------+--------------------------+--------------------------+
| <span                    | *QLogic/NetXen (1/10)    | [phanfw.bin](https://pac |
| id="Firmware-1.line-58"  | GbE Intelligent Ethernet | kages.debian.org/file%3A |
| class="anchor"></span>   | Driver*                  | phanfw.bin "DebianPkg"){ |
| netxen\_nic.ko           |                          | .interwiki}              |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Driver for Lucent      | [agere\_ap\_fw.bin](http |
| id="Firmware-1.line-59"  | Orinoco, Prism II based  | s://packages.debian.org/ |
| class="anchor"></span>   | and similar wireless     | file%3Aagere_ap_fw.bin " |
| orinoco.ko               | cards](https://wiki.debi | DebianPkg"){.interwiki}  |
|                          | an.org/orinoco)*         | [agere\_sta\_fw.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Aagere_sta_fw.bin |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [prism\_ap\_fw.bin](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Aprism_ap_fw.bin " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [prism\_sta\_fw.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Aprism_sta_fw.bin |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [symbol\_sp24t\_prim\_fw |
|                          |                          | ](https://wiki.debian.or |
|                          |                          | g/orinoco)               |
|                          |                          | [symbol\_sp24t\_sec\_fw] |
|                          |                          | (https://wiki.debian.org |
|                          |                          | /orinoco)                |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Driver for Orinoco     | [orinoco\_ezusb\_fw](htt |
| id="Firmware-1.line-60"  | wireless LAN cards using | ps://wiki.debian.org/ori |
| class="anchor"></span>   | EZUSB                    | noco_usb)                |
| orinoco\_usb.ko          | bridge](https://wiki.deb |                          |
|                          | ian.org/orinoco_usb)*    |                          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Prism54 PCI wireless   | [isl3886pci](https://wik |
| id="Firmware-1.line-61"  | driver](https://wiki.deb | i.debian.org/prism54)    |
| class="anchor"></span>   | ian.org/prism54)*        |                          |
| p54pci.ko                |                          |                          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [3826.arm](http://wirele |
| id="Firmware-1.line-62"  |                          | ss.kernel.org/en/users/D |
| class="anchor"></span>   |                          | rivers/p54){.http}       |
| p54spi.ko                |                          |                          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Prism54 USB wireless   | [isl3886usb](https://wik |
| id="Firmware-1.line-63"  | driver](https://wiki.deb | i.debian.org/prism54)    |
| class="anchor"></span>   | ian.org/prism54)*        | [isl3887usb](https://wik |
| p54usb.ko                |                          | i.debian.org/prism54)    |
+--------------------------+--------------------------+--------------------------+
| <span                    | *NE2000 compatible       | [cis/DP83903.cis](https: |
| id="Firmware-1.line-64"  | PCMCIA ethernet driver*  | //packages.debian.org/fi |
| class="anchor"></span>   |                          | le%3Acis/DP83903.cis "De |
| pcnet\_cs.ko             |                          | bianPkg"){.interwiki}    |
|                          |                          | [cis/LA-PCM.cis](https:/ |
|                          |                          | /packages.debian.org/fil |
|                          |                          | e%3Acis/LA-PCM.cis "Debi |
|                          |                          | anPkg"){.interwiki}      |
|                          |                          | [cis/NE2K.cis](https://p |
|                          |                          | ackages.debian.org/file% |
|                          |                          | 3Acis/NE2K.cis "DebianPk |
|                          |                          | g"){.interwiki}          |
|                          |                          | [cis/PCMLM28.cis](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Acis/PCMLM28.cis "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [cis/PE-200.cis](https:/ |
|                          |                          | /packages.debian.org/fil |
|                          |                          | e%3Acis/PE-200.cis "Debi |
|                          |                          | anPkg"){.interwiki}      |
|                          |                          | [cis/PE520.cis](https:// |
|                          |                          | packages.debian.org/file |
|                          |                          | %3Acis/PE520.cis "Debian |
|                          |                          | Pkg"){.interwiki}        |
|                          |                          | [cis/tamarack.cis](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Acis/tamarack.cis " |
|                          |                          | DebianPkg"){.interwiki}  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[(none)](https://wiki.d | [prism2\_ru.fw](https:// |
| id="Firmware-1.line-65"  | ebian.org/linux-wlan-ng) | packages.debian.org/file |
| class="anchor"></span>   | *                        | %3Aprism2_ru.fw "DebianP |
| prism2\_usb.ko           |                          | kg"){.interwiki}         |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Qlogic ISP SCSI         | [qlogic/1040.bin](https: |
| id="Firmware-1.line-66"  | (qla1x80/qla1x160)       | //packages.debian.org/fi |
| class="anchor"></span>   | driver*                  | le%3Aqlogic/1040.bin "De |
| qla1280.ko               |                          | bianPkg"){.interwiki}    |
|                          |                          | [qlogic/12160.bin](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Aqlogic/12160.bin " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [qlogic/1280.bin](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Aqlogic/1280.bin "De |
|                          |                          | bianPkg"){.interwiki}    |
+--------------------------+--------------------------+--------------------------+
| <span                    | *QLogic Fibre Channel    | [ql2100\_fw.bin](https:/ |
| id="Firmware-1.line-67"  | HBA Driver*              | /packages.debian.org/fil |
| class="anchor"></span>   |                          | e%3Aql2100_fw.bin "Debia |
| qla2xxx.ko               |                          | nPkg"){.interwiki}       |
|                          |                          | [ql2200\_fw.bin](https:/ |
|                          |                          | /packages.debian.org/fil |
|                          |                          | e%3Aql2200_fw.bin "Debia |
|                          |                          | nPkg"){.interwiki}       |
|                          |                          | [ql2300\_fw.bin](https:/ |
|                          |                          | /packages.debian.org/fil |
|                          |                          | e%3Aql2300_fw.bin "Debia |
|                          |                          | nPkg"){.interwiki}       |
|                          |                          | [ql2322\_fw.bin](https:/ |
|                          |                          | /packages.debian.org/fil |
|                          |                          | e%3Aql2322_fw.bin "Debia |
|                          |                          | nPkg"){.interwiki}       |
|                          |                          | [ql2400\_fw.bin](https:/ |
|                          |                          | /packages.debian.org/fil |
|                          |                          | e%3Aql2400_fw.bin "Debia |
|                          |                          | nPkg"){.interwiki}       |
|                          |                          | [ql2500\_fw.bin](https:/ |
|                          |                          | /packages.debian.org/fil |
|                          |                          | e%3Aql2500_fw.bin "Debia |
|                          |                          | nPkg"){.interwiki}       |
+--------------------------+--------------------------+--------------------------+
| <span                    | *QLogic 1/10 GbE         | [phanfw.bin](https://pac |
| id="Firmware-1.line-68"  | Converged/Intelligent    | kages.debian.org/file%3A |
| class="anchor"></span>   | Ethernet Driver*         | phanfw.bin "DebianPkg"){ |
| qlcnic.ko                |                          | .interwiki}              |
+--------------------------+--------------------------+--------------------------+
| <span                    | *ATI Rage 128*           | [r128/r128\_cce.bin](htt |
| id="Firmware-1.line-69"  |                          | ps://packages.debian.org |
| class="anchor"></span>   |                          | /file%3Ar128/r128_cce.bi |
| r128.ko                  |                          | n "DebianPkg"){.interwik |
|                          |                          | i}                       |
+--------------------------+--------------------------+--------------------------+
| <span                    | *RealTek RTL-8169        | [rtl\_nic/rtl8105e-1.fw] |
| id="Firmware-1.line-70"  | Gigabit Ethernet driver* | (https://packages.debian |
| class="anchor"></span>   |                          | .org/file%3Artl_nic/rtl8 |
| r8169.ko                 |                          | 105e-1.fw "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [rtl\_nic/rtl8168d-1.fw] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Artl_nic/rtl8 |
|                          |                          | 168d-1.fw "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [rtl\_nic/rtl8168d-2.fw] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Artl_nic/rtl8 |
|                          |                          | 168d-2.fw "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [rtl\_nic/rtl8168e-1.fw] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Artl_nic/rtl8 |
|                          |                          | 168e-1.fw "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [rtl\_nic/rtl8168e-2.fw] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Artl_nic/rtl8 |
|                          |                          | 168e-2.fw "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [rtl\_nic/rtl8168e-3.fw] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Artl_nic/rtl8 |
|                          |                          | 168e-3.fw "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [rtl\_nic/rtl8168f-1.fw] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Artl_nic/rtl8 |
|                          |                          | 168f-1.fw "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [rtl\_nic/rtl8168f-2.fw] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Artl_nic/rtl8 |
|                          |                          | 168f-2.fw "DebianPkg"){. |
|                          |                          | interwiki}               |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Linux driver for       | [RTL8192U/boot.img](http |
| id="Firmware-1.line-71"  | Realtek RTL8192 USB WiFi | s://wiki.debian.org/rtl8 |
| class="anchor"></span>   | cards](https://wiki.debi | 19x)                     |
| r8192u\_usb.ko           | an.org/rtl819x)*         | [RTL8192U/data.img](http |
|                          |                          | s://wiki.debian.org/rtl8 |
|                          |                          | 19x)                     |
|                          |                          | [RTL8192U/main.img](http |
|                          |                          | s://wiki.debian.org/rtl8 |
|                          |                          | 19x)                     |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[rtl871x wireless lan   | [rtlwifi/rtl8712u.bin](h |
| id="Firmware-1.line-72"  | driver](https://wiki.deb | ttps://packages.debian.o |
| class="anchor"></span>   | ian.org/rtl819x)*        | rg/file%3Artlwifi/rtl871 |
| r8712u.ko                |                          | 2u.bin "DebianPkg"){.int |
|                          |                          | erwiki}                  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[ATI                    | [radeon/ARUBA\_me.bin](h |
| id="Firmware-1.line-73"  | Radeon](https://wiki.deb | ttps://packages.debian.o |
| class="anchor"></span>   | ian.org/AtiHowTo)*       | rg/file%3Aradeon/ARUBA_m |
| radeon.ko                |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/ARUBA\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/ARUBA_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/ARUBA\_rlc.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/ARUBA_ |
|                          |                          | rlc.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/BARTS\_mc.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/BARTS_m |
|                          |                          | c.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/BARTS\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/BARTS_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/BARTS\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/BARTS_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/BTC\_rlc.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/BTC_rlc. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/CAICOS\_mc.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/CAICOS |
|                          |                          | _mc.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/CAICOS\_me.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/CAICOS |
|                          |                          | _me.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/CAICOS\_pfp.bin] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Aradeon/CAICO |
|                          |                          | S_pfp.bin "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [radeon/CAYMAN\_mc.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/CAYMAN |
|                          |                          | _mc.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/CAYMAN\_me.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/CAYMAN |
|                          |                          | _me.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/CAYMAN\_pfp.bin] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Aradeon/CAYMA |
|                          |                          | N_pfp.bin "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [radeon/CAYMAN\_rlc.bin] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Aradeon/CAYMA |
|                          |                          | N_rlc.bin "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [radeon/CEDAR\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/CEDAR_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/CEDAR\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/CEDAR_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/CEDAR\_rlc.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/CEDAR_ |
|                          |                          | rlc.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/CYPRESS\_me.bin] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Aradeon/CYPRE |
|                          |                          | SS_me.bin "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [radeon/CYPRESS\_pfp.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aradeon/CYPR |
|                          |                          | ESS_pfp.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [radeon/CYPRESS\_rlc.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aradeon/CYPR |
|                          |                          | ESS_rlc.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [radeon/JUNIPER\_me.bin] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Aradeon/JUNIP |
|                          |                          | ER_me.bin "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [radeon/JUNIPER\_pfp.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aradeon/JUNI |
|                          |                          | PER_pfp.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [radeon/JUNIPER\_rlc.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aradeon/JUNI |
|                          |                          | PER_rlc.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [radeon/PALM\_me.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/PALM_me. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/PALM\_pfp.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/PALM_pf |
|                          |                          | p.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/PITCAIRN\_ce.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aradeon/PITC |
|                          |                          | AIRN_ce.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [radeon/PITCAIRN\_mc.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aradeon/PITC |
|                          |                          | AIRN_mc.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [radeon/PITCAIRN\_me.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aradeon/PITC |
|                          |                          | AIRN_me.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [radeon/PITCAIRN\_pfp.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Aradeon/PIT |
|                          |                          | CAIRN_pfp.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
|                          |                          | [radeon/PITCAIRN\_rlc.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Aradeon/PIT |
|                          |                          | CAIRN_rlc.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
|                          |                          | [radeon/R100\_cp.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R100_cp. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R100\_cp.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R100_cp. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R200\_cp.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R200_cp. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R200\_cp.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R200_cp. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R300\_cp.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R300_cp. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R300\_cp.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R300_cp. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R420\_cp.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R420_cp. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R420\_cp.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R420_cp. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R520\_cp.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R520_cp. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R520\_cp.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R520_cp. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R600\_me.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R600_me. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R600\_me.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/R600_me. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/R600\_pfp.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/R600_pf |
|                          |                          | p.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/R600\_pfp.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/R600_pf |
|                          |                          | p.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/R600\_rlc.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/R600_rl |
|                          |                          | c.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/R700\_rlc.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/R700_rl |
|                          |                          | c.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/REDWOOD\_me.bin] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Aradeon/REDWO |
|                          |                          | OD_me.bin "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [radeon/REDWOOD\_pfp.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aradeon/REDW |
|                          |                          | OOD_pfp.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [radeon/REDWOOD\_rlc.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Aradeon/REDW |
|                          |                          | OOD_rlc.bin "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [radeon/RS600\_cp.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RS600_c |
|                          |                          | p.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RS600\_cp.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RS600_c |
|                          |                          | p.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RS690\_cp.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RS690_c |
|                          |                          | p.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RS690\_cp.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RS690_c |
|                          |                          | p.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RS780\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RS780_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RS780\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RS780_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RS780\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RS780_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RS780\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RS780_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV610\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV610_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV610\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV610_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV610\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV610_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV610\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV610_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV620\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV620_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV620\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV620_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV620\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV620_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV620\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV620_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV630\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV630_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV630\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV630_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV630\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV630_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV630\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV630_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV635\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV635_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV635\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV635_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV635\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV635_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV635\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV635_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV670\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV670_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV670\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV670_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV670\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV670_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV670\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV670_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV710\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV710_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV710\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV710_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV710\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV710_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV710\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV710_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV730\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV730_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV730\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV730_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV730\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV730_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV730\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV730_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV770\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV770_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV770\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/RV770_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/RV770\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV770_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/RV770\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/RV770_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/SUMO2\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/SUMO2_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/SUMO2\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/SUMO2_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/SUMO\_me.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Aradeon/SUMO_me. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [radeon/SUMO\_pfp.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/SUMO_pf |
|                          |                          | p.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/SUMO\_rlc.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/SUMO_rl |
|                          |                          | c.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/TAHITI\_ce.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/TAHITI |
|                          |                          | _ce.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/TAHITI\_mc.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/TAHITI |
|                          |                          | _mc.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/TAHITI\_me.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/TAHITI |
|                          |                          | _me.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/TAHITI\_pfp.bin] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Aradeon/TAHIT |
|                          |                          | I_pfp.bin "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [radeon/TAHITI\_rlc.bin] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Aradeon/TAHIT |
|                          |                          | I_rlc.bin "DebianPkg"){. |
|                          |                          | interwiki}               |
|                          |                          | [radeon/TURKS\_mc.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/TURKS_m |
|                          |                          | c.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/TURKS\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/TURKS_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/TURKS\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/TURKS_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/VERDE\_ce.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/VERDE_c |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/VERDE\_mc.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/VERDE_m |
|                          |                          | c.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/VERDE\_me.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Aradeon/VERDE_m |
|                          |                          | e.bin "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [radeon/VERDE\_pfp.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/VERDE_ |
|                          |                          | pfp.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
|                          |                          | [radeon/VERDE\_rlc.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Aradeon/VERDE_ |
|                          |                          | rlc.bin "DebianPkg"){.in |
|                          |                          | terwiki}                 |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Ralink RT2800 PCI &    | [rt2860.bin](https://pac |
| id="Firmware-1.line-74"  | PCMCIA Wireless LAN      | kages.debian.org/file%3A |
| class="anchor"></span>   | driver.](https://wiki.de | rt2860.bin "DebianPkg"){ |
| rt2800pci.ko             | bian.org/rt2800pci)*     | .interwiki}              |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Ralink RT2800 USB      | [rt2870.bin](https://pac |
| id="Firmware-1.line-75"  | Wireless LAN             | kages.debian.org/file%3A |
| class="anchor"></span>   | driver.](https://wiki.de | rt2870.bin "DebianPkg"){ |
| rt2800usb.ko             | bian.org/rt2800usb)*     | .interwiki}              |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Ralink RT61 PCI &      | [rt2561.bin](https://pac |
| id="Firmware-1.line-76"  | PCMCIA Wireless LAN      | kages.debian.org/file%3A |
| class="anchor"></span>   | driver.](https://wiki.de | rt2561.bin "DebianPkg"){ |
| rt61pci.ko               | bian.org/rt61pci)*       | .interwiki}              |
|                          |                          | [rt2561s.bin](https://pa |
|                          |                          | ckages.debian.org/file%3 |
|                          |                          | Art2561s.bin "DebianPkg" |
|                          |                          | ){.interwiki}            |
|                          |                          | [rt2661.bin](https://pac |
|                          |                          | kages.debian.org/file%3A |
|                          |                          | rt2661.bin "DebianPkg"){ |
|                          |                          | .interwiki}              |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Ralink RT73 USB        | [rt73.bin](https://packa |
| id="Firmware-1.line-77"  | Wireless LAN             | ges.debian.org/file%3Art |
| class="anchor"></span>   | driver.](https://wiki.de | 73.bin "DebianPkg"){.int |
| rt73usb.ko               | bian.org/WiFi/rt73)*     | erwiki}                  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Realtek 8192C/8188C    | [rtlwifi/rtl8192cfw.bin] |
| id="Firmware-1.line-78"  | 802.11n PCI              | (https://packages.debian |
| class="anchor"></span>   | wireless](https://wiki.d | .org/file%3Artlwifi/rtl8 |
| rtl8192ce.ko             | ebian.org/rtl819x)*      | 192cfw.bin "DebianPkg"){ |
|                          |                          | .interwiki}              |
|                          |                          | [rtlwifi/rtl8192cfwU\_B. |
|                          |                          | bin](https://packages.de |
|                          |                          | bian.org/file%3Artlwifi/ |
|                          |                          | rtl8192cfwU_B.bin "Debia |
|                          |                          | nPkg"){.interwiki}       |
|                          |                          | [rtlwifi/rtl8192cfwU.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Artlwifi/rtl |
|                          |                          | 8192cfwU.bin "DebianPkg" |
|                          |                          | ){.interwiki}            |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Realtek 8192C/8188C    | [rtlwifi/rtl8192cufw.bin |
| id="Firmware-1.line-79"  | 802.11n USB              | ](https://packages.debia |
| class="anchor"></span>   | wireless](https://wiki.d | n.org/file%3Artlwifi/rtl |
| rtl8192cu.ko             | ebian.org/rtl819x)*      | 8192cufw.bin "DebianPkg" |
|                          |                          | ){.interwiki}            |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Realtek 8192DE 802.11n | [rtlwifi/rtl8192defw.bin |
| id="Firmware-1.line-80"  | Dual Mac PCI             | ](https://packages.debia |
| class="anchor"></span>   | wireless](https://wiki.d | n.org/file%3Artlwifi/rtl |
| rtl8192de.ko             | ebian.org/rtl819x)*      | 8192defw.bin "DebianPkg" |
|                          |                          | ){.interwiki}            |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Realtek 8192S/8191S    | [rtlwifi/rtl8192sefw.bin |
| id="Firmware-1.line-81"  | 802.11n PCI              | ](https://packages.debia |
| class="anchor"></span>   | wireless](https://wiki.d | n.org/file%3Artlwifi/rtl |
| rtl8192se.ko             | ebian.org/rtl819x)*      | 8192sefw.bin "DebianPkg" |
|                          |                          | ){.interwiki}            |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [cis/3CCFEM556.cis](http |
| id="Firmware-1.line-82"  |                          | s://packages.debian.org/ |
| class="anchor"></span>   |                          | file%3Acis/3CCFEM556.cis |
| serial\_cs.ko            |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [cis/3CXEM556.cis](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Acis/3CXEM556.cis " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [cis/COMpad2.cis](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Acis/COMpad2.cis "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [cis/COMpad4.cis](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Acis/COMpad4.cis "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [cis/DP83903.cis](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Acis/DP83903.cis "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [cis/MT5634ZLX.cis](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Acis/MT5634ZLX.cis |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [cis/PCMLM28.cis](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Acis/PCMLM28.cis "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [cis/RS-COM-2P.cis](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Acis/RS-COM-2P.cis |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [cis/SW\_555\_SER.cis](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Acis/SW_555_SER |
|                          |                          | .cis "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [cis/SW\_7xx\_SER.cis](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Acis/SW_7xx_SER |
|                          |                          | .cis "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [cis/SW\_8xx\_SER.cis](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Acis/SW_8xx_SER |
|                          |                          | .cis "DebianPkg"){.inter |
|                          |                          | wiki}                    |
+--------------------------+--------------------------+--------------------------+
| <span                    | *SMC 91c92 series PCMCIA | [ositech/Xilinx7OD.bin]( |
| id="Firmware-1.line-83"  | ethernet driver*         | https://packages.debian. |
| class="anchor"></span>   |                          | org/file%3Aositech/Xilin |
| smc91c92\_cs.ko          |                          | x7OD.bin "DebianPkg"){.i |
|                          |                          | nterwiki}                |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [tr\_smctr.bin](https:// |
| id="Firmware-1.line-84"  |                          | packages.debian.org/file |
| class="anchor"></span>   |                          | %3Atr_smctr.bin "DebianP |
| smctr.ko                 |                          | kg"){.interwiki}         |
+--------------------------+--------------------------+--------------------------+
| <span                    | *AudioScience ALSA       | [asihpi/dsp5000.bin](htt |
| id="Firmware-1.line-85"  | ASI5000 ASI6000 ASI87xx  | ps://packages.debian.org |
| class="anchor"></span>   | ASI89xx*                 | /file%3Aasihpi/dsp5000.b |
| snd-asihpi.ko            |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [asihpi/dsp6200.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Aasihpi/dsp6200.b |
|                          |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [asihpi/dsp6205.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Aasihpi/dsp6205.b |
|                          |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [asihpi/dsp6400.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Aasihpi/dsp6400.b |
|                          |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [asihpi/dsp6600.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Aasihpi/dsp6600.b |
|                          |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [asihpi/dsp8700.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Aasihpi/dsp8700.b |
|                          |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [asihpi/dsp8900.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Aasihpi/dsp8900.b |
|                          |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Cirrus Logic Sound     | [cs46xx/cs46xx-old.fw](h |
| id="Firmware-1.line-86"  | Fusion                   | ttps://wiki.debian.org/s |
| class="anchor"></span>   | CS46XX](https://wiki.deb | nd-cs46xx)               |
| snd-cs46xx.ko            | ian.org/snd-cs46xx)*     |                          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Darla20      | [ea/darla20\_dsp.fw](htt |
| id="Firmware-1.line-87"  | soundcards               | ps://wiki.debian.org/ech |
| class="anchor"></span>   | driver](https://wiki.deb | oaudio)                  |
| snd-darla20.ko           | ian.org/echoaudio)*      |                          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Darla24      | [ea/darla24\_dsp.fw](htt |
| id="Firmware-1.line-88"  | soundcards               | ps://wiki.debian.org/ech |
| class="anchor"></span>   | driver](https://wiki.deb | oaudio)                  |
| snd-darla24.ko           | ian.org/echoaudio)*      |                          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Echo3G       | [ea/3g\_asic.fw](https:/ |
| id="Firmware-1.line-89"  | soundcards               | /wiki.debian.org/echoaud |
| class="anchor"></span>   | driver](https://wiki.deb | io)                      |
| snd-echo3g.ko            | ian.org/echoaudio)*      | [ea/echo3g\_dsp.fw](http |
|                          |                          | s://wiki.debian.org/echo |
|                          |                          | audio)                   |
|                          |                          | [ea/loader\_dsp.fw](http |
|                          |                          | s://wiki.debian.org/echo |
|                          |                          | audio)                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[EMU10K1](https://wiki. | [emu/audio\_dock.fw](htt |
| id="Firmware-1.line-90"  | debian.org/snd-emu10k1)* | ps://wiki.debian.org/snd |
| class="anchor"></span>   |                          | -emu10k1)                |
| snd-emu10k1.ko           |                          | [emu/emu0404.fw](https:/ |
|                          |                          | /wiki.debian.org/snd-emu |
|                          |                          | 10k1)                    |
|                          |                          | [emu/emu1010b.fw](https: |
|                          |                          | //wiki.debian.org/snd-em |
|                          |                          | u10k1)                   |
|                          |                          | [emu/emu1010\_notebook.f |
|                          |                          | w](https://wiki.debian.o |
|                          |                          | rg/snd-emu10k1)          |
|                          |                          | [emu/hana.fw](https://wi |
|                          |                          | ki.debian.org/snd-emu10k |
|                          |                          | 1)                       |
|                          |                          | [emu/micro\_dock.fw](htt |
|                          |                          | ps://wiki.debian.org/snd |
|                          |                          | -emu10k1)                |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Gina20       | [ea/gina20\_dsp.fw](http |
| id="Firmware-1.line-91"  | soundcards               | s://wiki.debian.org/echo |
| class="anchor"></span>   | driver](https://wiki.deb | audio)                   |
| snd-gina20.ko            | ian.org/echoaudio)*      |                          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Gina24       | [ea/gina24\_301\_asic.fw |
| id="Firmware-1.line-92"  | soundcards               | ](https://wiki.debian.or |
| class="anchor"></span>   | driver](https://wiki.deb | g/echoaudio)             |
| snd-gina24.ko            | ian.org/echoaudio)*      | [ea/gina24\_301\_dsp.fw] |
|                          |                          | (https://wiki.debian.org |
|                          |                          | /echoaudio)              |
|                          |                          | [ea/gina24\_361\_asic.fw |
|                          |                          | ](https://wiki.debian.or |
|                          |                          | g/echoaudio)             |
|                          |                          | [ea/gina24\_361\_dsp.fw] |
|                          |                          | (https://wiki.debian.org |
|                          |                          | /echoaudio)              |
|                          |                          | [ea/loader\_dsp.fw](http |
|                          |                          | s://wiki.debian.org/echo |
|                          |                          | audio)                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Indigo DJ    | [ea/indigo\_dj\_dsp.fw]( |
| id="Firmware-1.line-93"  | soundcards               | https://wiki.debian.org/ |
| class="anchor"></span>   | driver](https://wiki.deb | echoaudio)               |
| snd-indigodj.ko          | ian.org/echoaudio)*      | [ea/loader\_dsp.fw](http |
|                          |                          | s://wiki.debian.org/echo |
|                          |                          | audio)                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Indigo DJx   | [ea/indigo\_djx\_dsp.fw] |
| id="Firmware-1.line-94"  | soundcards               | (https://wiki.debian.org |
| class="anchor"></span>   | driver](https://wiki.deb | /echoaudio)              |
| snd-indigodjx.ko         | ian.org/echoaudio)*      | [ea/loader\_dsp.fw](http |
|                          |                          | s://wiki.debian.org/echo |
|                          |                          | audio)                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Indigo IO    | [ea/indigo\_io\_dsp.fw]( |
| id="Firmware-1.line-95"  | soundcards               | https://wiki.debian.org/ |
| class="anchor"></span>   | driver](https://wiki.deb | echoaudio)               |
| snd-indigoio.ko          | ian.org/echoaudio)*      | [ea/loader\_dsp.fw](http |
|                          |                          | s://wiki.debian.org/echo |
|                          |                          | audio)                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Indigo IOx   | [ea/indigo\_iox\_dsp.fw] |
| id="Firmware-1.line-96"  | soundcards               | (https://wiki.debian.org |
| class="anchor"></span>   | driver](https://wiki.deb | /echoaudio)              |
| snd-indigoiox.ko         | ian.org/echoaudio)*      | [ea/loader\_dsp.fw](http |
|                          |                          | s://wiki.debian.org/echo |
|                          |                          | audio)                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Indigo       | [ea/indigo\_dsp.fw](http |
| id="Firmware-1.line-97"  | soundcards               | s://wiki.debian.org/echo |
| class="anchor"></span>   | driver](https://wiki.deb | audio)                   |
| snd-indigo.ko            | ian.org/echoaudio)*      | [ea/loader\_dsp.fw](http |
|                          |                          | s://wiki.debian.org/echo |
|                          |                          | audio)                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[korg1212](https://wiki | [korg/k1212.dsp](https:/ |
| id="Firmware-1.line-98"  | .debian.org/snd-korg1212 | /wiki.debian.org/snd-kor |
| class="anchor"></span>   | )*                       | g1212)                   |
| snd-korg1212.ko          |                          |                          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Layla20      | [ea/layla20\_asic.fw](ht |
| id="Firmware-1.line-99"  | soundcards               | tps://wiki.debian.org/ec |
| class="anchor"></span>   | driver](https://wiki.deb | hoaudio)                 |
| snd-layla20.ko           | ian.org/echoaudio)*      | [ea/layla20\_dsp.fw](htt |
|                          |                          | ps://wiki.debian.org/ech |
|                          |                          | oaudio)                  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Layla24      | [ea/layla24\_1\_asic.fw] |
| id="Firmware-1.line-100" | soundcards               | (https://wiki.debian.org |
| class="anchor"></span>   | driver](https://wiki.deb | /echoaudio)              |
| snd-layla24.ko           | ian.org/echoaudio)*      | [ea/layla24\_2A\_asic.fw |
|                          |                          | ](https://wiki.debian.or |
|                          |                          | g/echoaudio)             |
|                          |                          | [ea/layla24\_2S\_asic.fw |
|                          |                          | ](https://wiki.debian.or |
|                          |                          | g/echoaudio)             |
|                          |                          | [ea/layla24\_dsp.fw](htt |
|                          |                          | ps://wiki.debian.org/ech |
|                          |                          | oaudio)                  |
|                          |                          | [ea/loader\_dsp.fw](http |
|                          |                          | s://wiki.debian.org/echo |
|                          |                          | audio)                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[ESS Maestro3           | [ess/maestro3\_assp\_ker |
| id="Firmware-1.line-101" | PCI](https://wiki.debian | nel.fw](https://wiki.deb |
| class="anchor"></span>   | .org/snd-maestro3)*      | ian.org/snd-maestro3)    |
| snd-maestro3.ko          |                          | [ess/maestro3\_assp\_min |
|                          |                          | isrc.fw](https://wiki.de |
|                          |                          | bian.org/snd-maestro3)   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Mia          | [ea/loader\_dsp.fw](http |
| id="Firmware-1.line-102" | soundcards               | s://wiki.debian.org/echo |
| class="anchor"></span>   | driver](https://wiki.deb | audio)                   |
| snd-mia.ko               | ian.org/echoaudio)*      | [ea/mia\_dsp.fw](https:/ |
|                          |                          | /wiki.debian.org/echoaud |
|                          |                          | io)                      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Digigram miXart*        | [mixart/miXart8AES.xlx]( |
| id="Firmware-1.line-103" |                          | https://packages.debian. |
| class="anchor"></span>   |                          | org/file%3Amixart/miXart |
| snd-mixart.ko            |                          | 8AES.xlx "DebianPkg"){.i |
|                          |                          | nterwiki}                |
|                          |                          | [mixart/miXart8.elf](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Amixart/miXart8.e |
|                          |                          | lf "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [mixart/miXart8.xlx](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Amixart/miXart8.x |
|                          |                          | lx "DebianPkg"){.interwi |
|                          |                          | ki}                      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Echoaudio Mona         | [ea/loader\_dsp.fw](http |
| id="Firmware-1.line-104" | soundcards               | s://wiki.debian.org/echo |
| class="anchor"></span>   | driver](https://wiki.deb | audio)                   |
| snd-mona.ko              | ian.org/echoaudio)*      | [ea/mona\_2\_asic.fw](ht |
|                          |                          | tps://wiki.debian.org/ec |
|                          |                          | hoaudio)                 |
|                          |                          | [ea/mona\_301\_1\_asic\_ |
|                          |                          | 48.fw](https://wiki.debi |
|                          |                          | an.org/echoaudio)        |
|                          |                          | [ea/mona\_301\_1\_asic\_ |
|                          |                          | 96.fw](https://wiki.debi |
|                          |                          | an.org/echoaudio)        |
|                          |                          | [ea/mona\_301\_dsp.fw](h |
|                          |                          | ttps://wiki.debian.org/e |
|                          |                          | choaudio)                |
|                          |                          | [ea/mona\_361\_1\_asic\_ |
|                          |                          | 48.fw](https://wiki.debi |
|                          |                          | an.org/echoaudio)        |
|                          |                          | [ea/mona\_361\_1\_asic\_ |
|                          |                          | 96.fw](https://wiki.debi |
|                          |                          | an.org/echoaudio)        |
|                          |                          | [ea/mona\_361\_dsp.fw](h |
|                          |                          | ttps://wiki.debian.org/e |
|                          |                          | choaudio)                |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Turtle Beach MultiSound | [turtlebeach/msndinit.bi |
| id="Firmware-1.line-105" | (Classic/Monterey/Tahiti | n](https://packages.debi |
| class="anchor"></span>   | )                        | an.org/file%3Aturtlebeac |
| snd-msnd-classic.ko      | Linux Driver*            | h/msndinit.bin "DebianPk |
|                          |                          | g"){.interwiki}          |
|                          |                          | [turtlebeach/msndperm.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Aturtlebeac |
|                          |                          | h/msndperm.bin "DebianPk |
|                          |                          | g"){.interwiki}          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Turtle Beach MultiSound | [turtlebeach/pndsperm.bi |
| id="Firmware-1.line-106" | (Pinnacle/Fiji) Linux    | n](https://packages.debi |
| class="anchor"></span>   | Driver*                  | an.org/file%3Aturtlebeac |
| snd-msnd-pinnacle.ko     |                          | h/pndsperm.bin "DebianPk |
|                          |                          | g"){.interwiki}          |
|                          |                          | [turtlebeach/pndspini.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Aturtlebeac |
|                          |                          | h/pndspini.bin "DebianPk |
|                          |                          | g"){.interwiki}          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Digigram pcxhr 0.9.6*   | [pcxhr/dspb1222e.b56](ht |
| id="Firmware-1.line-107" |                          | tps://packages.debian.or |
| class="anchor"></span>   |                          | g/file%3Apcxhr/dspb1222e |
| snd-pcxhr.ko             |                          | .b56 "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [pcxhr/dspb1222hr.b56](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Apcxhr/dspb1222 |
|                          |                          | hr.b56 "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [pcxhr/dspb882e.b56](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Apcxhr/dspb882e.b |
|                          |                          | 56 "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [pcxhr/dspb882hr.b56](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Apcxhr/dspb882hr |
|                          |                          | .b56 "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [pcxhr/dspb924.b56](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Apcxhr/dspb924.b56 |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [pcxhr/dspd1222.d56](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Apcxhr/dspd1222.d |
|                          |                          | 56 "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [pcxhr/dspd222.d56](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Apcxhr/dspd222.d56 |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [pcxhr/dspd882.d56](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Apcxhr/dspd882.d56 |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [pcxhr/dspe882.e56](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Apcxhr/dspe882.e56 |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [pcxhr/dspe924.e56](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Apcxhr/dspe924.e56 |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [pcxhr/xlxc1222e.dat](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Apcxhr/xlxc1222e |
|                          |                          | .dat "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [pcxhr/xlxc1222hr.dat](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Apcxhr/xlxc1222 |
|                          |                          | hr.dat "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [pcxhr/xlxc222.dat](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Apcxhr/xlxc222.dat |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [pcxhr/xlxc882e.dat](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Apcxhr/xlxc882e.d |
|                          |                          | at "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [pcxhr/xlxc882hr.dat](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Apcxhr/xlxc882hr |
|                          |                          | .dat "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [pcxhr/xlxc924.dat](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Apcxhr/xlxc924.dat |
|                          |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [pcxhr/xlxint.dat](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Apcxhr/xlxint.dat " |
|                          |                          | DebianPkg"){.interwiki}  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *riptide*                | [riptide.hex](https://pa |
| id="Firmware-1.line-108" |                          | ckages.debian.org/file%3 |
| class="anchor"></span>   |                          | Ariptide.hex "DebianPkg" |
| snd-riptide.ko           |                          | ){.interwiki}            |
+--------------------------+--------------------------+--------------------------+
| <span                    | *ALSA driver for SB16    | [sb16/alaw\_main.csp](ht |
| id="Firmware-1.line-109" | Creative Signal          | tps://packages.debian.or |
| class="anchor"></span>   | Processor*               | g/file%3Asb16/alaw_main. |
| snd-sb16-csp.ko          |                          | csp "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [sb16/ima\_adpcm\_captur |
|                          |                          | e.csp](https://packages. |
|                          |                          | debian.org/file%3Asb16/i |
|                          |                          | ma_adpcm_capture.csp "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [sb16/ima\_adpcm\_init.c |
|                          |                          | sp](https://packages.deb |
|                          |                          | ian.org/file%3Asb16/ima_ |
|                          |                          | adpcm_init.csp "DebianPk |
|                          |                          | g"){.interwiki}          |
|                          |                          | [sb16/ima\_adpcm\_playba |
|                          |                          | ck.csp](https://packages |
|                          |                          | .debian.org/file%3Asb16/ |
|                          |                          | ima_adpcm_playback.csp " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [sb16/mulaw\_main.csp](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Asb16/mulaw_mai |
|                          |                          | n.csp "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *ENSONIQ SoundScape      | [scope.cod](https://pack |
| id="Firmware-1.line-110" | driver*                  | ages.debian.org/file%3As |
| class="anchor"></span>   |                          | cope.cod "DebianPkg"){.i |
| snd-sscape.ko            |                          | nterwiki}                |
|                          |                          | [sndscape.co0](https://p |
|                          |                          | ackages.debian.org/file% |
|                          |                          | 3Asndscape.co0 "DebianPk |
|                          |                          | g"){.interwiki}          |
|                          |                          | [sndscape.co1](https://p |
|                          |                          | ackages.debian.org/file% |
|                          |                          | 3Asndscape.co1 "DebianPk |
|                          |                          | g"){.interwiki}          |
|                          |                          | [sndscape.co2](https://p |
|                          |                          | ackages.debian.org/file% |
|                          |                          | 3Asndscape.co2 "DebianPk |
|                          |                          | g"){.interwiki}          |
|                          |                          | [sndscape.co3](https://p |
|                          |                          | ackages.debian.org/file% |
|                          |                          | 3Asndscape.co3 "DebianPk |
|                          |                          | g"){.interwiki}          |
|                          |                          | [sndscape.co4](https://p |
|                          |                          | ackages.debian.org/file% |
|                          |                          | 3Asndscape.co4 "DebianPk |
|                          |                          | g"){.interwiki}          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *TerraTec DMX 6Fire USB  | [6fire/dmx6fireap.ihx](h |
| id="Firmware-1.line-111" | audio driver, version    | ttps://packages.debian.o |
| class="anchor"></span>   | 0.3.0*                   | rg/file%3A6fire/dmx6fire |
| snd-usb-6fire.ko         |                          | ap.ihx "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [6fire/dmx6firecf.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3A6fire/dmx6fire |
|                          |                          | cf.bin "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [6fire/dmx6firel2.ihx](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3A6fire/dmx6fire |
|                          |                          | l2.ihx "DebianPkg"){.int |
|                          |                          | erwiki}                  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Common routines for     | [vx/bd56002.boot](https: |
| id="Firmware-1.line-112" | Digigram VX drivers*     | //packages.debian.org/fi |
| class="anchor"></span>   |                          | le%3Avx/bd56002.boot "De |
| snd-vx-lib.ko            |                          | bianPkg"){.interwiki}    |
|                          |                          | [vx/bd563s3.boot](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Avx/bd563s3.boot "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [vx/bd563v2.boot](https: |
|                          |                          | //packages.debian.org/fi |
|                          |                          | le%3Avx/bd563v2.boot "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [vx/bx\_1\_vp4.b56](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Avx/bx_1_vp4.b56 " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [vx/bx\_1\_vxp.b56](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Avx/bx_1_vxp.b56 " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [vx/l\_1\_v22.d56](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Avx/l_1_v22.d56 "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [vx/l\_1\_vp4.d56](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Avx/l_1_vp4.d56 "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [vx/l\_1\_vx2.d56](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Avx/l_1_vx2.d56 "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [vx/l\_1\_vxp.d56](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Avx/l_1_vxp.d56 "De |
|                          |                          | bianPkg"){.interwiki}    |
|                          |                          | [vx/x1\_1\_vp4.xlx](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Avx/x1_1_vp4.xlx " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [vx/x1\_1\_vx2.xlx](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Avx/x1_1_vx2.xlx " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [vx/x1\_1\_vxp.xlx](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Avx/x1_1_vxp.xlx " |
|                          |                          | DebianPkg"){.interwiki}  |
|                          |                          | [vx/x1\_2\_v22.xlx](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Avx/x1_2_v22.xlx " |
|                          |                          | DebianPkg"){.interwiki}  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Turtle Beach Wavefront* | [wavefront.os](https://p |
| id="Firmware-1.line-113" |                          | ackages.debian.org/file% |
| class="anchor"></span>   |                          | 3Awavefront.os "DebianPk |
| snd-wavefront.ko         |                          | g"){.interwiki}          |
|                          |                          | [yamaha/yss225\_register |
|                          |                          | s.bin](https://packages. |
|                          |                          | debian.org/file%3Ayamaha |
|                          |                          | /yss225_registers.bin "D |
|                          |                          | ebianPkg"){.interwiki}   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Yamaha DS-1            | [yamaha/ds1\_ctrl.fw](ht |
| id="Firmware-1.line-114" | PCI](https://wiki.debian | tps://wiki.debian.org/sn |
| class="anchor"></span>   | .org/snd-ymfpci)*        | d-ymfpci)                |
| snd-ymfpci.ko            |                          | [yamaha/ds1\_dsp.fw](htt |
|                          |                          | ps://wiki.debian.org/snd |
|                          |                          | -ymfpci)                 |
|                          |                          | [yamaha/ds1e\_ctrl.fw](h |
|                          |                          | ttps://wiki.debian.org/s |
|                          |                          | nd-ymfpci)               |
+--------------------------+--------------------------+--------------------------+
| <span                    | *softing CANcard driver, | [softing-4.6/bcard2.bin] |
| id="Firmware-1.line-115" | links PCMCIA card to     | (https://packages.debian |
| class="anchor"></span>   | softing driver*          | .org/file%3Asofting-4.6/ |
| softing\_cs.ko           |                          | bcard2.bin "DebianPkg"){ |
|                          |                          | .interwiki}              |
|                          |                          | [softing-4.6/bcard.bin]( |
|                          |                          | https://packages.debian. |
|                          |                          | org/file%3Asofting-4.6/b |
|                          |                          | card.bin "DebianPkg"){.i |
|                          |                          | nterwiki}                |
|                          |                          | [softing-4.6/cancard.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Asofting-4.6 |
|                          |                          | /cancard.bin "DebianPkg" |
|                          |                          | ){.interwiki}            |
|                          |                          | [softing-4.6/cancrd2.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Asofting-4.6 |
|                          |                          | /cancrd2.bin "DebianPkg" |
|                          |                          | ){.interwiki}            |
|                          |                          | [softing-4.6/cansja.bin] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Asofting-4.6/ |
|                          |                          | cansja.bin "DebianPkg"){ |
|                          |                          | .interwiki}              |
|                          |                          | [softing-4.6/ldcard2.bin |
|                          |                          | ](https://packages.debia |
|                          |                          | n.org/file%3Asofting-4.6 |
|                          |                          | /ldcard2.bin "DebianPkg" |
|                          |                          | ){.interwiki}            |
|                          |                          | [softing-4.6/ldcard.bin] |
|                          |                          | (https://packages.debian |
|                          |                          | .org/file%3Asofting-4.6/ |
|                          |                          | ldcard.bin "DebianPkg"){ |
|                          |                          | .interwiki}              |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Solos PCI driver*       | [solos-db-FPGA.bin](http |
| id="Firmware-1.line-116" |                          | s://packages.debian.org/ |
| class="anchor"></span>   |                          | file%3Asolos-db-FPGA.bin |
| solos-pci.ko             |                          |  "DebianPkg"){.interwiki |
|                          |                          | }                        |
|                          |                          | [solos-Firmware.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Asolos-Firmware.b |
|                          |                          | in "DebianPkg"){.interwi |
|                          |                          | ki}                      |
|                          |                          | [solos-FPGA.bin](https:/ |
|                          |                          | /packages.debian.org/fil |
|                          |                          | e%3Asolos-FPGA.bin "Debi |
|                          |                          | anPkg"){.interwiki}      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [isdn/ISAR.BIN](https:// |
| id="Firmware-1.line-117" |                          | packages.debian.org/file |
| class="anchor"></span>   |                          | %3Aisdn/ISAR.BIN "Debian |
| speedfax.ko              |                          | Pkg"){.interwiki}        |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Adaptec Starfire        | [adaptec/starfire\_rx.bi |
| id="Firmware-1.line-118" | Ethernet driver*         | n](https://packages.debi |
| class="anchor"></span>   |                          | an.org/file%3Aadaptec/st |
| starfire.ko              |                          | arfire_rx.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
|                          |                          | [adaptec/starfire\_tx.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Aadaptec/st |
|                          |                          | arfire_tx.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Tehuti Networks(R)      | [tehuti/bdx.bin](https:/ |
| id="Firmware-1.line-119" | Network Driver*          | /packages.debian.org/fil |
| class="anchor"></span>   |                          | e%3Atehuti/bdx.bin "Debi |
| tehuti.ko                |                          | anPkg"){.interwiki}      |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Broadcom Tigon3         | [tigon/tg3.bin](https:// |
| id="Firmware-1.line-120" | ethernet driver*         | packages.debian.org/file |
| class="anchor"></span>   |                          | %3Atigon/tg3.bin "Debian |
| tg3.ko                   |                          | Pkg"){.interwiki}        |
|                          |                          | [tigon/tg3\_tso5.bin](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Atigon/tg3_tso5. |
|                          |                          | bin "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [tigon/tg3\_tso.bin](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Atigon/tg3_tso.bi |
|                          |                          | n "DebianPkg"){.interwik |
|                          |                          | i}                       |
+--------------------------+--------------------------+--------------------------+
| <span                    | *TI USB 3410/5052 Serial | [mts\_cdma.fw](https://p |
| id="Firmware-1.line-121" | Driver*                  | ackages.debian.org/file% |
| class="anchor"></span>   |                          | 3Amts_cdma.fw "DebianPkg |
| ti\_usb\_3410\_5052.ko   |                          | "){.interwiki}           |
|                          |                          | [mts\_edge.fw](https://p |
|                          |                          | ackages.debian.org/file% |
|                          |                          | 3Amts_edge.fw "DebianPkg |
|                          |                          | "){.interwiki}           |
|                          |                          | [mts\_gsm.fw](https://pa |
|                          |                          | ckages.debian.org/file%3 |
|                          |                          | Amts_gsm.fw "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [mts\_mt9234mu.fw](https |
|                          |                          | ://packages.debian.org/f |
|                          |                          | ile%3Amts_mt9234mu.fw "D |
|                          |                          | ebianPkg"){.interwiki}   |
|                          |                          | [mts\_mt9234zba.fw](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Amts_mt9234zba.fw  |
|                          |                          | "DebianPkg"){.interwiki} |
|                          |                          | [ti\_3410.fw](https://pa |
|                          |                          | ckages.debian.org/file%3 |
|                          |                          | Ati_3410.fw "DebianPkg") |
|                          |                          | {.interwiki}             |
|                          |                          | [ti\_5052.fw](https://pa |
|                          |                          | ckages.debian.org/file%3 |
|                          |                          | Ati_5052.fw "DebianPkg") |
|                          |                          | {.interwiki}             |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [tms380tr.bin](https://p |
| id="Firmware-1.line-122" |                          | ackages.debian.org/file% |
| class="anchor"></span>   |                          | 3Atms380tr.bin "DebianPk |
| tms380tr.ko              |                          | g"){.interwiki}          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *3Com Typhoon Family     | [3com/typhoon.bin](https |
| id="Firmware-1.line-123" | (3C990, 3CR990, and      | ://packages.debian.org/f |
| class="anchor"></span>   | variants)*               | ile%3A3com/typhoon.bin " |
| typhoon.ko               |                          | DebianPkg"){.interwiki}  |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[8388 USB WLAN          | [libertas/usb8388.bin](h |
| id="Firmware-1.line-124" | Driver](https://wiki.deb | ttps://packages.debian.o |
| class="anchor"></span>   | ian.org/libertas)*       | rg/file%3Alibertas/usb83 |
| usb8xxx.ko               |                          | 88.bin "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [libertas/usb8388\_v5.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Alibertas/u |
|                          |                          | sb8388_v5.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
|                          |                          | [libertas/usb8388\_v9.bi |
|                          |                          | n](https://packages.debi |
|                          |                          | an.org/file%3Alibertas/u |
|                          |                          | sb8388_v9.bin "DebianPkg |
|                          |                          | "){.interwiki}           |
|                          |                          | [libertas/usb8682.bin](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Alibertas/usb86 |
|                          |                          | 82.bin "DebianPkg"){.int |
|                          |                          | erwiki}                  |
|                          |                          | [usb8388.bin](https://pa |
|                          |                          | ckages.debian.org/file%3 |
|                          |                          | Ausb8388.bin "DebianPkg" |
|                          |                          | ){.interwiki}            |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[VIA Networking         | [vntwusb.fw](https://pac |
| id="Firmware-1.line-125" | Wireless LAN USB         | kages.debian.org/file%3A |
| class="anchor"></span>   | Driver](https://wiki.deb | vntwusb.fw "DebianPkg"){ |
| vt6656\_stage.ko         | ian.org/vt665x)*         | .interwiki}              |
+--------------------------+--------------------------+--------------------------+
| <span                    | *USB ConnectTech         | [whiteheat.fw](https://p |
| id="Firmware-1.line-126" | WhiteHEAT driver*        | ackages.debian.org/file% |
| class="anchor"></span>   |                          | 3Awhiteheat.fw "DebianPk |
| whiteheat.ko             |                          | g"){.interwiki}          |
|                          |                          | [whiteheat\_loader.fw](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Awhiteheat_load |
|                          |                          | er.fw "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
+--------------------------+--------------------------+--------------------------+
| <span                    | *TI wl1251 Wireles LAN   | [wl1251-fw.bin](https:// |
| id="Firmware-1.line-127" | Driver Core*             | packages.debian.org/file |
| class="anchor"></span>   |                          | %3Awl1251-fw.bin "Debian |
| wl1251.ko                |                          | Pkg"){.interwiki}        |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [ti-connectivity/wl127x- |
| id="Firmware-1.line-128" |                          | fw-3.bin](https://packag |
| class="anchor"></span>   |                          | es.debian.org/file%3Ati- |
| wl12xx\_sdio.ko          |                          | connectivity/wl127x-fw-3 |
|                          |                          | .bin "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [ti-connectivity/wl128x- |
|                          |                          | fw-3.bin](https://packag |
|                          |                          | es.debian.org/file%3Ati- |
|                          |                          | connectivity/wl128x-fw-3 |
|                          |                          | .bin "DebianPkg"){.inter |
|                          |                          | wiki}                    |
+--------------------------+--------------------------+--------------------------+
| <span                    | *(none)*                 | [ti-connectivity/wl127x- |
| id="Firmware-1.line-129" |                          | fw-3.bin](https://packag |
| class="anchor"></span>   |                          | es.debian.org/file%3Ati- |
| wl12xx\_spi.ko           |                          | connectivity/wl127x-fw-3 |
|                          |                          | .bin "DebianPkg"){.inter |
|                          |                          | wiki}                    |
|                          |                          | [ti-connectivity/wl128x- |
|                          |                          | fw-3.bin](https://packag |
|                          |                          | es.debian.org/file%3Ati- |
|                          |                          | connectivity/wl128x-fw-3 |
|                          |                          | .bin "DebianPkg"){.inter |
|                          |                          | wiki}                    |
+--------------------------+--------------------------+--------------------------+
| <span                    | *Yam amateur radio modem | [yam/1200.bin](https://p |
| id="Firmware-1.line-130" | driver*                  | ackages.debian.org/file% |
| class="anchor"></span>   |                          | 3Ayam/1200.bin "DebianPk |
| yam.ko                   |                          | g"){.interwiki}          |
|                          |                          | [yam/9600.bin](https://p |
|                          |                          | ackages.debian.org/file% |
|                          |                          | 3Ayam/9600.bin "DebianPk |
|                          |                          | g"){.interwiki}          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[Driver for ZyDAS       | [zd1201-ap.fw](https://w |
| id="Firmware-1.line-131" | ZD1201 based USB         | iki.debian.org/zd1201)   |
| class="anchor"></span>   | Wireless                 | [zd1201.fw](https://wiki |
| zd1201.ko                | adapters](https://wiki.d | .debian.org/zd1201)      |
|                          | ebian.org/zd1201)*       |                          |
+--------------------------+--------------------------+--------------------------+
| <span                    | *[USB driver for devices | [zd1211/zd1211b\_ub](htt |
| id="Firmware-1.line-132" | with the ZD1211          | ps://packages.debian.org |
| class="anchor"></span>   | chip.](https://wiki.debi | /file%3Azd1211/zd1211b_u |
| zd1211rw.ko              | an.org/zd1211rw)*        | b "DebianPkg"){.interwik |
|                          |                          | i}                       |
|                          |                          | [zd1211/zd1211b\_uphr](h |
|                          |                          | ttps://packages.debian.o |
|                          |                          | rg/file%3Azd1211/zd1211b |
|                          |                          | _uphr "DebianPkg"){.inte |
|                          |                          | rwiki}                   |
|                          |                          | [zd1211/zd1211b\_ur](htt |
|                          |                          | ps://packages.debian.org |
|                          |                          | /file%3Azd1211/zd1211b_u |
|                          |                          | r "DebianPkg"){.interwik |
|                          |                          | i}                       |
|                          |                          | [zd1211/zd1211\_ub](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Azd1211/zd1211_ub  |
|                          |                          | "DebianPkg"){.interwiki} |
|                          |                          | [zd1211/zd1211\_uphr](ht |
|                          |                          | tps://packages.debian.or |
|                          |                          | g/file%3Azd1211/zd1211_u |
|                          |                          | phr "DebianPkg"){.interw |
|                          |                          | iki}                     |
|                          |                          | [zd1211/zd1211\_ur](http |
|                          |                          | s://packages.debian.org/ |
|                          |                          | file%3Azd1211/zd1211_ur  |
|                          |                          | "DebianPkg"){.interwiki} |
+--------------------------+--------------------------+--------------------------+

</div>

<p>
<span id="Firmware-1.line-133" class="anchor"></span><span
id="Firmware-1.bottom" class="anchor"></span>

</div>

 

Ce tableau est destiné essentiellement à associer modules et microcodes.
Il pourrait être amélioré en listant les noms des paquets
correspondants. <span id="line-62" class="anchor"></span><span
id="line-63" class="anchor"></span>

Microcodes d'ordinateur {#Microcodes_d.27ordinateur}
-----------------------

 

<div>

+--------------------------------------+--------------------------------------+
| [BIOS](https://wiki.debian.org/BIOS) | Présent sur les ordinateurs          |
| <small>([wikipedia](https://en.wikip | appelés compatibles *IBM-PC*         |
| edia.org/wiki/BIOS "WikiPedia"){.int |                                      |
| erwiki})</small>                     |                                      |
+--------------------------------------+--------------------------------------+
| <span id="line-66"                   | Présent sur : \* les systèmes Sun    |
| class="anchor"></span>               | SPARC, \* IBM Power, \* les Apple    |
| [OpenFirmware](https://wiki.debian.o | Macintosh basés sur PowerPC, \* IEEE |
| rg/OpenFirmware)                     | 1275-1994, ...                       |
| connu aussi sous le nom de           |                                      |
| [OpenBoot](https://wiki.debian.org/O |                                      |
| penBoot)                             |                                      |
| <small>([wikipedia](https://en.wikip |                                      |
| edia.org/wiki/Open_Firmware "WikiPed |                                      |
| ia"){.interwiki})</small>            |                                      |
+--------------------------------------+--------------------------------------+
| <span id="line-67"                   | Présent sur : \* les systèmes ia64   |
| class="anchor"></span>               | (Itanium), \* quelques systèmes      |
| EFI                                  | ia32/amd64 (Macintosh Intel,         |
| <small>([wikipedia](https://en.wikip | quelques Dell Servers..), \*         |
| edia.org/wiki/Extensible_Firmware_In | quelques systèmes basés sur          |
| terface "WikiPedia"){.interwiki})</s | [XScale](https://en.wikipedia.org/wi |
| mall>                                | ki/XScale "WikiPedia"){.interwiki}   |
+--------------------------------------+--------------------------------------+
| <span id="line-68"                   | Présent sur quelques très rares      |
| class="anchor"></span>               | cartes mères de PC. Peut être testé  |
| Coreboot (LinuxBIOS)                 | sous QEMU                            |
| <small>([wikipedia](https://en.wikip | <http://www.coreboot.org/QEMU>       |
| edia.org/wiki/Coreboot "WikiPedia"){ |                                      |
| .interwiki})</small>                 |                                      |
+--------------------------------------+--------------------------------------+
| <span id="line-69"                   | Présent sur le [Lemote               |
| class="anchor"></span>               | Yeeloong](https://wiki.debian.org/De |
| PMON2000                             | bianYeeloong)                        |
| <small>([homepage](http://www.pmon20 | et des systèmes embarqués.           |
| 00.com/){.http})</small>             |                                      |
+--------------------------------------+--------------------------------------+

</div>

<div>

Voir en ligne :
[firmware](https://wiki.debian.org/fr/firmware){.spip_out}

</div>
