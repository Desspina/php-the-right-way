---
isChild: true
---

## Data şi ora 

PHP are o clasa numită DateTime care vă ajută să citiţi, să scrieţi, să comparaţi şi să calculaţi data şi ora. Există multe funcţii ce fac referire la dată şi oră în PHP pe lângă DateTime, dar care oferă de obicei interfeţe orientate pe obiect. Pot suporta fusuri orare, dar se află în afara aceste scurte introduceri. 

Pentru a începe să lucraţi cu DateTime, transformaţi şirul de date şi timp brute în obiecte prim metoda createFromFormat()` sau creaţi `new \DateTime` pentru a obţine data şi ora actuală. Folosiţi metoda `format()` pentru a transforma DateTime într-o serie de ieşire. 

{% highlight php %}
<?php
$raw = '22. 11. 1968';
$start = \DateTime::createFromFormat('d. m. Y', $raw);

echo 'Start date: ' . $start->format('m/d/Y') . "\n";
{% endhighlight %}

Calcularea cu DateTime este posibilă cu DateInterval class. DateTime are metode precum `add()` and `sub()` care preiau DateInterval ca un argument. Nu scrieţi cod care aşteaptă acelaşi număr de secunde în fiecare zi, ambele daylight saving şi timezone vor rupe această ipoteză. Folosiţi în schimb intervale de zile. Pentru a calcula diferenţa de dată folosiţi metoda `diff()`. Veţi obţine un nou DateInterval, care este foarte uşor de afişat. 

{% highlight php %}
<?php
// creaţi o copie a lui $start şi mai adăugaţi încă o lună şi 6 zile 
$end = clone $start;
$end->add(new \DateInterval('P1M6D'));

$diff = $end->diff($start);
echo 'Difference: ' . $diff->format('%m month, %d days (total: %a days)') . "\n";
// Diferenţa: 1 month, 6 days (total: 37 days)
{% endhighlight %}

La obiectele DateTime puteţi folosi comparatia standard:
{% highlight php %}
<?php
if ($start < $end) {
    echo "Start is before end!\n";
}
{% endhighlight %}


Ultimul exemplu arată DatePeriod class. Este folosit pentru a repeta evenimente periodice. Pot fi două obiecte DateTime, start şi end, şi de interval care vor repeta toate evenimentele din acea perioadă. 

{% highlight php %}
<?php
// output all thursdays between $start and $end
$periodInterval = \DateInterval::createFromDateString('first thursday');
$periodIterator = new \DatePeriod($start, $periodInterval, $end, \DatePeriod::EXCLUDE_START_DATE);
foreach ($periodIterator as $date) {
    // output each date in the period
    echo $date->format('m/d/Y') . ' ';
}
{% endhighlight %}

* [Citiţi despre DateTime][datetime]
* [Citiţi despre formatarea datei][dateformat] (accepted date format string options)

[datetime]: http://www.php.net/manual/book.datetime.php
[dateformat]: http://www.php.net/manual/function.date.php
