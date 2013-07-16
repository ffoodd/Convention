Charte CSS
==========

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