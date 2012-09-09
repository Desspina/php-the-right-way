---
isChild: true
---

## Configurarea pentru Mac

Sistemul OSX vine prefigurat cu PHP care in mod normal nu este actualizat la ultima versiune. Lion vine cu PHP 5.3.6 şi Mountain Lion has 5.3.10.

Pentru actualizarea versiunii PHP din sistemul OSX se poate instala printr-o serie de [managere de pachete][mac-package-managers], fiind recomandat [php-osx by Liip][php-osx-downloads].

Altă opţiune disponibilă ar fi să [îl compilaţi][mac-compile], caz în care trebuie să fiţi siguri că aveţi instalat Xcode sau un înlocuitor Apple ["Command Line Tools for Xcode"][apple-developer] ce se poate descărcă direct din Mac Developer Center. 

Pentru un pachet "all-in-one" complet care include PHP, Web server Apache şi baza de date MySQL, toate cu un bun control GUI, încercaţi [MAMP][mamp-downloads].


[mac-package-managers]: http://www.php.net/manual/en/install.macosx.packages.php
[mac-compile]: http://www.php.net/manual/en/install.macosx.compile.php
[xcode-gcc-substitution]: https://github.com/kennethreitz/osx-gcc-installer
[apple-developer]: https://developer.apple.com/downloads
[mamp-downloads]: http://www.mamp.info/en/downloads/index.html
[php-osx-downloads]: http://php-osx.liip.ch/
