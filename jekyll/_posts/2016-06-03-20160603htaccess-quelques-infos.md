---
title: HTACCESS, Quelques infos...
date: 2016-06-03 12:35
layout: post
---

<p>
<div class="main">

<div class="chapo surlignable">

### Introduction : {#introduction .spip}

Un petit topo rapide sur les fichiers .htaccess  
Les fichiers .htaccess sont des fichiers de configuration des serveurs
HTTP Apache. Leur particularité est leur emplacement : dans les
répertoires de données du site Web, au lieu du répertoire de
configuration d’Apache. La portée de leur configuration est limitée au
contenu du répertoire où ils résident. Cette particularité apporte deux
principaux avantages : leur gestion peut être déléguée à des
utilisateurs n’ayant pas le droit de gérer le serveur HTTP lui-même ;
les modifications sont prises en compte sans qu’il soit nécessaire de
redémarrer le serveur HTTP.

Les fichiers .htaccess sont notamment utilisés pour configurer des
droits d’accès, des redirections d’URL, des messages d’erreur
personnalisés, et des associations d’extension de nom de fichier à un
layout MIME.

</div>

<div class="texte surlignable">

<div id="outil_sommaire" class="cs_sommaire cs_sommaire_avec_fond">

<div class="cs_sommaire_inner">

<div class="cs_sommaire_titre_avec_fond cs_done">

  

</div>

</div>

</div>

### Quelques lignes rapides {#outil_sommaire_0 .spip}

### Rediriger une URL de manière permanente {#outil_sommaire_1 .spip}

Code HTML :  
`Redirect permanent /news/news-6-13+linuxien-decouvre-windows-7.php /news/0-root/13-linuxien-decouvre-windows-7/`{.spip_code
dir="ltr"}

Et pour un changement de nom de domaine, si on veut récupérer la suite
d’une URL (exemple linuxtricks.asso-linux-online.fr/truc-bidule pour
pointer sur inuxtricks.fr/truc-bidule ) On place le .htaccess sur
l’ancien site (linuxtricks.asso-linux-online.fr) avec ceci dedans :

Code HTML :  
`RedirectMatch 301 /(.*) http://linuxtricks.fr/$1`{.spip_code dir="ltr"}

Ces modifs sont prises en compte par les moteurs de recherche et mettent
à jour leur base de données.

### Redirection temporaire {#outil_sommaire_2 .spip}

Code HTML :  
`Redirect temp / /maintenance.html`{.spip_code dir="ltr"}

Ces modifs ne sont pas prises en compte par les moteurs de recherche.

### Pages d’erreur personnalisées {#outil_sommaire_3 .spip}

Code HTML :

<div class="spip_code" dir="ltr">

`ErrorDocument 403 /intrdit.htmlErrorDocument 404 /erreur.html`

</div>

### Supprimer l’extension .php {#outil_sommaire_4 .spip}

Si on veut que l’URL /truc appelle /truc.php voici ce qu’il faut mettre
dans le htaccess :

Code HTML :

<div class="spip_code" dir="ltr">

`RewriteEngine onRewriteRule ^([^.]+)$ $1.php [NC]`

</div>

### Créer un fichier .htaccess sous Windows {#outil_sommaire_5 .spip}

Ouvrir cmd et se rende dans le dossier du site :

Code BASH :  
`cd C:....`{.spip_code dir="ltr"}

Puis créer le fichier ainsi :

Code BASH :  
`echo >.htaccess`{.spip_code dir="ltr"}

</div>

Voir en ligne : [HTACCESS : Quelques
infos... ](http://www.linuxtricks.fr/wiki/htaccess-quelques-infos){.spip_out}

Merci a Adrien.D de me permettre de copier intégralement son article sur
Linuxtricks selon les termes : [Licence Creative
Commons](https://creativecommons.org/licenses/by-sa/2.0/fr/) ![CC by
SA](http://www.linuxtricks.fr/upload/cc_by_sa_petit.png)

</div>

<p>
</p>

