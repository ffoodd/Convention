Convention d'écriture
=====================

@author Gaël Poupard

@last-modified 2013-07-10

@note Inspiré par la charte du projet Normandie et diverses chartes, citées au fil du document.

@see [Luc Poupard](http://www.kloh.fr "kloh.fr") [@klohFR](https://twitter.com/klohFR "@klohFR")

@see David Bénard [@magicbart](https://twitter.com/magicbart "@magicbart")

La présente charte détaille l'ensemble des règles et/ou recommandations à suivre pour créer ou modifier les fichiers d'un projet web : HTML, CSS, PHP, javascript, microdonnées, images… Il s'agit de règles générales applicables à l'ensemble d'un projet, que chaque intervenant devra(it) respecter.


Généralités
-----------

* Encodage : Tous les fichiers doivent être encodés en UTF-8 sans BOM.
* Indentation : Utiliser 2 espaces pour chaque niveau d'indentation.
* Annotations : Citer les sources & références, et annoter autant que possible le code.
* Espaces : Supprimer les espaces inutiles en bout de ligne.


Règle de nommage
----------------

Les règles suivantes sont valables pour tous les fichiers, à l'exception des fichiers spécifiques : par exemple les templates WordPress qui doivent suivre les règles inhérentes à [la hiérarchie des templates WordPress](http://codex.wordpress.org/fr:Hi%C3%A9rarchie_de_modeles), ou les éléments Zend qui doivent respecter [les standards de Zend](http://framework.zend.com/wiki/display/ZFDEV2/Coding+Standards "Wiki Zend Coding Standard").

* Les noms de fichiers, classes, identifiants et fonctions doivent être :
 * En Français,
 * Sans aucune caractère accentué,
 * Explicites et pertinents ( proscrire les `.bloc` par exemple ),
 * Au singulier,
 * Basés sur la [méthode BEM](http://bem.info/method/) ( originellement conçue pour les sélecteurs CSS, mais que j'aime étendre aux fonctions PHP ou noms de fichiers sources par exemple ).
 
==

* Les images apellées via CSS doivent être intitulées suivant l'élément qu'elles ornent ( par exemple: `body.jpg` ).


Mise en Production
------------------

Lorsque le développement et l'intégration sont terminés, une recette est nécessaire. Il s'agit de parcourir toutes les pages, vérifier toutes les fonctionnalités ainsi que la compatibilité navigateurs. Selon les contraintes du projet, des tests sur différents terminaux et un audit d'accessibilité peuvent être nécessaires. Différents outils peuvent nous y aider. On passera ensuite à l'optimisation technique en vue d'améliorer les performances du site, toujours bénéfique tant aux internautes qu'aux robots.

* Vérifications :
 * Des outils commes [les checklists d'Opquast](http://checklists.opquast.com/fr/ "Open Quality Standard") ou [WebDev Checklist](http://webdevchecklist.com/) devraient être utilisés pour garantir la qualité du projet.
 * Les pages doivent être validées à l'aide du Validator ( cf "Convention HTML" ).
 * Selon les contraintes du projet, des tests de désactivation du css et / ou du js devront être effectués.
 * Procéder à des tests complets sur tous les navigateurs ciblés, et le cas échéant les technologies d'assistance visées.
 * Vérifier l'agrandissement en mode Texte jusqu'à 200%.

*Attention :* chaque concaténation / minification doit se faire après avoir dupliqué les fichiers sources.

* Optimisation CSS :
 * Les fichiers .css doivent être concaténés en un seul fichier `style.css`.
 * Les fichiers .css doivent être conservés tels quels dans un répertoire `/css` dédié.
 * Le fichier final doit être minifié selon les règles suivantes :
  * Supprimer les espaces avant et après les accolades ouvrantes ( `{` ),
  * Supprimer les espaces avant et après les accolades fermantes ( `}` ),
  * Supprimer les espaces avant et après les deux points ( `:` ),
  * Supprimer les espaces avant et après les points-virgules ( `;` ),
  * Supprimer le dernier point-virgule d'une règle ( `; }` ),
  * Supprimer les retours à la ligne,
  * Supprimer les doubles espaces,
  * Supprimer les commentaires.
  * L'outil [CssCompressor](http://www.cssdrive.com/index.php/main/csscompressor "cssdrive.com") peut être utilisé avec les options suivantes: Super Compact, Strip all comments.

==

* Minification : Le code HTML doit être minifé pour le navigateur.

* Optimisation js :
 * Charger les scripts en fin de documents dès que possible.
 * Charger les scripts en asynchrone dès que possible ( les attributs `async` et `defer` sont voués à ça : pour en savoir plus, [un petit tour sur Alsacréations](http://www.alsacreations.com/astuce/lire/1562-script-attribut-async-defer.html "Article sur async et defer par Dew")).
 * Les scripts doivent être minifiés :
  * Concaténer les fichiers ( à l'exception de la lib' utilisée).
  * Supprimer les commentaires.
 * L'outil [jsCompress](http://jscompress.com/ "jscompress.com") peut-être utilisé pour cette opération.

==

Les fichiers .php ne doivent en aucun cas être minifiés.

* Paramètres serveurs ( dans le cas d'un serveur Apache, en passant par le fichier .htaccess )
 * Activer la compression ( Gzip ou Deflate ),
 * Définir un type MIME correct pour chaque type de fichier utilisé,
 * Optimiser la mise en cache navigateur,
 * Supprimer les Etags,
 * Interdire l'accès aux index de répertoire,
 * Personnaliser les pages d'erreur (404, 403).
 * Adapter le fichier `.htaccess` afin d'améliorer la gestion du cache, les performances globales, gérer les autorisations d'accès aux répertoires, personnaliser les pages d'erreur, etc.. Voir l'article à propos du [.htaccess pour WordPress sur Seo-Mix](http://www.seomix.fr/guide-htaccess-performances-et-temps-de-chargement/), dont la plupart des règles sont applicables hors WordPress.

==

* Robots.txt :
 * Éditer le fichier robots.txt ( à minima le lien vers le sitemap ).

==

* Human.txt :
 * Éditer le fichier human.txt afin de créditer tous les participants, les sources et les informations sur le projet.

==

* Réseaux sociaux :
 * Pour les Twitter Cards, il faut déclarer le site sur Twitter ( cf [la FAQ du plugin par jmlapam](http://wordpress.org/plugins/jm-twitter-cards/faq/) a.k.a TweetPress ) ainsi que [la documentation Twitter](https://dev.twitter.com/docs/cards).
 * Pour Google author également, lier un compte Google+ au site : [les instructions de Google](https://plus.google.com/authorship "Associez votre profil Google+ au contenu que vous créez").

==

* Liens brisés :
 * Utilisez un outil comme [Xenu](http://home.snafu.de/tilman/xenulink.html) pour vérifier qu'aucun lien ne manque (fichiers, images, liens sortants, liens internes, etc).

==

* Références & outils :
 * [Theme-Check](http://wordpress.org/plugins/theme-check/ 'Theme-Check sur le repostory des plugins')
 * [Conventions WordPress sur la déclaration des thèmes](http://codex.wordpress.org/Theme_Development#Theme_Stylesheet "Explications sur le Codex")
 * [PageSpeed](http://developers.google.com/speed/pagespeed/insights) ( existe également en extention pour Chrome et Firefox, ainsi qu'en module pour Apache et Nginx ).
 * [WebPageTest](http://www.webpagetest.org)
 * [GTMetrix](http://gtmetrix.com/)
 * [Pingdom Tools](http://tools.pingdom.com/fpt/)
 * [jsCompress](http://jscompress.com/ "jscompress.com")
 * [CssCompressor](http://www.cssdrive.com/index.php/main/csscompressor "cssdrive.com")
 * [les checklists d'Opquast](http://checklists.opquast.com/fr/ "Open Quality Standard")
 * [WebDev Checklist](http://webdevchecklist.com/)
 * [bpi-checklist](https://github.com/inseo/bpi-checklist/blob/master/checklist.md "La checklist des 'Bonnes Pratiques de l'intégration Web'")
 * [.htaccess sur Seo-Mix](http://www.seomix.fr/guide-htaccess-performances-et-temps-de-chargement/)
 * [robots.txt sur GeekPress](http://www.geekpress.fr/wordpress/astuce/fichier-robots-txt-optimise-wordpress-503/ "Fichier robots.txt optimisé pour WordPress")
 * [wp-config sur seo-mix](http://www.seomix.fr/wp-config-vitesse/ "Daniel Roch / seo-mix vous conseille sur la modification du wp-config")
 * [Validation Twitter par TweetPress](http://wordpress.org/plugins/jm-twitter-cards/faq/)
 * [La documentation Twitter](https://dev.twitter.com/docs/cards)
 * [Les instructions de Google](https://plus.google.com/authorship "Associez votre profil Google+ au contenu que vous créez")
 * [Xenu](http://home.snafu.de/tilman/xenulink.html)
 * [Hardening WordPress](http://codex.wordpress.org/Hardening_WordPress)
 * [Async et defer par Dew](http://www.alsacreations.com/astuce/lire/1562-script-attribut-async-defer.html "Article sur async et defer par Dew")