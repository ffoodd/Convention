Charte HTML
===========

* Doctype : Utiliser le doctype HTML5 `<!DOCTYPE html>`.

* Encodage : Spécifier l'encodage via la balise meta dédiée `<meta charset="utf-8">`.

* Langue : La langue doit être spécifiée sur la balise `<html>` ( ex: `lang="fr-FR"` ).

* Organisation du `<head>` :
 * La `<meta charset="utf-8">` doit être le premier enfant du `<head>`;
 * La balise `<title>` doit venir en deuxième position;
 * Ajouter la balise `<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">` en vue d'améliorer le rendu sur IE;
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
 * Ne pas fournir l'attribut `type` pour les styles et scripts;
 * Utiliser des guillemets doubles pour cerner les valeurs des attributs;
 * Spécifier les *rôles ARIA* dès que possible ( cf: [WAI ARIA](http://www.w3.org/TR/wai-aria/ "La recommandation du W3C") );
 * Ajouter les *microdonnées* lorsque c'est utile ( cf: [schema.org](http://schema.org/docs/full.html "Liste des microdonnées") );
 * L'attribut `style` ne doit pas être utilisé;
 * Dans le cas de nombreux attributs, on envisagera de revenir à la ligne entre chaque attribut afin d'améliorer la lisibilité.

==

* Ordre des attributs :
 1. `class` : valoriser l'utilisation des classes par rapport aux IDs pour les CSS;
 2. `id`;
 3. `role`;
 4. `data-*` : pour servir de crochet au javascript;
 5. `aria-*` : pour l'accessibilité et la sémantique;
 6. autre(s) : href, title, alt, microdonnées, etc...

==

* Métadonnées :
 * Ajouter le profil [DublinCore](http://dublincore.org/documents/2008/08/04/dc-html/ "Profil DublinCore") sur `<html>`;
 * Les métas DublinCore, OpenGraph et TwitterCard doivent être renseignées.

==

* Favicon :
 * Deux fichiers doivent être présents à la racine : un `favicon.ico` et un un `apple-touch-icon-precomposed.png`;
 * Ils ne doivent pas être déclarés dans le `<head>` (cf [Everything you always wanted to know about touch icons](http://mathiasbynens.be/notes/touch-icons) ).

==

* Formulaires :
 * Chaque champ est associé à un label, avec les attributs `for` et `aria-labelled-by`;
 * Le format attendu est indiqué sous forme de légende à côté du champ;
 * Les placeholders ne doivent pas être la seule indication du format attendu;
 * L'attribut `type` doit être utilisé efficacement;
 * Les champs obligatoires sont indiqués par une indication textuelle à côté du label, mais aussi via les attributs `required` et `aria-required`;
 * Les erreurs sont retournées champ par champ, avec un intitulé explicitant l'erreur;
 * Le succès d'une soumission est également explicité textuellement;
 * Les contraintes de chaque champ sont indiquées à côté de celui-ci ( masque de saisie, sensibilité à la casse, nombre de caractères... ).

==

* Tableaux :
 * Chaque tableau de données doit disposer d'un titre;
 * Les en-têtes sont correctement balisées ( `<th>` );
 * Les cellules doivent être reliées à leur en-tête ( `headers=""` );

==

* Liens :
 * Chaque lien est doté d'un intitulé utile, décrivant sa fonction et/ou sa cible;
 * Éviter les intitulés passe-partout (en savoir plus, cliquez ici);
 * Le soulignement est réservé aux liens, afin de les distinguer visuellement;
 * Les liens visités ont un style particulier, différenciant;
 * Les liens externes sont distingués visuellement;
 * Éviter l'emploi de `<a href="#">` comme bouton d'action; préferer `<button type="button">`.

==

* Annotations : Citer les sources & références, et annoter autant que possible le code.

* La première occurrence d'un `<abbr>` doit permettre d'accéder à sa signification.

* La capitalisation à des fins décoratives doit être faite via CSS.

* Les mots ne comportent ni espaces ni balisage interne (`<span>`L`</span>`ettrine).

* Compatibilité :
 * S'appuyer sur des commentaires conditionnels pour cibler les versions d'IE;
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
 * [ConvertIco](http://www.convertico.com/ 'Convertissez vos png en ico')
 * [PNG Optimizer](http://psydk.org/PngOptimizer.php)