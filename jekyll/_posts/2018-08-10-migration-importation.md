---
title: En cours d'importation vers Jekyll.
date: 2018-08-10 23:20
layout: post
---

Me voila donc sur un Jekyll tout neuf et propre, aucune demande externe au site et je trouve ça cool et plus honnête. Les billets de Pelican / Hugo sont en cours d'importation, il y a toujours un petit truc à faire, normale quand dés le départ on ne suit pas les bonnes recommandations d'un nommage de fichiers, je balançais les noms des fichiers du type je-raconte-my-life.md au lieu de 2018-08-10-je-raconte-my-life.md.

Et puis certains champs sont à changer, pour ça j'ai mon ami `sed, il s’emploie de cette manière:

	sed -e 's/type/layout/g' -i *

Donc un peu de patience et ça sera bon:).

