---
isChild: true
---

## Filtrarea datelor

Niciodată, dar niciodată să nu aveţi încredere într-o intrare externă introdusă în codul PHP. Întotdeauna curăţaţi si validaţi input-urile externe înainte de a le folosi în cod. Funcţiile `filter_var` and `filter_input` pot curăţa şi valida textul (exp. Adresele de email) 

Input extern poate fi orice: formulare `$_GET` şi `$_POST`, unele valori în `$_SERVER` şi cererile HTTP via `fopen('php://input', 'r')`. Reţineri, intrările străine nu sunt limitate de datele prezentate în formularul de utilizator. Fişierele încărcate şi descărcate, valorile sesiunii, datele cookie şi datele din serviciile web ale terţilor sunt intrări strâine de asemene. 

În timp ce datele externe pot fi stocate, combinate şi accesate ulterior ele încă reperezintă un input exterior. Cu fiecare procesare, ieşire, îmbinare sau includere a datelor în cod, se pune întrebarea dacă datele sunt filtrate corespunzător şi pot fi de încredere.

Datele pot fi _filtrate_ în mod diferit bazându-se pe propriul scop. De exemplu, când un input străin este plasat într-o pagină de ieşire HTML, poat eexecuta HTML şi JavaScript pe site! Aceasta este cunoscută sub numele de Cross-Site Scripting (XSS) şi poate reprezenta un atac periculos. O modalitate de a evita XSS este de a curăţa toate tag-urile HTML din intrare prin îndepărtarea tag-urilor.

Un alt exemplu este executarea opţiunii în linia de comandă. Asta poate fi foarte periculos (şi de obicei nu este o idee prea bună), dar puteţi folosi funcţia built-in `escapeshellarg` pentru a curăţa argumentele comenzii executate. 

Un ultim exemplu este acceptarea input-ului străin pentru a determina un fişier să se încarce din sistemul de fişiere. Acesta poate fi executat prin schimbarea numelui fişierului într-un fişier cale. Trebuie să înlăturaţi "/", "../", [null bytes][6] sau alte caratere din fişîerul cale pentru a putea fi încărcat non-public sau ca fişier sensibil. 


* [Citeşte despre filtrarea datelor][1]
* [Citeşte despre `filter_var`][4]
* [Citeşte despre `filter_input`][5]
* [Citeşte despre manevrarea bytes-lor nuli][6]

### Igienizarea

Igienizarea elimină (sau îndepărtează) caractere ilegale sau nesigure de la un input străin.

De exemplu, trebuie să curăţaţi inputurile străine înainte de a include input-ul in HTML sau să-l inseraţi în interogări SQL brute. Când utilizați parametrii legați cu [PDO](#databases), acesta va curăţă input-ul pentru dvs.

Uneori este necesar să se permită intrarea unor tag-uri HTML sigure când se introduc in pagini HTML. Aceast lucru este destul de greu de făcut şi mulţi se feresc prin folosirea altor formatări mult mai restrictive precum Markdown asau BBCode, dar şi biblioteci whitelisting precum [HTML Purifier][html-purifier].

[Vezi filtrele de igienizare][2]


### Validarea 

Validarea asigură că input-ul străin este exact aşa cum te aştepţi să fie. De exemplu, ai putea dori să validezi o adresă de email, un număr de telefon sau o vârstă în timpul procesului de înregistrare.


[Vezi filtrele de validare][3]

[1]: http://www.php.net/manual/en/book.filter.php
[2]: http://www.php.net/manual/en/filter.filters.sanitize.php
[3]: http://www.php.net/manual/en/filter.filters.validate.php
[4]: http://php.net/manual/en/function.filter-var.php
[5]: http://www.php.net/manual/en/function.filter-input.php
[6]: http://php.net/manual/en/security.filesystem.nullbytes.php
[html-purifier]: http://htmlpurifier.org/
