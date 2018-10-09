---
layout: post
title:  Welcome to Jekyll!
date:   2018-08-10 20:04:50 +0200
categories: jekyll update
---
J'avais besoin de rendre encore plus simple et lisible le site, je voulais aussi me passer de Disqus qui ne fait pas plaisir à tous, fini donc les commentaires sur le blog, il faudra passer par [le journal du hacker](https://www.journalduhacker.net/) quand le billet y est cité et seulement au cas où il parlerait de libre. 

Mes raisons sont simple, très peu de thèmes Hugo sont totalement "internes", c'est à dire et j'entends par là que la lecture de la page ne fait aucun appel externe, or ce n'est pas le cas pour 90% des thèmes de Hugo, la plupart faisant des appels soit pour les fonts ou pour des scripts. Donc Hugo j’arrête là surtout que j'avais en tête de simplifier l'aspect du site avec un look proche de celui de Jekyll par défaut qui me plaît bien pour sa sobriété. Il y a aussi le cas Pelican, mon favori, il fait beaucoup moins de demande et un thème se rapproche de celui de Jekyll, mais c'est en bootstrap et aussi les images qui ne se mettent pas à la bonne taille, ils explosent la vue, je sais c'est un réglage dans le CSS mais je ne trouve pas, en même temps je n'ai pas envie de chercher plus loin quand je sais qu'un autre fait tout avec aucune demande externe.

Donc me voilà sous Jekyll maintenant, je prends le même chemin que mon ami [Devil505](https://devil505.gitlab.io/). J'en profite donc -comme annoncé plus haut- pour dégager Disqus. La version Pelican sera pour le moment accessible à [cette adresse](https://passiongnulinux.tuxfamily.org/pelican/), il me permet par là de garder une trace de ce qui s'est fait auparavant et de pouvoir importer sans mal ce qui à été fait sur Hugo et même Wordpress avec des soucis de liens/accents/images/looks....

Et puis que serait le site sans les changements annuels?

Pour finir je laisse le "welcome de Jekyll".

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
