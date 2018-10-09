---
title: Dotclear, Oups I did it again!
date: 2018-01-13T23:11:07+01:00
layout: post
---
C'est pas parce que je n'utilise plus de *CMS* et donc Dotclear que je ne dois pas parler des projets qui m'interessent! Ce matin j'ai eu le plaisir de voir ceci:

![dotclear](https://open-time.net/public/illustrations/2018/dotclear-2.13.png)

>Avec un changelog pas si petit que ça, finalement (je dis ça à chaque release j’ai l’impression):

	Dotclear 2.13 - 2018-01-13
	===========================================================
	* 🐘 PHP 5.5+ is required
	* 🛡 Security: New password management system (including silent migration)
	* 🛡 Security: Add Referrer-Policy header in admin pages
	* 🛡 Security: Fix potential XSS - thank's Trí Chim Trích for report
	* Dotclear news are now displayed in async way by js
	* Dotclear core update check is now done by async js - a forced check may still be done on <admin>/update.php page
	* Add utf8mb4 driver (MySQL server 5.7.7+)
	* Add target="blank" option in simpleMenu
	* Update CKEditor from 4.6.2 to 4.7.3
	* Update CodeMirror from 5.25.1 to 5.32.1
	* Add required attribute for mandatory fields
	* Fix: Avoid horizontal scrolling table when longest comment's usernames in list of comments
	* Fix: Cope with MySQLi connection via socket
	* Fix: Error messages markup and styling
	* Fix: Set caret at the end of the inserted thing (img, url, blockquote, …) in Legacy editor if current selection is empty
	* Fix: Cope with query part only in SimpleMenu URLs
	* 🐛 → Various bugs and typos fixed
	* 🌼 → Some locales and cosmetic adjustments
	
	Dotclear 2.12.2 - merged in 2.13
	===========================================================
	* Fix: lang attribute was missing on entry alone contexts for currywurst and dotty templatesets
	* Fix: Add http:// protocol before media.dotaddict.org for csp_admin_img
	* Fix: tpl:sysIf blog_lang generated code
	* Fix: Duplicate auto-generated URI (entries)
	* Fix: Do not use border and background on select to use the system aspect of them in Firefox.
	* Fix: For select element, target Safari to cope with font-size select/option problem.
	* Fix: Error messages styling

Enjoy comme disent les grands-bretons !

---

>Sauf qu’à peine avais-je fini de faire cette release le serveur s’est mis HS ! J’arrive même plus à m’y connecter en SSH, c’est ballot :-p
>
>Ah ben maintenant il est ressuscité, ah les nouilles ah \o/
>

[Source](https://open-time.net/post/2018/01/13/Oups-I-did-it-again) 
