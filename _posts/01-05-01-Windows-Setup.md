---
isChild: true
---

## Configurarea pentru Windows

PHP de poate configura pe Windows în numeroase moduri. Puteţi [descărcaţi fişierele binare](php-downloads) care până de curând era disponibil în format '.msi'. Pachetul de instalare nu s-a mai acualizat oprindu-se la versiunea PHP 5.3.0.

Pentru a înnvăţa PHP şi pentru a-l rula local puteţî folosi web serverul Built-in ce vine cu versiunea PHP 5.4 nefiind nevoie să îl mai configuraţi. Dar dacă doriţi sa dispuneţi de o siluţie "all-in-one" ce oferă un web server şi o bază de date MySQL completă, atunci instrumente precum [Web Platform Installer][wpi], 
[Zend Server CE][zsce], [XAMPP][xampp] şi [WAMP][wamp] vă vor ajuta să configuraţi mediul de dezvoltare de Windows şi să ruleze rapid. Ţineţi seama că aceste instrumente vor fi un pic diferite decât cele produse, aşa că fiţi atenţi la diferenţele de mediu dacă lucraţi pe Windows şi implementaţi pe Linux.

Dacă este nevoie să rulaţi un sistem de producţie pe Windows, atunci IIS7 vă va oferi cea mai bună şi stabilă performanţă. Puteţi folosi [phpmanager][phpmanager] (un plugin GUI pentru IIS7) pentru a configura şi gestiona PHP. IIS7 vine configurat cu FastCGI pentru a fi folosit, trebuie doar configurat PHP ca şi manipulator. Pentru informaţii suplimentare si suport există [o secţune dedicată iis.net][php-iis] pentru PHP.

În general, rulând aplicaţia în diferite medii de dezvoltare şi producţie, poate duce la apariţia unor erori în timpul folosirii. Dacă lucraţi în Windows şi implementaţi pe Linux (sau orice alt sistem în afară de Windows) ar trebui să luaţi în considerare folosirea unei maşini virtuale. Poate suna un pic complicat, dar folosind [Vagrant][vagrant] puteţi seta simple recipiente, iar apoi folosind [Puppet][puppet] sau [Chef][chef] puteţi să le împărtăşiţi colegii voştri pentru a vă asigura că lucraţi cu toţii la aceelaşi lucru. Mai multe despre asta în curând.

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
