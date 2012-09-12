---
isChild: true
---

## Paradigme ale programării

PHP este un limbaj flexibil, dinamic ce suportă o varietate a tehnicilor de programare. A evoluat foarte mult în în timp, în mod special adugând un foarte bun model orientat spre PHP 5.0 (2004), funcţii anonime şi secţiuni în PHP 5.3 (2009) şi caracetristici în PHP 5.4 (2012). 


### Programarea orientată pe obiect

PHP are un set complet de caracteristici în ce priveşte programarea orientată pe obiect, inclusiv sprijin pentru clase, clase abstracte, interfeţe, constructori, clonare, aşteptări şi altele. 

* [Citiţi despre programarea orientată pe obiecte][oop]
* [Citiţi despre caracteristici][traits]

### Programarea funcţională

PHP suportă funcţii de prima clasă, asta însemnând că o funcţie poate fi atinsă printr-o variabilă. Atât userul definit cât şi funcţiile built-in pot fi exprimate de o variabila şi invocate dinamic. Funcţiile pot definite ca argumente ale altor funcţii (caracteristici denumite funcţii de nivel înalt) şi ele pot reveni la alte funcţii. 

Recursivitatea, o trăsătură ce permite unei funcţii să se numească într-un anume fel, este sprijinită de limbaj, dar cel mai mult de focusată pe codul PHP. 

Noile funcţii anonime (cu sprijin pentru încheiere) există de la PHP 5.3(2009)

PHP 5.4 a adugat posibilitatea de legare de domeniul de aplicare al unui obiect şi, de asemenea, suport îmbunătăţit pentru obiectele apelabile astfel încât ele pot fi folosite şi ca funcţii anonime în aproape orice situaţie.

* Citeşte mai departe [Programarea Funcţională în PHP](/pages/Functional-Programming.html)
* [Citeşte despre Funcţii Anonime][anonymous-functions]
* [Citeşte despre Closure class][closure-class]
* [Mai multe detalii în Closures RFC][closures-rfc]
* [Citeşte despre Callables][callables] 
* [Citeşte despre dinamica invocării funcţiilor cu `call_user_func_array`][call-user-func-array]

### Meta Programare

PHP suportă mai multe forme de meta programare prin mijloace precum Reflection API şi Metode Magice. Există multe metode magice disponibile precum `__get()`, `__set()`, `__clone()`, `__toString()`, `__invoke()` etc. care permit programatorilor să se lege de comportamentul clasei. Programatorii Ruby spun adesea că PHP lipsit de `method_missing`, dar este disponibil ca `__call()` şi `__callStatic()`.


* [Citeşte despre Metodele Magice][magic-methods]
* [Citeşte despre Reflecţie][reflection]

[namespaces]: http://php.net/manual/en/language.namespaces.php
[overloading]: http://php.net/manual/en/language.oop5.overloading.php
[oop]: http://www.php.net/manual/en/language.oop5.php
[anonymous-functions]: http://www.php.net/manual/en/functions.anonymous.php
[closure-class]: http://php.net/manual/en/class.closure.php
[callables]: http://php.net/manual/en/language.types.callable.php
[magic-methods]: http://php.net/manual/en/language.oop5.magic.php
[reflection]: http://www.php.net/manual/en/intro.reflection.php
[traits]: http://www.php.net/traits
[call-user-func-array]: http://php.net/manual/en/function.call-user-func-array.php
[closures-rfc]: https://wiki.php.net/rfc/closures
