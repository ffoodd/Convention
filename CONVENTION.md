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


Charte CSS
----------

* Encodage : Déclarer le charset `@charset "UTF-8";` en tout début de fichier.

* Indentation : Utiliser 2 espaces pour chaque niveau d'indentation. *Les tabulations sont proscrites.*

* Espaces : Supprimer les espaces inutiles en bout de ligne.

* Information : Les fichiers doivent débuter par une introduction rédigée en suivant le format [CSSdoc](http://cssdoc.net/ "CSSDoc").

* Sectionnement : Scinder en sections majeures le fichier, dont l'intitulé sera composé comme suit : `/* == @section ==================== */` ( 2 signes `=`, le tag `@section`, et 20 signes `=` ). Chaque titre de section sera précédé de deux sauts de ligne.

* Chapitrage : Scinder en chapitres les sections principales, dont l'intitulé sera composé de la même façon que celui des sections. Cependant le tag sera `@subsection` et le signe `=` est remplacé par le signe `-`. Chaque titre de chapitre sera précédé d'un saut de ligne.

* Sommaire : Un sommaire doit récapituler et répertorier les sections et chapitres, respectivement précédé d'un `==` ou d'un `--`.

* Annotations : Citer les sources & références, et annoter autant que possible le code.

* Commentaires :
 * Placer systématiquement le commentaire sur la ligne au dessus du sélecteur, lorsqu'il concerne l'ensemble du groupe de règles.
 * Commenter systématiquement les valeurs arbitraires ou issues d'un calcul, afin de permettre une bonne appréhension des styles.
 * Exception lorsque le commentaire concerne une règle particulière : il est placé à l'intérieur du bloc de règles, mais à la ligne précédant la règle concernée.
 * Le format des commentaires respectera également le format CSSDoc.

==

* Sélecteurs :
 * Un seul sélecteur par ligne.
 * Une déclaration par ligne au sein du bloc de règles.
 * Les règles sont ferrées à gauche.
 * Un espace avant l'accolade ouvrante ` {`.
 * Un espace après les deux-points `: ` d'une règle.
 * Un point-virgule `;` à la fin de *chaque* règle.
 * L'accolade de fermeture `}` est placée à la ligne après la dernière règle et au même niveau d'indentation que le(s) sélecteur(s) au(x)quel(s) s'appliquent les déclarations.
 * Une ligne est sautée entre chaque bloc de règles.
 * Éviter de surqualifier les sélecteurs : *ne jamais indiquer l'élément HTML dans un sélecteur qui contient une classe ou un ID*. La seule exception acceptable concerne les sélecteurs d'attributs, mais même dans ce cas il faut tenter de s'en passer.
 * Les sélecteurs d'adjacence, d'enfant ou d'attributs doivent être évités autant que possible, car ils nuisent à la performance globale.
 * De même les sélecteurs doivent être courts, une seule cible par sélecteur est l'idéal.
 * Les sélecteurs d'attributs doivent utiliser des guillemets doubles ( `type="radio"` ).
 * Dans tous les cas utilisant des guillemets, préférer les guillemets doubles.
 * Exception : Dans le cas d'une déclaration contenant une seule règle *et* un seul sélecteur, ne pas la mettre à la ligne mais préférer insérer un espace avant et après les accolades (`.classe { margin: 0; }`).

==

* Classes et identifiants :
 * Limiter au maximum l'utilisation d'identifiants.
 * Les classes et identifiants - et, de fait, les sélecteurs - doivent être écrits en minuscules. *NB :* le CamelCase est interdit.

==

* Valeurs :
 * Toutes les propriétés doivent utiliser leur syntaxe raccourcie quand c'est possible.
 * La valeur des couleurs simples doit se faire en hexadécimal raccourci ( `#fff` pour le blanc )
 * Utiliser des bas de casses pour les valeurs hexadécimales.
 * La valeur des couleurs complexes doit se faire autant que possible en `hsl` / `hsla` avec un fallback en `rgb` pour *IE8 et -* . ( cf [l'article de Vincent De Oliveira](http://blog.iamvdo.me/post/46251119961/les-avantages-de-hsl-par-rapport-a-rgb) ).
 * Les corps de texte doivent être formulés en `em` (avec un fallback en `px` pour *IE7 et - s'ils sont supportés*).
 * Les hauteurs doivent être formulées en `em` afin de conserver le rythme vertical.
 * Les *marges* ( `margin` et `padding` ) doivent également être formulées en `em`.
 * Les largeurs doivent être formulées en `%` afin de simplifier les calculs de largeurs cumulées.
 * Les chiffres magiques ( arbitraires, ex : `37px` ) sont à bannir : toutes les valeurs doivent être exprimées de façon relative.
 * Ne pas préciser d'unité pour les valeurs nulles (`0`) lorsque c'est autorisé.
 * Ne pas préciser le `0` dans les valeurs décimales inférieures à `1` ( `0.2` => `.2` ).
 * Toujours ajouter une espace après une virgule dans les valeurs complexes ( comme `hsla`, Ex: `hsla( 0, 0, 0, .5)`.
 * Proscrire l'emploi de `!important`.
 * Dans le cas des préfixes vendeurs, ferrer à gauche les règles *et* les valeurs ( après les deux points ).
 * Exception : Dans le cas d'une valeur complexe, il convient de la scinder en plusieurs lignes avec une indentation supplémentaire pour en faciliter la lecture ( notamment les dégradés ).

==

* Liens :
 * Les liens doivent être stylés en suivant [la méthode LoVeHAte](http://meyerweb.com/eric/css/link-specificity.html "Article d'Eric Meyer") comme suit :
 * `a:link { }` : pour les liens non visités.
 * `a:visited { }` : pour les liens visités.
 * `a:hover { }` : pour les liens survolés.
 * `a:active { }` : pour les liens actifs.

==

* Navigation : La navigation au clavier doit être facile et claire, la prise de `:focus` doit être visuellement indiquée.

* Media Queries :
 * Les requêtes médias doivent être indentées logiquement, afin que leur imbrication soit visuellement parlante ( les déclarations au sein d'une requête auront un niveau d'indentation suplémentaire par rapport aux déclarations hors requêtes ).
 * Les requêtes médias sont ordonnées de la contrainte la plus basse à la contrainte la plus haute, de façon cumulative ( penser "Mobile First" ).

==

* Images :
 * Les images ajoutées via CSS doivent être purement décoratives, et leur nom doit indiquer l'élément qu'elles ornent.
 * Les images présentes sur l'ensemble des pages - ou presque - doivent être regroupées en sprite, au format `.png` de préférence.
 * Les `.png` doivent être optimisés : en `png-8` quand c'est possible, et avec des outils tels que [PngOptimizer](http://psydk.org/PngOptimizer.php "Optimisateur de png").
 * Les petites images spécifiques à certaines pages ne doivent pas être ajoutées au sprite, mais peuvent être converties en DataURI ( encodage en base64 ). Des sites comme [Duri.me](http://duri.me/ "Encoder une image en base64") permettent une conversion très simple.

==

* Typographies :
 * Un rythme vertical est primordial, issue d'une échelle typographique clairement définie. Elle est personnalisable via [cet outil](http://soqr.fr/vertical-rhythm/ "Générateur de rythme vertical").
 * L'utilisation de polices exotiques doit se faire à l'aide de `@font-face` ou de services tels que [Typekit](https://typekit.com/ "Typekit").
 * Un fallback correct doit être fourni pour chaque police exotique. Deux outils à votre secours : le [font-stack builder](http://www.codestyle.org/servlets/FontStack?stack=Palatino%20Linotype,Palatino,FreeSerif&generic= "CodeStyle") et [FFFALLBACK](http://ffffallback.com/"Le bookmarklet FFFALLBACK").
 * Un dernier recours doit être fourni sous la forme d'une famille générique ( ex : `sans-serif` ).
 * Les formats `.woff` et `.eot` suffisent dans la plupart des cas.
 * Éviter l'emploi de faux-gras et faux-italiques ( id est : généré par le navigateur en l'absence de fichier dédié ).
 * Il est fortement déconseillé d'utiliser plus de trois typographies ( leur déclinaison en graisse(s) est recommandée ).

==

* Compatibilité :
 * Dans le cas de règles expérimentales ou anciennes, ajouter un commentaire pour spécifier le navigateur / version ciblé(e) ( CSSDoc prévoit le duo `@bugfix` et `@affected` ).
 * Dégradés : un outil tel que [CSS Gradient Generator](http://www.colorzilla.com/gradient-editor/ "Générateur de dégradé") doit être utilisé pour les dégradés, afin de maximiser la compatibilité.
 * Dégradés : les dégradés sont des valeurs de `background-image` : il faut définir un fallback à l'aide de `background-color`, et ne surtout pas les appliquer directement en tant que `background` !
 * Les préfixes vendeurs doivent précéder la version non-préfixée.
 * Les styles spécifiques à IE8 et inférieur doivent être inséré dans un fichier `ie.css` dédié.
 * Les styles spécifiques à IE8 et inférieur s'appuient sur des classes conditonnelles appliquées à `<html>`.
 * Une couleur de fond doit être appliquée au `<body>`, au cas ou un navigateur appliquerait une couleur incorrecte.
 * Aucun hack n'est autorisé : chaque problème appelle une solution propre.
 * Une classe `js` / `no-js` doit permettre d'appliquer des styles en fonction de l'activation du javascript, lorsque les data-attributs ne suffisent pas.
 * Éviter les filtres propriétaires de Microsoft : la transparence ou les dégradés sont souvent de simples ornements, dispensables dans le cadre d'une dégradation gracieuse comme d'une amélioration progressive.
 * Si besoin de distinguer un élément au sein d'un groupes d'éléments identiques ( Ex : un `<li>` dans un `<ul>` ), préférer distinguer le premier élément plutôt que le dernier. `:first-child` dispose d'une meilleure compatibilité que son jumeau maléfique `:last-child`, et le nombre total peut varier ce qui rend le dernier élément volatile, tandis qu'on est sûr de toujours avoir un premier élément.

==

* Ordre des déclarations : par ordre alphabétique, car c'est une méthode plus simple à appréhender.

* Exemple :

```css
/* == @section Une section ==================== */
/* @note : Notes à propos de la section  */

/* Un commentaire sur le bloc */
.exemple,
.exemple--2 {
  display: block;
  background: #fff; /* Un commentaire sur la règle */
}

.exemple--2::after {
  content: "Mon contenu";
  display: block;
  position: relative;
  box-shadow:
    1px 1px 0 #333,
    2px 2px 0 #444,
    3px 3px 0 #555;
  -webkit-transition: all 1s linear; /* @affected Chrome 26-, Safari, Ios Safari, Androïd, Blackberry */
  transition:         all 1s linear;
}

.exemple--3 { display: none; }
```

==

* Références & Inspirations :
 * [WordPress CSS Coding Standards](http://make.wordpress.org/core/handbook/coding-standards/css/ "Le guide de contribution à WordPress")
 * [Google Style Guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml "Recommandations Google")
 * [Interactive Guide to Blog Typography](http://www.kaikkonendesign.fi/typography/section/1 "Guide interactif de l'usage des typographies sur le web")
 * [Charte CSS](http://css.thenew.fr/ "Charte CSS par Rémy Barthez, intégrateur")  par Rémy Barthez
 * [Idiomatic CSS](https://github.com/DirtyF/idiomatic-css/tree/master/translations/fr-FR "Principes d'écriture pour des CSS cohérents et idiomatiques") par Nicolas Gallagher
 * [BBC's Standards & Guidelines](http://www.bbc.co.uk/guidelines/futuremedia/technical/css.shtml "V1.3")
 * [CSS Guidelines](https://github.com/csswizardry/CSS-Guidelines) par CSSWizardry
 * [CSSdoc](http://cssdoc.net/ "CSSDoc")
 * [knacss](http://knacss.com/)
 * [RÖCSSTI](http://rocssti.nicolas-hoffmann.net/)
 * [OOCSS](http://oocss.org/ "oocss.org")
 * [BEM](http://bem.info/method/)
 * [CSS Wizardry](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
 * [Vincent De Oliveira sur hsla](http://blog.iamvdo.me/post/46251119961/les-avantages-de-hsl-par-rapport-a-rgb)
 * [LVHA par Eric Meyer](http://meyerweb.com/eric/css/link-specificity.html "Article d'Eric Meyer")
 * [Générateur de rythme vertical](http://soqr.fr/vertical-rhythm/ "Générateur de rythme vertical")
 * [Typekit](https://typekit.com/ "Typekit").
 * [Font-stack Builder](http://www.codestyle.org/servlets/FontStack)
 * [FFFALLBACK](http://ffffallback.com/"Le bookmarklet FFFALLBACK")
 * [CSS Gradient Generator](http://www.colorzilla.com/gradient-editor/ "Générateur de dégradé")
 * [CSSLisible](https://github.com/Darklg/CSSLisible/blob/master/inc/valeurs.php "Le rangement des valeurs selon CSSLisible")
 * [PngOptimizer](http://psydk.org/PngOptimizer.php "Optimisateur de png")
 * [Duri.me](http://duri.me/ "Encoder une image en base64")

Charte HTML
-----------

* Doctype : Utiliser le doctype HTML5 `<!DOCTYPE html>`.

* Encodage : Spécifier l'encodage via la balise meta dédiée `<meta charset="utf-8">`.

* Langue : La langue doit être spécifiée sur la balise `<html>` ( ex: `lang="fr-FR"` ).

* Organisation du `<head>` :
 * La `<meta charset="utf-8">` doit être le premier enfant du `<head>`.
 * La balise `<title>` doit venir en deuxième position.
 * Ajouter la balise `<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">` en vue d'améliorer le rendu sur IE.
 * La balise `<base>` est également primordiale et doit être spécifiée.

==

* Indentation : Utiliser 2 espaces pour chaque niveau d'indentation.

* Espaces : Supprimer les espaces inutiles en bout de ligne.

* Écriture : Les balises et attributs doivent être rédigés en minuscules ( *CamelCase prohibé* ).

* Retours chariots : Revenir à la ligne à chaque ouverture de balise, et indenter en conséquence. Reformulé : une seule balise par ligne.

* Sémantique : Utiliser les balises en fonction de leur signification et non de leur mise en forme : le choix des balises doit se faire indépendamment de la présentation et du comportement. Un détail de chaque balise et de son sens est disponible sur [HTML5 Doctor](http://html5doctor.com/ "Index des éléments HTML5").

* Organisation : La hiérarchie des titres doit être cohérente et claire.

* Validation : Créer du code validé par le [W3C Validator](http://validator.w3.org/ "Validator") dans la mesure du possible.

* Commentaires : Commenter la fermeture de chaque balise importante en HTML, puis sauter une ligne. L'importance dépend du seul jugement de l'auteur. *L'intérêt est de faciliter l'orientation dans le code source.*

* Multimédias : Fournir des alternatives aux médias ( attributs `alt`, sous-titres, etc...).

* Fermeture de balise : Chaque balise doit être correctement fermée; les balises auto-fermantes doivent contenir un espace avant le slash de fermeture.

* Attributs :
 * Ne pas fournir l'attribut `type` pour les styles et scripts.
 * Utiliser des guillemets doubles pour cerner les valeurs des attributs.
 * Spécifier les *rôles ARIA* dès que possible ( cf: [WAI ARIA](http://www.w3.org/TR/wai-aria/ "La recommandation du W3C") ).
 * Ajouter les *microdonnées* lorsque c'est utile ( cf: [schema.org](http://schema.org/docs/full.html "Liste des microdonnées") ).
 * L'attribut `style` ne doit pas être utilisé.
 * Dans le cas de nombreux attributs, on envisagera de revenir à la ligne entre chaque attribut afin d'améliorer la lisibilité.

==

* Ordre des attributs :
 1. `class` : valoriser l'utilisation des classes par rapport aux IDs pour les CSS.
 2. `id`
 3. `role`
 4. `data-*` : pour servir de crochet au javascript.
 5. `aria-*` : pour l'accessibilité et la sémantique.
 6. autre(s) : href, title, alt, microdonnées, etc...

==

* Métadonnées :
 * Ajouter le profil [DublinCore](http://dublincore.org/documents/2008/08/04/dc-html/ "Profil DublinCore") sur `<html>`.
 * Les métas DublinCore, OpenGraph et TwitterCard doivent être renseignées.

==

* Les favicon, Apple icon et tuiles Windows doivent être fournies aux formats demandés :
 * `apple-touch-icon-144x144.png`
 * `apple-touch-icon-114x114.png`
 * `apple-touch-icon-72x72.png`
 * `apple-touch-icon.png`
 * `favicon.ico` (48x48)
 * `favicon.png` (32x32)
 * `favicon-128.png`
 * `favicon.ico` (16x16)
* Pour ce faire, utiliser le fichier `favicons.psd` :
 * Modifiez le premier objet dynamique en y incluant votre image (logo ou autre), enregistrez l'objet puis le `psd`.
 * Choisissez "Enregistrer pour le web", au format `png-24`. Toutes les images nécessaires seront exportées, déjà nommées correctement.
 * Convertissez les fichiers dont le nom se termine par "-ico.png" au format `.ico` via [favicon.cc](http://www.favicon.cc/ 'Convertissez vos png en ico') et les renommer en `favicon.ico`.
 * *Exception* : le `favicon.ico` de 16x16 pixel doit être placé à la racine du site.
 * Optimisez vos `.png` à l'aide de [PNG Optimizer](http://psydk.org/PngOptimizer.php) par exemple, et le tour est joué !

==

* Formulaires :
 * Chaque champ est associé à un label, avec les attributs `for` et `aria-labelled-by`.
 * Le format attendu est indiqué sous forme de légende à côté du champ.
 * Les placeholders ne doivent pas être la seule indication du format attendu.
 * L'attribut `type` doit être utilisé efficacement.
 * Les champs obligatoires sont indiqués par une indication textuelle à côté du label, mais aussi via les attributs `required` et `aria-required`.
 * Les erreurs sont retournées champ par champ, avec un intitulé explicitant l'erreur.
 * Le succès d'une soumission est également explicité textuellement.
 * Les contraintes de chaque champ sont indiquées à côté de celui-ci ( masque de saisie, sensibilité à la casse, nombre de caractères... ).

==

* Tableaux :
 * Chaque tableau de données doit disposer d'un titre.
 * Les en-têtes sont correctement balisées ( `<th>` ).
 * Les cellules doivent être reliées à leur en-tête ( `headers=""` ).

==

* Liens :
 * Chaque lien est doté d'un intitulé utile, décrivant sa fonction et/ou sa cible.
 * Éviter les intitulés passe-partout (en savoir plus, cliquez ici).
 * Le soulignement est réservé aux liens, afin de les distinguer visuellement.
 * Les liens visités ont un style particulier, différenciant.
 * Les liens externes sont distingués visuellement.
 * Éviter l'emploi de `<a href="#">` comme bouton d'action; préferer `<button type="button">`.

==

* Annotations : Citer les sources & références, et annoter autant que possible le code.

* La première occurrence d'un `<abbr>` doit permettre d'accéder à sa signification.

* La capitalisation à des fins décoratives doit être faite via CSS.

* Les mots ne comportent ni espaces ni balisage interne (`<span>`L`</span>`ettrine).

* Compatibilité :
 * S'appuyer sur des commentaires conditionnels pour cibler les versions d'IE.
 * Une classe `no-js` doit être présente sur `<html>` afin de tester l'activation du js.

==

* Limiter au maximum la profondeur du DOM, ainsi que le nombre d'éléments.

==

* Exemple :

```html
<header role="banner">
  <h1 itemprop="name">Exemple</h1>
</header>
<!-- /header -->

<hr />
<main role="main">
</main>
<!-- /main -->
```

==

* Références & Inspirations :
 * [WordPress HTML Coding Standards](http://make.wordpress.org/core/handbook/coding-standards/html/ "Le guide de contribution à WordPress")
 * [Google Style Guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml "Recommandations Google")
 * [BBC's Standards & Guidelines](http://www.bbc.co.uk/guidelines/futuremedia/technical/xhtml_integrity.shtml)
 * [W3C Validator](http://validator.w3.org/ "Validator")
 * [schema.org](http://schema.org/docs/full.html "Liste des microdonnées")
 * [WAI ARIA](http://www.w3.org/TR/wai-aria/ "La recommandation du W3C")
 * [DublinCore](http://dublincore.org/documents/2008/08/04/dc-html/ "Profil DublinCore")
 * [Idiomatic HTML](https://github.com/necolas/idiomatic-html/)
 * [HTML5 Boilerplate Favicon PSD Template](http://drublic.de/blog/html5-boilerplate-favicons-psd-template/)
 * [favicon.cc](http://www.favicon.cc/ 'Convertissez vos png en ico')
 * [PNG Optimizer](http://psydk.org/PngOptimizer.php)


Charte Javascript
-----------------

Ça n'est pas ma spécialité, vous voilà prévenus ! Ces recommandations sont issues de ma pratique du javascript, majoritairement limitée à l'utilisation de jQuery et de ses acolytes de plugin. Elles ne conviendront peut-être pas à votre projet, voire seront même contre-indiquées par la librairie que vous utilisez !

* Indentation : Utiliser 2 espaces pour chaque niveau d'indentation.

* Retours chariots : Revenir à la ligne entre chaque fonction, et indenter en conséquence.

* Accolades : L'accolade ouvrante doit être sur la même ligne que la définition de la fonction et précédée d'une espace; l'accolade fermante doit être isolée sur la ligne suivant la dernière déclaration de la fonction.

* Parenthèses : Toujours cerner les parenthèses d'espace `if ( this ) ` y compris dans les opérations. Ex: `i = ( 20 + 30 ) - 17`;.

* Espaces : Supprimer les espaces inutiles en bout de ligne.

* Ligne seule : Rester sur une seule ligne si une seule action est executée dans un `if`, `for` ou `while`.

* Commentaires :
 * Commenter la fermeture de chaque fonction.
 * Annoter les fonctions et plugins particuliers ( cf point suivant "Annontations" ).
 * Expliquer les fonctions dont la lecture n'est pas naturelle.

==

* Manipulation du DOM : préférer s'appuyer sur des attributs `data-` que sur des classes ou des identifiants.

* Annotations : Citer les sources & références, et annoter autant que possible le code.

* Organisation : Chaque script doit être isolé à l'aide d'un bloc de commentaires respectant [JSDoc](http://usejsdoc.org/ "Documentation JSDoc").

* Sommaire : Si plusieurs scripts sont cumulés, on créera un sommaire détaillant leur ordre d'apparition dans le fichier.

* Guillemets : Toujours utiliser des guillemets doubles.

* Erreurs : Simple bon sens, les scripts ne doivent générer aucune erreur Javascript.

* Références & inspirations :
 * [WordPress JS Coding Standard](http://make.wordpress.org/core/handbook/coding-standards/javascript/)
 * [JSLint](http://www.jslint.com/)
 * [JSDoc](http://usejsdoc.org/ "Documentation JSDoc")
 * [jQuery](http://www.jquery.com "jquery.com")
 * [Zepto](http://zeptojs.com/ "En savoir plus sur Zepto")
 * [data-js selectors](http://toddmotto.com/data-js-selectors-enhancing-html5-development-by-separating-css-from-javascript/ "data-js selectors, enhancing HTML5 development by separating CSS from JavaScript")

Charte PHP
----------

*Attention* : ces conventions sont conséquentes d'une utilisation récurrente de WordPress, et ne conviennent pas à tous les cas d'utilisation ( notamment Zend qui dispose [d'un standard de codage](http://framework.zend.com/wiki/display/ZFDEV2/Coding+Standards) particulier, et souvent contradictoire avec mes propres recommandations ).

* Indentation : Utiliser 2 espaces pour chaque niveau d'indentation.

* Retours chariots : Revenir à la ligne entre chaque fonction, et indenter en conséquence.

* Accolades : L'accolade ouvrante doit être sur la même ligne que la définition de la fonction et précédée d'une espace; l'accolade fermante doit être isolée sur la ligne suivant la dernière déclaration de la fonction.

* Accolades : ouvrir et fermer les accolades pour chaque `if`, `else`, `elseif`, `while`, `swicth`, etc comme conseillé dans [la convention Zend](http://framework.zend.com/manual/1.12/fr/coding-standard.coding-style.html).

* Parenthèses : Une espace doit être insérée après la parenthèse ouvrante, et avant la parenthèse fermante : `if( this );`.

* Concaténation : Dans des chaînes concaténées, toujours cerner les points par des espaces : `echo '<a href="' . $lien . '">';`.

* Ouverture de PHP : Toujours utiliser la version complète pour ouvrir php. Ex: `<?php .. ?>` au lieu de `<? ... ?>`.

* Espaces : Supprimer les espaces inutiles en bout de ligne.

* Virgules : Toujours ajouter une espace après une virgule.

* Commentaires :
 * Un commentaire d'introduction pour chaque fonction est bienvenu.
 * Un commentaire sur une seule ligne commence par `//`.
 * Un commentaire sur plusieurs lignes débute par `/*` et se termine par `*/`.
 * Les commentaires servent également à baliser les fichiers et créer un sommaire, à l'instar des fichiers css.

==

* Annotations : Citer les sources & références, et annoter autant que possible le code.

* Guillemets : Préférer les guillemets simples dès que possible.

* Nommage : Les fonctions doivent être préfixées par un nom de code pour le projet ( par exemple `ffeeeedd__` ) et disposer d'un intitulé clair, en français ( le cas échéant, dans la langue de l'auteur ).

* Ne jamais utiliser de CamelCase (!) Si vous utilisez Zend, cette règle est absurde.
 
==

* Références & inspirations :
 * [Theme Review](http://codex.wordpress.org/Theme_Review)
 * [WordPress PHP Coding Standard](http://make.wordpress.org/core/handbook/coding-standards/php/)
 * [PEAR Coding Standards](http://pear.php.net/manual/en/standards.php)
 * [Convention Zend](http://framework.zend.com/manual/1.12/fr/coding-standard.coding-style.html)


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