# H1 Oma linux

## 15.08.2023 Ensinmäinen oppitunti

Saimme tehtäväksi asentaa Virtuaalikoneen ja siihen Debian pohjaisen Linux palvelimen. Virtuaalikoneeksi asennettiin Oraclen Virtualbox niminen sovellus, joka on minulle ennestään tuttu. Pohdin kuitenkin ennen asentamista, teenkö asennuksen omalle pöytäkoneelleni vai avaanko koulutarkoitukseen ostamani kannettavan tietokoneen. Päädyin kuitenkin siihen lopputulokseen, että käytän kotikäytössäni olevaa tietokonetta, sillä se on huomattavasti tehokkaampi ja lisäksi minulla on käytössäni kaksi näyttöä, joka helpottaa työskentelyä huomattavasti.

## Asennus

Kun virtualbox oli asennettu, oli aika ladata Debian levytiedosto, johon oli suora linkki. Versio 12.1.0. Linuxia ja Ubuntua olen joskus koulutarkoituksessa käytetty, mutta Debian ei ole minulle ennestään tuttu. 

Kun levytiedoston lataaminen oli valmis, oli aika avata VirtualBox ja luoda Debian virtuaalikone. Virtuaalikoneen luominen on itsessään aika suoraviivaista, mutta joitakin "tweakkeja" täytyi tehdä, jotta Debian käyttöjärjestelmä toimisi vaadittavalla tavalla.

Yksiselitteisesti VirtualBoxin avattua painoimme ylhäältä sinistä nappia jossa luki "new", jonka jälkeen aukeaa valikko jossa annat virtuaalitietokoneelle nimen, päätät virtuaalitietokoneen kansion, valitset levytiedoston, käyttöjärjestelmän tyypin ja version. Nimeksi annoimme Debian ja ISO Image kohtaan liitimme levytiedoston (debian-live-12.1.0-amd64-xfce.iso). Tyypiksi laitoimme Linux, koska Debian on linux pohjainen käyttöjärjestelmä ja versioksi Debian (64-bit). En muista syytä miksi, mutta checkkasimme "Skip unattended Installation" kohdan. Jälkeenpäin selvitettyäni oletan, että syy tälle on se, että täten emme luo käyttäjää Linuxille, vaan myöhemmin Debianin asennuksen jälkeen Debianille.
![image](https://github.com/bgz859/linux-kurssi/assets/143337738/7b66c1a1-2ef6-474a-9f3e-2e947ee92504)

Hardware valikosta nostimme basememorya 2048 -> 4096 ja tietokonekohtaisesti lisäsimme prosessoreja virtuaalikoneen toimivuutta ajatellen.


