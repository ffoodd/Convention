Charte Javascript
=================

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