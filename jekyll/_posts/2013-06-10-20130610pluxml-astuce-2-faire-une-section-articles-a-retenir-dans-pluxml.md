---
title: PluXml Astuce 2, Faire une section "articles à retenir" dans PluXml
date: 2013-06-10 23:10
layout: post
---

Il suffit de se rendre dans *[paramètre d'affichage](/index.php?tag/paramètre%20d'affichage)* pour modifier le fichier *[sidebar.php](/index.php?tag/sidebar.php)* de notre *[thème](/index.php?tag/thème)* et on rajoute la balise:

      <div class="well"> <h3>Articles à retenir</h3> <ul><?php $plxShow->lastArtList('<li><a href="#art_url" title="#art_title">#art_title</a></li>',5,'005') ?></ul>           </div><!-- /well -->

Une fois enregistré on peut aller voir ce que ça donne!
