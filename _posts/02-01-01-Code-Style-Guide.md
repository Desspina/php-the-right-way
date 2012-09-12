# Ghid al Stilului Codului 

Comunitatea PHP este mare şi diversă, compusă din nenumărate biblioteci, cadre şi alte componente. Este o obişnuinţă pentru programatorii PHP să aleagă căteva din acestea şi să le combine într-un singur proiect. Este important să adere codul PHP (cât mai mult posibil) la un stil al codului comun pentru a uşura munca programatorilor în combinarea şi potrivirea diferitelor resurse pentru proiectele lor. 

[Grupul Framework Interop][fig] (cunoscut şi ca 'PHP Standards Group') a propus şi a aporbat o serie de recomandări ale stilului, cunoscute şi ca [PSR-0][psr0], [PSR-1][psr1] şi [PSR-2][psr2]. Nu vă lăsaţi păcăliţi de numele amuzante, aceste recomandări sunt doar un set de reguli pe care unele proiecte precum Drupal, Zend, CakePHP, phpBB, AWS SDK, FuelPHP, Lithium, etc încep să le adopte. Le puteţi folosi pentru proiectele proprii sau continuaţi să folosiţi propriile stiluri.

În mod ideal, ar trebui să scrieţi un cod PHP care să adere la unul sau mai multe dintre aceste standarde astfel încât alţi programatori să-l poată citi cu uşurinţă şi să poată lucra cu el. Acestea toate se adaugă recomandării anterioare, deci folosirea PSR-1 cere PSR-0, dar nu este necedară PSR-2

* [Citiţi despre PSR-0][psr0]
* [Citiţi despre PSR-1][psr1]
* [Citiţi despre PSR-2][psr2]

Puteţi folosi [phpcs-psr][phpcs-psr] şi [PHP_CodeSniffer][phpcs] pentru a verifica dacă sunt respectate aceste recomandări.

Folosiţi Fabien Potencier's [PHP Coding Standards Fixer][phpcsfixer] pentru a modifica în mod automat codul syntax pentru a se conforma standardelor şi pentru a vă scuti de rezolvarea manuală a fiecărei probleme.

[fig]: http://www.php-fig.org/
[psr0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md
[psr1]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md
[psr2]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md
[phpcs]: http://pear.php.net/package/PHP_CodeSniffer/
[phpcs-psr]: https://github.com/klaussilveira/phpcs-psr
[phpcsfixer]: http://cs.sensiolabs.org/
