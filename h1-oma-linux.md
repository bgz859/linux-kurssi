# H1 Oma linux

## 15.08.2023 Ensinmäinen oppitunti

Saimme tehtäväksi asentaa Virtuaalikoneen ja siihen Debian pohjaisen Linux palvelimen. Virtuaalikoneeksi asennettiin Oraclen Virtualbox niminen sovellus, joka on minulle ennestään tuttu. Pohdin kuitenkin ennen asentamista, teenkö asennuksen omalle pöytäkoneelleni vai avaanko koulutarkoitukseen ostamani kannettavan tietokoneen. Päädyin kuitenkin siihen lopputulokseen, että käytän kotikäytössäni olevaa tietokonetta, sillä se on huomattavasti tehokkaampi ja lisäksi minulla on käytössäni kaksi näyttöä, joka helpottaa työskentelyä huomattavasti.

## Asennus

Kun virtualbox oli asennettu, oli aika ladata Debian levytiedosto, johon oli suora linkki. Versio 12.1.0. Linuxia ja Ubuntua olen joskus koulutarkoituksessa käytetty, mutta Debian ei ole minulle ennestään tuttu. 

Kun levytiedoston lataaminen oli valmis, oli aika avata VirtualBox ja luoda Debian virtuaalikone. Virtuaalikoneen luominen on itsessään aika suoraviivaista, mutta joitakin "tweakkeja" täytyi tehdä, jotta Debian käyttöjärjestelmä toimisi vaadittavalla tavalla.

Yksiselitteisesti VirtualBoxin avattua painoimme ylhäältä sinistä nappia jossa luki "new", jonka jälkeen aukeaa valikko jossa annat virtuaalitietokoneelle nimen, päätät virtuaalitietokoneen kansion, valitset levytiedoston, käyttöjärjestelmän tyypin ja version. Nimeksi annoimme Debian ja ISO Image kohtaan liitimme levytiedoston (debian-live-12.1.0-amd64-xfce.iso). Tyypiksi laitoimme Linux, koska Debian on linux pohjainen käyttöjärjestelmä ja versioksi Debian (64-bit). En muista syytä miksi, mutta checkkasimme "Skip unattended Installation" kohdan. Jälkeenpäin selvitettyäni oletan, että syy tälle on se, että täten emme luo käyttäjää Linuxille, vaan myöhemmin Debianin asennuksen jälkeen Debianille.
![image](https://github.com/bgz859/linux-kurssi/assets/143337738/7b66c1a1-2ef6-474a-9f3e-2e947ee92504)

Hardware valikosta nostimme basememorya 2048 -> 4096 ja tietokonekohtaisesti lisäsimme prosessoreja virtuaalikoneen toimivuutta ajatellen.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/a6d8a623-4bba-4cfc-83da-378460385612)

Hard Disk valikosta annoimme kovalevlle lisää muistia. 60gb oli kuulema riittävä.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/4a4b2e90-8290-4a71-9262-19b7b4b79f9b)

Kun asetukset olivat valmiit, painoin Finish ja virtuaalikone on valmis.

## Debian

Virtualboxin vasemmasta valikosta näkee asennetut tietokoneet ja meidän tilanteessa Debian. Painoin sen auki tuplaklikkaamalla (ylhäältä voi valita myös vihreän "start" nappulan) ja hetken lataamisen jälkeen aukesi uusi ikkuna jossa oli debian boot menu. 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/b517d40f-3f1a-44ad-9109-7b076368c71d)

Boot menusta valitsin "Live system (amd64)" ja taas odotettiin..

Lopulta aukesi käytännössä tutun näköinen käyttöjärjestelmä. Saimme opettajalta vinkiksi, että internetissä kannattaa käydä, jotta näkee saako virtuaalitietokone internetyhteyden. Tämän tarkastettuani olin valmis jatkamaan asennusta.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/7c1008e2-5b1b-4539-b191-81dd729a5fe5)

Työpöydältä löytyi valmiiksi "install debian" pikakuvake jota painamalla aukesi varoitus "Untrusted application launcher" mutta koska kyseessä on virtuaalikone ja koulutehtävä luotin pikakuvakkeeseen varoituksesta huolimatta ja painoin "launch anyways"

## Debianin asennus

Installer avautui ja ruudun täytti "Debian GNU/Linux-asentaja" ikkuna. Ensinmäisestä ikkunasta valittiin käyttöönotettava kieli joksika valittiin Englanti. Syy tälle on se, että virhekoodeja ja herjauksia on helpompi selvittää, kun virheilmoitukset tulevat englanniksi.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/a0a1eda0-828b-4c59-9974-41cceb6e69cf)

Location valikosta loogisesti Helsinki, jotta pysytään reaaliajassa.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/484e04ec-b51d-42f7-82e8-dcd39967e8a9)

Näppäimistön kieleksi vaihdettiin "Finnish", tarkemmin "Finnish (classic). Tässä kohtaa piti muistaa tarkistaa, toimiiko äöå kirjaimet.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/b0b2a472-68cb-4666-a724-9835f994c876)

Partition kohdassa valitaan "Erase disk".

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/72e631dc-21d2-4954-994f-37ce9b6a733b)

Users kohdassa täytetään omat tiedot ja luodaan käyttäjä käyttöjärjestelmälle. Salasana tässä tärkeä, sillä ei haluta, että ulkopuoliset tahot pääsevät käsiksi tietokoneeseen ja sen sisältöön.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/c2de8326-2451-4fcf-9736-b74e53c62649)

Summary kohdassa on bugi (tai huono feature), jonka vuoksi siitä ei pääse etenemään, tai siltä se aluksi näyttää. 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/f2bf1584-7efb-4b61-bc30-40e6a6dad161)

Syy tälle on se, että ikkuna ei ole virtuaalikoneen sisällä valittuna kokonäytölle. Kun ikkunan suurentaa koko näytölle ylhäältä pikkuneliöstä, ilmestyy alhaalta 3. nappulaa lisää, joista tärkein "install".

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/d0aef1bd-3405-426c-8566-da0c19c0d911)

Tämän jälkeen ollaan valmiita Debianin asennusikkunan kanssa ja voidaan painaa "install". (Ja taas odotella.)

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/1b75da04-90ec-46d4-be66-64eaaf4749a8)

Kun asennus on valmis, Debian pyytää käynnistämään tietokoneen uudelleen. Checkkasin "restart now" ja painoin "Done" ja tietokone käynnistyi uudelleen.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/69e1f5e4-752e-4b60-8836-41eaf5ee304d)

Kun kone on bootannut uudelleen aukeaa "log in" ikkuna johon syötin käyttäjänimen ja salasanan.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/2a38a3bc-7cbb-4c1a-a389-b660fdc56d35)

Tässä vaiheessa on hyvä taas tarkistaa, toimiiko internetyhteys.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/3e5de6ef-ca83-41cb-8c87-ee871802e1e6)

Kaikki toimii ja Debianin asennus onnistui ongelmitta. Hyvä minä!

## Final steps

Lopuksi ohjeessa pyydetään tarkistamaan päivitykset Debianin terminal emulatorin avulla. Avasin Terminal emulatorin ja syötin komennon "sudo apt-get update". Sain vastaukseksi "[sudo] password for stefanb". (Tämä johtuu m siitä, että komennon alussa oleva "sudo" tarkoittaa "use superuser privlidges" eli möyntää käyttäjälle selkokielellä kaikki oikeudet.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/e131458b-d381-48da-bb44-9b80829bd2c5)

Kun päivitykset on ladattu, syötetään uusi komento terminal emulaattoriin; "sudo apt-get -y dist-upgrade". Ohjeessa lukee, että -y tarkoittaa "yes" jolla ilmeisesti tuetaan komentoa "dist-upgrade" joka taas tarkoittaa upgrade everything.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/df27a669-374e-4a9d-9b18-f639801a7854)

Tämän jälkeen silmääni pisti komentorivin 3. viimeistä kohtaa.
I: The initramfs will attempt to resume from /dev/sda2
I: (UUID=a433e3bc-4d42-49e6-b5e0-3dc998249779)
I: Set the RESUME variable to override this.

Googlaamalla selvisi, että tämä voi johtua siitä, että käyttöjärjestelmä on asennettu toisen käyttöjärjestelmän sisälle. En alkanut korjaamaan ongelmaa, sillä oletettavasti kaikilla muillakin herjaa samaa asiaa. Tämä varmasti selviää seuraavalla oppitunnilla.

Viimeisenä syötin terminal emulaattoriin "sudo apt-get -y install ufw" joka asentaa firewallin tietokoneelle.

Kun asennus oli valmis syötin vielä "sudo ufw enable" joka laittaa firewallin päälle.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/67d7bd19-cc93-4806-9384-ead338a3ec49)

Ja näin kaikki on valmista.









