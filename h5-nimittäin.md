# h5 Nimittäin

## x) Tiivistelmä

## Omien nettisivujen luonti Apache2 avulla.

* Apache2 asennetaan komennolla "sudo apt-get -y install apache2
* Virtualhostin-konfiguroaatiotiedosto "/etc/apache2/sites-available/tero.conf"
* Vanha virtualhost pois ja Uusi virtualhost käyttöön komennolla "sudo a2ensite" ja "sudo a2dissite"
* Uudelleen käynnistys "sudo service apache2 restart"
* Oma kotisivusto löytyy osoitteesta "http://localhost"
* HTML5-kotisivuston voi valitoida osoitteessa "http://validator.w3.org"
* Voit muokata omaa sivustoasi

## Monen web-sivuston "hostaaminen"

Sivustolla kerrotaan step-by-step kuinka hostata montaa eri sivustoa yhdellä ip-osoitteella.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/c54597f3-cab1-4757-b03e-18862d465cef)

* Toimivuutta voi kokeilla komennolla "$curl -H 'Host: osoite' localhost" ja "$ curl localhost"

## IP-pohjainen ja Nimi-pohjainen virtuaalipalvelin Apachessa

* IP-pohjaisessa virtuaalipalvelimessa käytetään yhteyden IP-osoitetta oikean virtuaalipalvelimen valitsemiseksi. Tämä tarkoittaa erillistä IP-osoitetta joakiselle palvelimelle
* Nimipohjaisessa virtuaalipalvelimessa palvelin luo
