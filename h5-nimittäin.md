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
* Nimipohjaisessa virtuaalipalvelimessa palin käyttää host-nimeä, eikä jokaisella verkkosivustolla tarvitse olla omaa erillistä IP-osoitetta. Tämä edellyttää DNS-palvelimen konfigurointia, jotta se tunnistaa eri hostnamet.

## a) Vuokraa domain-nimi

Tähän tehtävään käytän hyödyksi Github education pakettia. Sieltä voi hakea itselleen mieleisen sivuston syöttämällä halutun url:n. Valitsin itselleni ilmaisen "stefanstefanstefan.me" osoitteen. Tämä edellyttää sivustolle rekisteröitymistä.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/8de0531d-d942-4c1a-8859-e23a1828a87c)

Seuraavaksi liitetään osoitteemme virtuaalipalvelimeemme.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/156dc2f3-f2b7-4259-861c-7897cd98d090)

Kaverini vinkkasi, että TTL tarkoittaa "Time to live" johon laitoin 60min.

Kokeilin ja heti kun olin syöttänyt tarvittavat tiedot, niin sivusto toimi välittömästi.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/2e48aeba-8c0a-4c34-8a4a-2b0382c90e8c)

Sivusto on nyt ok.

## b) Tutki oman nimesi tietoja

Seuraavaksi käytetään komentoja "host" ja "dig". Tehtävässä analysoidaan tuloksia. Lähdetään liikkeelle asentamalla host komennolla "$ sudo apt-get install host" ja "$ sudo apt-get install dnsutils".

Asentamisen jälkeen syötetään komento "$ host stefanstefanstefan.me" (oma osoitteeni).

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/e84abaf7-0a9f-4931-9c5b-74cbdcd77842)

Tuloksena saatiin palvelimen ip-osoite, sekä ilmeisesti osoitteeseen liittyvän sähköpostiin liittyvää tekstiä, mutta en osaa kertoa mitä se käsittelee.

Seuraavaksi syötetään komento "$ dig stefanstefanstefan.me"

Komento käy läpi kyselyn, jonka tuloksena näkyy virtuaalipalvelin, osoitteemme, IP-osoit, kyselyn aika, milloin kysely on tehty ja serverin ip.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/47d72029-5463-4b58-b0ba-234bf4e3c3d8)

## c) Etusivu uusiksi

Seuraavaksi muutetaan kotisivustomme etusivu siten, että uusi kotisivustomme näkyy osoitteessamme, sivuston tulee olla tallennettu jonnekkin kitohakemistojen alle ja muokattavissa ilman sudo komentoa.

En ole varma, olenko tehnyt tehtäväni oikein, mutta lähtökohta on se, että Localhost ja oma nettisivustoni avaavat eri sivuston. Tämä taisi olla yksi tehtävän tavoitteista. 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/b1e25b52-cc65-43c4-a2a8-e802a306fd66)

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/a9188d08-b362-42b7-8aa1-1693895a2666)

Muutan "stefanstefanstefan.me" sivuston siten, että se on tallennettu myös kotihakemistojen alle ja muokattavissa ilman sudoa.

Nyt pienen säätämisen jälkeen sain luokkalaiseltani aika runsaalla kädellä apua tehtävän tekemiseksi, sillä olin täysin jumissa. Tästä syystä raportointi aika mitätöntä. Periaatteessa olen luonut omalle sivustolleni uuteen URL:iin ja muokannut siitä alkeellisen mutta toimivan.

Pitkän säätämisen jälkeen törmäsin ongelmaan, jossa aina kun yritän syöttää komennon "sudo a2ensite stefanstefanstefan.me" saan vastaukseksi: "a real file, not touching it". Tämän kanssa meni n. tunti, ennenkuin löysin netistä ohjeen mistä mättää.. Olin siis luonut ilmeisesti tiedoston väärään paikkaan.. En nyt ihan varmasti tiedä, mikä auttoi, mutta aluksi syötin komennon sudo "a2dissite stefanstefanstefan.me" ja sitten siirsin tiedoston paikasta "sites-enabled" paikkaan "sites-available". Lisäsin myös tiedoston loppuun "stefanstefanstefan.me.conf" poiketen siten, että edellisessä tiedostossa nimenä oli "stefanstefanstefan.conf" en tiedä vaikuttiko nimi, mutta nyt komento "sudo a2ensite stefanstefanstefan.me.conf" toimii.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/d5e96cda-2d0e-45fd-89dc-05fb2f6a998f)

No kaiken tämän jälkeen sain lopulta sivustoni näkymään omalla tietokoneellani, puhelimella ja virtuaalikoneella. 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/9f00d89e-0a4c-411a-b8c8-02245d103e0d)

## Lähteet

forum:piki, Käyttäjä forumilla Luettavissa: https://www.linode.com/community/questions/6592/sites-enabled-and-sites-available-confusion
New Default Website with Apache2, (Tero Karvinen, 2016) Luettavissa: https://terokarvinen.com/2016/02/16/new-default-website-with-apache2-show-your-homepage-at-top-of-example-com-no-tilde/
Name Based Virtual Hosts on Apache, (Tero Karvinen, 2018) Luettavissa: https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/
Name-based Virtual Host Support, (Apache) Luettavissa: https://httpd.apache.org/docs/2.4/vhosts/name-based.html
