---
isChild: true
---

## Linii de comandă (Command Line Interface)

PHP a fost creat în primul rând pentru a scrie aplicaţii web, dar este, de asemenea, folositor pentru a scrie şi linii de comandă (CLI). Liniile de comandă PHP pot ajuta la automatizarea sarcinilor precum testare, implementarea şi aplicare. 

Programele CLI PHP sunt puternice deoarece îţi poţi folosi codul aplicaţiei fără a fi nevoie să creezi şi să securizezi un GUI web pentru el. Doar asiguraţi-vă că nu faceţi public scriptul CLI PHP!

încercaţi să rulaţi PHP din linia de comandă:


{% highlight bash %}
> php -i
{% endhighlight %}

Opţiunea `-i` va imprima configuraţia PHP exact ca funcţia [`phpinfo`][phpinfo].

Opţiunea `-a` oferă un shell interactiv, similar cu IRB al ruby sau shell-ul interactiv al python. Există un număr de alte [command line options][cli-options] folositoare. 

Să scriem un program simplu "Hello, $name" CLI. Pentru a încerca, creaţi un fişier numit `hello.php`, ca şi cel ce urmează.


{% highlight php %}
<?php
if ($argc != 2) {
    echo "Usage: php hello.php [name].\n";
    exit(1);
}
$name = $argv[1];
echo "Hello, $name\n";
{% endhighlight %}

PHP stabilește două variabile speciale bazate pe argumente, iar script-ul se execută cu. [`$argc`][argc] este o variabilă integer ce conţine argumentul *count* şi [`$argv`][argv] este o variabilă array ce conţine *valoarea* fiecărui argument. Primul argument este întotdeauna numele fişierului script PHP, în acest caz `hello.php`.

Expresia `exit()` este folosită cu un număr non zero pentru a permite shell să detecteze eşuarea comenzii. Codurile utilizate în mod obişnuit pot fi găsite [aici][exit-codes]

Pentru a rula scriptul nostru de mai sus, din linia de comandă:


{% highlight bash %}
> php hello.php
Usage: php hello.php [name]
> php hello.php world
Hello, world
{% endhighlight %}


 * [Învăţaţi despre rularea PHP din linia de comandă][php-cli]
 * [Învăţaţi despre setarile Windows pentru a rula PHP din linia de comandă][php-cli-windows]

[phpinfo]: http://php.net/manual/en/function.phpinfo.php
[cli-options]: http://www.php.net/manual/en/features.commandline.options.php
[argc]: http://php.net/manual/en/reserved.variables.argc.php
[argv]: http://php.net/manual/en/reserved.variables.argv.php
[php-cli]: http://php.net/manual/en/features.commandline.php
[php-cli-windows]: http://www.php.net/manual/en/install.windows.commandline.php
[exit-codes]: http://www.gsp.com/cgi-bin/man.cgi?section=3&topic=sysexits