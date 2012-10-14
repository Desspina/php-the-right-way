---
isChild: true
---

## Excepţii

Excepţiile alcătuiesc o parte standard a celor mai multe limbaje de programare, dar ele sunt adesea trecute cu vederea de către programatorii PHP.
Limbaje precum Ruby sunt excepţii de luat în seamnă, aşa că ori de câte ori ceva nu merge bine cum ar fi o eşuarea unei cereri HTTP sau o interogare DB nu merge bine sau o imagine nu poate fi găsită, Ruby (sau orice altceva este folosit) vor indica o excepţie pe ecran pentru ca tu să-ţi dai seama că undeva există o greşeală. 

Inclusiv PHP este foar permisiv cu asta, şi te anunţă că `file_get_contents()` vei obţine un `FALSE` şi o atenţionare.

Mai multe cadre PHP mai vechi precum CodeIgniter vor indica un fals, un mesaj de logare în istoricul logărilor şi poate vor permite folosirea unei metode ca `$this->upload->get_error()` pentru a detecta ce nu a mers bine. Problema e că trebuie să căutaţi greşeala şi că verificaţi documentele pentru a vedea care este metoda erorii pentru acestă clasă şi pentru a o evidenţia.

O altă problemă este atunci când clasele dau automat o eroare şi ies din program. Când se întâmplă asta, opriţi alt dezvoltator să se ocupe de eroare . Excepţiile ar trebui să existe pentru a face  un dezvoltator conştient de existenţa unei erori şi pentru a putea să se ocupe de ea. De exemplu: 


{% highlight php %}
<?php
$email = new Fuel\Email;
$email->subject('My Subject');
$email->body('How the heck are you?');
$email->to('guy@example.com', 'Some Guy');

try
{
    $email->send();
}
catch(Fuel\Email\ValidationFailedException $e)
{
    // The validation failed
}
catch(Fuel\Email\SendingFailedException $e)
{
    // The driver could not send the email
}
{% endhighlight %}

### SPL Exceptions

O excepție în mod implicit nu are nici un sens și pentru a-i da sens trebui setat numele acesteia:

{% highlight php %}
<?php
class ValidationException extends Exception {}
{% endhighlight %}

Acest lucru înseamnă că puteți adăuga mai multe capturi și să gestionaţi în mod diferit excepţiile. Asta poate duce la crearea unei <em>mulţimi</em> de Excepţii, unele dintre ele putând fi evitate folosind SPL Exceptions furnizate în [SPL extension][splext].

Dacă, de exemplu, folosiţi `__call()` Magic Method şi o metodă nevalidă este obligatorie, atunci în loc să adăugaţi o excepţie standard care este vagă, sau sa creaţi o excepţie personalizată, puteţi doar `throw new BadFunctionCallException;`.



* [Citiţi despre Excepţii][exceptions]
* [Citiţi despre SPL Exceptions][splexe]
* [Nesting Exceptions In PHP][nesting-exceptions-in-php]
* [Exception Best Practices in PHP 5.3][exception-best-practices53]

[exceptions]: http://php.net/manual/en/language.exceptions.php
[splexe]: http://php.net/manual/en/spl.exceptions.php
[splext]: /#standard_php_library
[exception-best-practices53]: http://ralphschindler.com/2010/09/15/exception-best-practices-in-php-5-3
[nesting-exceptions-in-php]: http://www.brandonsavage.net/exceptional-php-nesting-exceptions-in-php/
