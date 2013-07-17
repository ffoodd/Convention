Charte PHP
==========

*Attention* : ces recommandations sont conséquentes d'une utilisation récurrente de WordPress, et ne conviennent pas à tous les cas d'utilisation.

* Conventions particulières :
 * Si vous codez dans Magento ou Zend, vous devriez jeter un œil [au standard de codage](http://framework.zend.com/wiki/display/ZFDEV2/Coding+Standards).
 * Prestashop dispose également d'une [norme de développement](http://doc.prestashop.com/pages/viewpage.action?pageId=15171593).

Si vous travaillez dans un thème WordPress, ces règles pourront vous convenir :

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
 * Un commentaire d'introduction pour chaque fonction est bienvenu;
 * Un commentaire sur une seule ligne commence par `//`;
 * Un commentaire sur plusieurs lignes débute par `/*` et se termine par `*/`;
 * Les commentaires servent également à baliser les fichiers et créer un sommaire, à l'instar des fichiers css.

==

* Annotations : Citer les sources & références, et annoter autant que possible le code.

* Guillemets : Préférer les guillemets simples dès que possible.

* Nommage : Les fonctions doivent être préfixées par un nom de code pour le projet ( par exemple `ffeeeedd__` ) et disposer d'un intitulé clair, en français ( le cas échéant, dans la langue de l'auteur ).

* Ne jamais utiliser de CamelCase.
 
==

* Références & inspirations :
 * [Theme Review](http://codex.wordpress.org/Theme_Review)
 * [WordPress PHP Coding Standard](http://make.wordpress.org/core/handbook/coding-standards/php/)
 * [PEAR Coding Standards](http://pear.php.net/manual/en/standards.php)
 * [Convention Zend](http://framework.zend.com/manual/1.12/fr/coding-standard.coding-style.html)