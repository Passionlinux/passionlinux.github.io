---
title: Utilisation de GnuPG et debsign
date: 2017-02-21 23:39
layout: post
---

[Toujours repris de la documentation de
Debian-facile.](https://debian-facile.org/doc:mentors:signer-un-paquet)
Quand on commence a faire ses propres paquets, on sent très vite le
besoin de signer ses paquets pour plus de sécurité.  

Introduction {#introduction .sectionedit2}
------------

<div class="level2">

-   <div class="li">

    Créer une paire de clés GPG dédiés à vos contribution Debian

    </div>

-   <div class="li">

    Configurer Debsign pour qu'il utilise cette clé par défaut

    </div>

</div>

<div class="secedit editbutton_section editbutton_2">

</div>

<!--more-->

Générer une paire de clés GPG {#generer-une-paire-de-cles-gpg .sectionedit3}
-----------------------------

<div class="level2">

Utilisés pour signer (ou chiffrer) les courriels et les paquets Debian.

</div>

### Installation

<div class="level3">

``` {.code .root}
apt-get install gnupg
```

</div>

### Génération {#generation}

<div class="level3">

</div>

#### Génération de la clé privée GPG {#generation-de-la-cle-privee-gpg}

<div class="level4">

``` {.code .user}
gpg --gen-key
```

</div>

#### Génération du certificat de révocation {#generation-du-certificat-de-revocation}

<div class="level4">

Remplacer XXXXXXXX par l'ID de la clé :
``` {.code .user}
gpg --output revoke.asc --gen-revoke XXXXXXXX
```

</div>

#### Génération de la clé publique {#generation-de-la-cle-publique}

<div class="level4">

``` {.code .user}
gpg --output ~/votre-login.gpg --export votre@adresse-email.org
```

</div>

#### Génération de la clé publique version ASCII {#generation-de-la-cle-publique-version-ascii}

<div class="level4">

``` {.code .user}
gpg --armor --export votre@adresse-email.org
```

GPG Agent {#gpg-agent .sectionedit4}
---------

<div class="level2">

Pour ne pas avoir à retaper la passphrase à chaque signature, on peut
utiliser `gpg-agent`, qui fonctionne de la même manière que `ssh-agent`.
Pour ce faire, il faut rajouter au fichier `~/.gnupg/gpg.conf` le code
suivant:

[\~/.gnupg/gpg.conf](https://debian-facile.org/_export/code/doc:mentors:signer-un-paquet?codeblock=5 "Télécharger un extrait"){.mediafile .mf_conf}

:   ``` {.code .text}
    use-agent
    ```

</div>

<div class="secedit editbutton_section editbutton_4">

</div>

Signer un paquet avec debsign {#signer-un-paquet-avec-debsign .sectionedit5}
-----------------------------

<div class="level2">

</div>

### Installation {#installation1}

<div class="level3">

``` {.code .root}
apt-get install devscripts
```

</div>

### Configuration

<div class="level3">

Dans son dossier personnel, ajouter au fichier `~/.devscripts` (à créer
s'il n'existe pas) la ligne suivante :
``` {.code .bash}
DEBSIGN_KEYID=0xXXXXXXXX
```

En remplaçant 0xXXXXXXXX par l'id de votre clé GPG.

</div>

### Utilisation

<div class="level3">

``` {.code .user}
debsign nom-du-paquet_version-revision_arch.changes
```

</div>

</div>
