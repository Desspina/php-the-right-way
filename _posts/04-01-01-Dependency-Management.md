# Managementul dependenţei

Există o mulţime de biblioteci PHP, cadre şi componente dintre care se poate alege. Proiectul ar putea folosi câteva dintre ele- acestea sunt dependenţele proiectului. Până de curând, PHP nu avea o modalitate bună de a gestiona aceste dependenţe de proiect. Chiar dacă s-a făcut manual, tot va trebui să fiţi atenţi la autoloaders. Nu mai mult. 

În prezent, există două sisteme majore de management ale pachetelor PHP - Composer și PEAR. Care este cel mai potrivit pentru tine? Răspunsul este ambele.

* Folosiţi **Composer** când manageriaţi dependenţele pentru un singur proiect.
* Folosiţi **PEAR** când manageriaţi dependenţele pentru PHP ca un întreg, pe sistemul dvs.

În general, pachetele Composer vor fi disponibile doar în proiectele pe care le specificaţi în mod explicit, iar un pachet PEAR ar fi disponibil pentru toate proiectele PHP. În timp ce PEAR ar putea părea o abordare uşoară la prima vedere, există avantaje în folosirea proiect-în-proiect potrivit dependenţelor. 
