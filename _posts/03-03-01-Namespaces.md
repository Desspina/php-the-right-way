---
isChild: true
---

## Namespace-uri

Cum am menţionat mai sus, comunitatea PHP este formată dintr-o mulţume de dezvoltatori care crează cod. Asta înseamnă că biblioteca PHP poate folosi acelaşi nume al clasei ca şi altă bibliotecă. Când ambele biblioteci sunt folosite în acelaşi namespace, ele se ciocnesc şi cauzează probleme. 

_Namespace-urile_ rezolvă această problemă. Aşa cum este descris în manualul de referinţă al PHP, namespace-urile pot fi comparate cu acele fişiere _namespace_ ale directoarelor sistemului de operare; două fişiere cu acelaşî nume pot co-exista în directoare separate. De asemenea, două clase PHP cu acelaşi nume pot co-exista în namespace-uri PHP separate. Este foarte simplu. 

Este important să-ţi numeşti codul pentru a putea fi folosit de alţi dezvoltatori fără teama de a produce probleme cu alte biblioteci.

Un mod recomandat de a folosi namespace-urile este indicat în [PSR-0][psr0], care îşi propune să ofere un fişier standard, o convenţie între clasă şi namespace ce permit codul plug_and_play. 


* [Citeşte despre Namespaces][namespaces]
* [Citeşte despre PSR-0][psr0]

[namespaces]: http://php.net/manual/en/language.namespaces.php
[psr0]: https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md
