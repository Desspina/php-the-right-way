---
isChild: true
---

## Hash-uirea parolelor cu Bcrypt

Aplicaţiile PHP construite se bazează pe autentificarea cu user. Usernameul şi parola sunt stocate într-o bază de date şi mai apoi foloste pentru autentificarea utilizatorilor la logare. 

Este important să _hash-uiţi_ în mod corespunzător parolele stocate în baza de date. Dacă parolele nu sunt hash-uite, şi baza de date este atacată sau accesată de un terţ neautorizat, toate conturilor userilor sunt compromise. 

**Hash-uiţi parolele cu Bcrypt** Este foarte simplu, şi (cu orice intenţie sau scop) Brypt face imposibil cuiva să inverseze textul simplu al unei parole, iar baza de date nu este compromisă. 

Există câteva biblioteci Bcrypt pentru PHP pe care ai putea să le foloseşti. 

* [Citiţi "How to Safely Store a Password" de Coda Hale][3]
* [Folosiţi Bcrypt cu PHPass][4]

[3]: http://codahale.com/how-to-safely-store-a-password/
[4]: http://www.openwall.com/phpass/
