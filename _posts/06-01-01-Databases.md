---
title: Databases
---

# Bazele de date

Adeseori, codul tău PHP va folosi o bază de date pentru a păstra informaţia. Ai câteva opţiuni pentru a te conecta şi a interacţiona cu baza ta de date. Opţiune recomandată _pănă la PHP 5.1.0_ era să foloseşti divere autohtone precum [mysql][mysql], [mysqli][mysqli], [pgsql][pgsql], etc.

Driverele native sunt grozave dacă foloseşti doar o bază de date în aplicaţia ta, dar dacă, de exemplu, foloseşti MySQL şi un pic de MSSQL, vei fi nevoie să te conectezi la o bază de date Oracle şi apoi nu vei fi capabil să foloseşti aceleaşi drivere. Va trebui să înveţi un nou API pentru fiecare bază de date şi asta poate fi caraghios. 

Ca o notă în plus pentru driverele native, extensia mysql pentru PHP nu mei este disponibilă în programare şi un status oficial de la PHP 5.4.0 este "Amortizare pe termen lung". Asta înseamnă că va fi înlăturată în următoarele versiuni, aşa că la PHP 5.6 (sau ce ar urma după 5.5) s-ar putea să nu mai fie. Dacă foloseşti `mysql_connect()` şi `mysql_query()` în aplicaţie atunci te cei confrunta cu o rescriere la un moment dat, aşa că cea mai bună opţiune este să înlocuieşti în aplicaţie folosirea mysql cu mysqli sau PDO pentru a nu fi obligat să vă grăbiţi apoi. _Dacă porneşti de la zero atunci nu folosi extensii mysql: foloseşte [extensii MySQLi ][mysqli], sau PDO._


* [PHP: Alegerea unul API pentru MySQL](http://php.net/manual/en/mysqlinfo.api.choosing.php)

## PDO

PDO este o bază de date conectată la biblioteci abstracte construită în PHP încă de la versiunea 5.1.0 şi care oferă o interfaţă obişnuită ce comunică cu diferite baze de date. PDO nu va traduce interogările SQL şi nu va itima caracteristici ce lipsesc; pur şi simplu te conectează cu mai multe baze de date cu acelaşi API. 

Şi mai important, `PDO` îţi permite să intri în siguranţă în interogările SQL fără să te temi de atacurile asupra bazei de date SQL. 
Aceasta este posibil pe baza declaraţiilor şi parametrilor PDO

Să presupunem că un script PHP primeşte un ID numeri ca un parametru de interogare. Acest ID ar trebui folosit pentru a înregistra un utilizator într-o bază de date. Acesta e un mod `greşit` de a proceda: 

{% highlight php %}
<?php
$pdo = new PDO('sqlite:users.db');
$pdo->query("SELECT name FROM users WHERE id = " . $_GET['id']); // <-- NO!
{% endhighlight %}

Iată un cod greşit. Introduci un paramentru de interogare brut într-o cerere SQL. Vei fi piratat într-o clipită. Imaginează-ţi că un hacker trece cu un `id` inventiv prin apelarea unul URL precum `http://domain.com/?id=1%3BDELETE+FROM+users`. Aceasta va seta variabila `$_GET['id']`în id=1;DELETE FROM users` care va şterge toţi userii! În schimb, va trebui să ştergi ID-ul folosing parametri referitori la PDO.

{% highlight php %}
<?php
$pdo = new PDO('sqlite:users.db');
$stmt = $pdo->prepare('SELECT name FROM users WHERE id = :id');
$stmt->bindParam(':id', $_GET['id'], PDO::PARAM_INT); //<-- Automatically sanitized by PDO
$stmt->execute();
{% endhighlight %}

Acesta este codul corect. Foloseşte parametri legaţi de PDO. Asta scapă ID-ul de intrarea externă înainte de a fi introdus în baza de date şi previne posibilele atacuri SQL.


* [Mai multe despre PDO][1]

Ar trebui de asemenea să fiţi atenţi la conexiunile bazei de date care folosesc resurse şi nu s0a întâmplat să se epuizeze resursele dacă conexiunile nu au fost închise implicit, aceasta fiind mai întâlnită în alte limbaje. Folosind PDO, conexiunile de pot inchide implicit prin eliminarea obiectului prin care se făcea trimiterea, de exemplu, setându-l ca fiind NULL. Dacă nu faci asta explicit, PHP va închide automat conexiunea când script-ul se termină
cu excepția cazului în care, desigur, utilizați conexiuni persistente.


* [Mai multe despre conexiunile PDO][5]

## Nivele de abstractizare

Multe cadre oferă propriile nivele de abstractizare care ar putea sau nu să fie deasupra PDO. Acestea vor imita adesea caracteristici ale unei baze de date ce lipsesc în alta prin împachetarea interogărilor în metode PHP. 
Asta vă va da un pic de bătaie de cap dar dacă construiţi o aplicaţie portabilă ce necesită lucrul cu MySQL, PostgreSQL şi SQLite, atunci aceasta bătaie de cap va merita de dragul unul cod curat. 
Unele nivele de abstractizare au fost construite rin folosire namespace-ului standard PSR-0 şi pentru a putea fi intalate în orice aplicaţie: 

* [Doctrine2 DBAL][2]
* [ZF2 Db][4]
* [ZF1 Db][3]

[1]: http://www.php.net/manual/en/book.pdo.php
[2]: http://www.doctrine-project.org/projects/dbal.html
[3]: http://framework.zend.com/manual/en/zend.db.html
[4]: http://packages.zendframework.com/docs/latest/manual/en/index.html#zend-db
[5]: http://php.net/manual/en/pdo.connections.php

[mysql]: http://php.net/mysql
[mysqli]: http://php.net/mysqli
[pgsql]: http://php.net/pgsql
