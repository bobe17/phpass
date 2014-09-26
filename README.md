Librairie phpass
================

Librairie phpass de hashage de mots de passe modifiée pour mes besoins.
Voici la liste des modifications introduites par rapport à la librairie d'origine disponible à [cette adresse](http://www.openwall.com/phpass/) :

 - Nommage des méthodes en camelCase
 - Utilisation de `uniqid()` pour l'initialisation de `$random_state` (repris de l'adaptation de phpass dans Wordpress)
 - Les arguments du constructeur sont rendus optionnels (le coût est fixé par défaut à 10)
 - La classe tente par défaut d'utiliser `crypt()` avant de se rabattre sur les hashages portables
 - Ajout de la propriété `$blowfish_mode`. Utilisation du mode '2y' avec fallback vers le mode '2a' si PHP < 5.3.7
 - Utilisation si possible de la fonction `openssl_random_pseudo_bytes()` dans `Password::getRandomBytes()`
 - Ajout d'une fonction de compatibilité `hash_equals()` pour PHP < 5.6.0

Sentez vous libre de réutiliser ce code comme il vous plaira.
