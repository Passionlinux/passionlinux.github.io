---
title: "Le blog passe au HTTPS !"
date: 2017-11-18T01:29:22+01:00
layout: post
---
Enfin !!! Ça y est, j'ai fait le nécessaire pour que le site passe au HTTPS uniquement !!!

Pour vous, c'est transparent, [Tuxfamily ayant fait en sorte que les sites soient disponibles en sécurisé ou non](https://www.tuxfamily.org/fr/news/2016040201) , j'ai opté pour une redirection via *.htaccess*, oui je ne me prends pas la tête...

Le *https* permet d'éviter d'intercepter les données entre le serveur et moi, au moment où je me connecte sur mon site en rentrant mes logins/MdP, mais aussi dans un autre contexte, ça évitera à Google de descendre (flinguer) ou d'exclure des recherches PassionGNU/Linux. La politique de Google est en effet de favoriser les sites en HTTPS et de ne plus répertorier les autres.

Alors comme toujours avec moi, c'est fait à l'arrache, sans tester et en directe, mais ça devrait être totalement transparent pour vous, si vous consultez le blog en HTTP ou que vous l'avez dans les favoris en HTTP, la redirection vers HTTPS est automatiquement faite.

![HTTPS](https://upload.wikimedia.org/wikipedia/commons/thumb/d/da/Internet2.jpg/745px-Internet2.jpg)
Image prise chez Wikipédia:  Par Fabio Lanari — Internet1.jpg by Rock1997 modified., GFDL, https://commons.wikimedia.org/w/index.php?curid=20995390
