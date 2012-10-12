---
isChild: true
---

## Composer şi Packagist


Composer este un manager al dependenţei pentru PHP **brilliant**. Enumeraţi dependenţele proiectului dvs. într-un fişier `composer.json` şi cu câteva comenzi simple, Composer va descărca automat dependenţele proiectului şi va seta autoîncărcarea. 

Există numeroase biblioteci PHP care sunt compatibile cu Composer, gata sa fie folosite în proiectul dvs. Aceste "pachete" sunt enumerate în [Packagist][1], depozitul oficial pentru Composer-biblioteci compatibile PHP.

### Cum să instalezi Composer

Puteţi instala Composer local (în directorul în care lucreaţi; deşi acesta nu este recomandat) sau global (exp.  /usr/local/bin). Să presupunem că doriţi să instalaţi Composer local. Din rădăcina directorului proiectului: 

    curl -s http://getcomposer.org/installer | php

Acesta va descărca `composer.phar` (o arhivă binară PHP). O puteţi rula cu `php` pentru a manageria dependenţe proiectului.<strong>De reţinut:</strong> Dacă aţi descărcat codul direct într-un interpreter, citiţi mai întâi codul online pentru a avea confirmarea că este sigur.

### Cum să instalaţi Composer (manual)

Instalarea manuală este o tehnică avansată; oricum, există numeroase motive pentru care un dezvoltator ar prefera această metodă vs. folosirea rutinei de instalare interactivă. Instalarea interactivă verifică instalarea PHP pentru a se asigura că:

- că este folosită versiunea potrivită de PHP
- fişierele `.phar` pot fi executate corect
- anumite directoare au permisiunile corecte
- anumite extensii nu sunt încărcate
- anumite setări `php.ini` sunt setate 

Din moment ce un manual de instalare nu face niciuna din aceste verificări, trebuie să vă decideţi dacă acest compromis merită făcut. De aceea, mai jos este prezentat cum să instalaţi Composer manual: 

    curl -s http://getcomposer.org/composer.phar -o $HOME/local/bin/composer
    chmod +x $HOME/local/bin/composer

Calea `$HOME/local/bin` (sau directorul ales la instalare) ar trebui să existe în variabila `$PATH`, astfel încât comanda `composer` să fie disponibilă. 

Când treci prin documentaţia care te îndrumă să rulezi Composer ca `php composer.phar install`, poţi inlocui cu:

    composer install

### Cum poţi defini şi instala dependenţe

În primul rând, crează un fişier `composer.json` în acelaşi director ca şi `composer.phar`. Iată un exemplu ce listează [Twig][2] ca o dependenţă a proiectului. 

	{
	    "require": {
	        "twig/twig": "1.8.*"
	    }
	}

Pasul următor este să rulaţi această comandă din rădăcina proiectului.

    php composer.phar install

Aceasta va descărca şi instala dependenţele proiectului în directorul `vendors/`. Apoi, adăugaţi această linie primului fişier PHP al aplicaţiei; asta va transmite PHP să folosească autoloader-ul Composer pentru dependenţele proiectului. 

{% highlight php %}
<?php
require 'vendor/autoload.php';
{% endhighlight %}

Acum puteţi folosi dependenţele proiectului, şi ele vor fi încarcate automat, când este nevoie de ele. 

* [Mai multe despre Composer][3]

[1]: http://packagist.org/
[2]: http://twig.sensiolabs.org
[3]: http://getcomposer.org/doc/00-intro.md
