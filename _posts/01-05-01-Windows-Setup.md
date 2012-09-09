---
isChild: true
---

## Configurarea pentru Windows

PHP se poate configura pe Windows în numeroase moduri. Puteţi [descărca fişierele binare](php-downloads) care până de curând erau disponibile în format '.msi'. Pachetul de instalare nu s-a mai actualizat oprindu-se la versiunea PHP 5.3.0.

Pentru a învăţa PHP şi pentru a-l rula local puteţi folosi web serverul built-in ce vine cu versiunea PHP 5.4 nefiind nevoie să îl mai configuraţi. Dar dacă doriţi să dispuneţi de o soluţie "all-in-one" ce oferă un web server şi o bază de date MySQL completă, atunci instrumente precum [Web Platform Installer][wpi], [Zend Server CE][zsce], [XAMPP][xampp] şi [WAMP][wamp] vă vor ajuta să configuraţi mediul de dezvoltare pe Windows şi să ruleze rapid. Acestea fiind spuse, ţineţi seama că aceste instrumente vor fi un pic diferite faţă de serverul de producţie, aşa că fiţi atenţi la diferenţe	 dacă lucraţi pe Windows şi implementaţi pe Linux.

Dacă este nevoie să rulaţi un sistem de producţie pe Windows, atunci IIS7 vă va oferi cea mai bună şi stabilă performanţă. Puteţi folosi [phpmanager][phpmanager] (un plugin GUI pentru IIS7) pentru a configura şi gestiona PHP. IIS7 vine configurat cu FastCGI instalat şi gata de a fi folosit; trebuie doar configurat PHP ca şi *handler*. Pentru informaţii suplimentare şi suport există [o secţiune dedicată iis.net][php-iis] pentru PHP.

În general, rularea aplicaţiei în diferite medii de dezvoltare şi producţie poate duce la apariţia unor erori în timpul folosirii. Dacă lucraţi în Windows şi implementaţi pe Linux (sau orice alt sistem în afară de Windows) ar trebui să luaţi în considerare folosirea unei maşini virtuale. Poate suna un pic complicat, dar folosind [Vagrant][vagrant] puteţi seta simple recipiente, iar apoi folosind [Puppet][puppet] sau [Chef][chef] puteţi să le distribuiţi colegilor pentru a vă asigura că lucraţi cu toţii în aceelaşi mediu. Mai multe despre asta în curând.

[php-downloads]: http://windows.php.net
[phpmanager]: http://phpmanager.codeplex.com/
[wpi]: http://www.microsoft.com/web/downloads/platform.aspx
[zsce]: http://www.zend.com/en/products/server-ce/
[xampp]: http://www.apachefriends.org/en/xampp.html
[wamp]: http://www.wampserver.com/
[php-iis]: http://php.iis.net/
[vagrant]: http://vagrantup.com/
[puppet]: http://www.puppetlabs.com/
[chef]: http://www.opscode.com/
