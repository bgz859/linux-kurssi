# H6 DJ Ago

## x) Lue ja tiivistä

## Python Web- Idea to Production - 2023
* Oppia eri käyttöjärjestelmiä ja selaimia
* Osata hakea tietoa
* Osata jakaa oikeuksia käyttäjille
* Osata asettaa automaattiset päivitykset
  
## Django 4 Instant Customer Database Tutorial
* Djangon asentaminen
* Database pohjainen sovellus jolla saat sivustollesi databasen
* Asennus tapahtuu komennolla "$ sudo apt-get -y install virtualenv", sitten "$ virtualenv --system-site-packages -p python3 env/
* Aina kun käytetään djangoa, täytyy muistaa aloittaa laittamalla "$ source env/bin/activate"
* "$ which pip" ÄLÄ KÄYTÄ PIP JA SUDOA SAMAAN AIKAAN!
* Uusi projekti komennolla "$ django-admin startproject xxx"
* Admin käyttäjä komennolla "$ ./manage.py createsuperuser"

## Deploy Django 4 - Production Install
* Apachen ja Djangon asentaminen ja niiden yhdistäminen
* Lataa apache2, configuroi.
* Lataa django, configuroi.
* Python yhdistetään apacheen käyttämällä mod_wsgi
* VirtualHost config tiedoston avulla yhdistäminen mahdollista.
* TDIR: /home/käyttäjä/publicwsgi/serverinimi
* TWSGI: /home/käyttäjä/publicwsgi/servernimi/servernimi/wsgi.py
* TVENV: /home/käyttäjä/publicwsgi/env/lib/pythonversio/site-packages
* Apache WSGI module, jotta Apache tietää mitä WSGI komennot tarkoittavat: "$ sudo apt-get -y install libapache2-mod-wsgi-py3"


## a) Asenna Django

Kuten aina alussa, avataan VM virtuaalikone. Edetään alustavasti ohjeiden mukaan ja katsotaan mihin asti päästään ilman ongelmia.

Aluksi avataan command prompt ja syötetään "$ sudo apt-get -y install virtualenv" ja sen jälkeen luodaan uusi kansio "evn/" johon saadaan uusimmat paketit. Tähän käytetään komentoa "$ virtualenv --system-site-packages -p python3 env/"

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/42eaf15c-b524-4484-99f8-e9bdf8ae091b)

Tässä kohtaa tajusin, että unohdin juosta sudo-apt get updaten, niin tein sen nyt.

Ohjeissa seuraavaksi käytetään virtuaali ympäristöä ajamalla komento "$ source env/bin/activate" tällä komennolla command promptin alkuun tulee (env) joka ilmeisesti tarkoittaa sitä, että kun (env) on ajettu, kaikki python paketit asentuvat sen sisälle.

komennolla which pip nähdään ilmeisesti, mihin asennetaan. Seuraavaksi ohjeissa sanotaan "Lets list our single Python package in a text file", joka tuottaa ongelmia. Ohjeissa annetaan komentoja, joita olen yrittänyt laittaa, mutta toistaiseksi komento "$ django-admin --version" ei anna haluttua ratkaisua.

Ratkaisu oli, että komento "$ micro requirements.txt # "django" ctrl-s saves, ctrl-q quits" oli myös ohje, jonka fiksumpi olisi varmasti heti tajunnut.
Komennolla avataan micro editor, johon kirjoitetaan sisään "django" ja loppuosa tallentaa ja sammuttaa micro editorin.
cat requirements.txt käy läpi tiedoston sisällön ja kun sisältö on "django" komennolla "$pip install -r requirements.txt" saadaan asennettua tiedoston sisältö? eli django.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/b83118b7-82f6-478b-aac8-ea41770e193e)

komennolla "$ django-admin --version" saadaan esiin versio, joka meillä on 4.2.5. Ohjeissa se on 4.0.2 mutta varmaan hieman vanhempi ohje, niin ei välitetä tästä.

Seuraavaksi luodaan projekti. Komennolla "$ django-admin startproject stefanba" tämä ilmeisesti onnistuu.

Viimeiseski ajetaan komento "$./manage.py runserver" ja serveri on päällä.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/33f2503b-5e94-4e51-8276-92a86446c631)

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/03df7791-24d8-4bc4-91ef-52f5a226a395)

Django valmis.

## b) Yksinkertainen esimerkkitietokanta Django-kehitysympäristöön

Seuraavaksi luodaan esimerkkitietokanta. Edetään taas tero karvisen ohjeiden mukaan kohdasta "Admin interface - for free" ja katsotaan miten pitkälle päästään ilman ongelmia.

Ensinmäisenä lisätään admini. Tämä onnistuu siten, että aluksi updatetaan database kahdella komennolla "$ ./manage.py makemirgations" ja "$ ./manage.py migrate"

En tiedä miten serverinäkymästä pääsee pois, niin suljin promptin ja syötin aluksi "source env/bin/activate" ja "which pip" niin näen että ollaan oikeassa paikassa. Seuraavaksi avataan projekti taas komennolla "$ django-admin startproject stefanba"
Eipä tehdäkkään näin koska projekti on jo olemassa.. komennolla "$ cd stefanba" saadaan oikea näkymä auki.

Komento "./manage.py makemigrations" antaa vastaukseksi "no changes detected" ja "./manage.py migrate" antaa kaikesta OK selkeästi. 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/362a113e-03d5-44fa-82ac-5a19db7787e8)

Seuraavaksi lisätään käyttäjä komennolla "./manage.py createsuperuser" ohjeissa annetaan pwgen ohjelma, jonka avulla saadaan luotua turvallinen salasana. Käytän sitä tässä tehtävässä ja laitan salasanan tänne talteen :D stefan HtGrBjS66ydCMDuXeTP8
Fiksua!
Kun tämä on tehty, voidaan kokeilla kirjautua sisään adminina. se onnistuu lisäämällä url perään /admin eli "127.0.0.1:8000/admin ja päästään sisäänkirjautumis sivustolle.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/e7460ee7-d665-4bd5-aa44-4b3e40a8a0cc)

ja näin ollaan admin viewissä. 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/06ce7d5e-f4ba-4b7a-a305-75ff417cfc02)

Täällä voidaan ilmeisesti luoda ryhmiä ja käyttäjiä databaseen.

Seuraavaksi luodaan tietokanta, joka olisi varmaan täytynyt tehdä ensin, mutta oletan että admin käyttäjän luotua tämä onnistuu helpommin.

Opin myös, että kun server on laitettu päälle, pikanäppäimillä CTRL + C voidaan sulkea serveri, eikä aina tarvitse avata cmd promptia uudelleen. Kätevää.

Aluksi syötetään komento "$ ./manage.py startapp crm" joka luo kansion crm/.

Sen jälkeen avataan "settings.py" tiedosto ja lisätään "INSTALLED_APPS" kohtaan 'crm'.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/9e6b43f9-cbab-42a1-94c1-b0003ff6c86d)

Sitten lisätään modeleita.. komennolla "$ micro crm/models.py" lisätään pari pätkää tekstiä.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/a052a892-49be-4706-b41b-2dec6b545b11)

Tämä luo Customer tablen databaseen johon tulee nimiä.

Tämän jälkeen ajetaan "$ ./manage.py makemigrations" ja "$ ./manage.py migrate" jotta saadaan muutokset käyttöön.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/8958355f-948f-493c-bb95-da2ff114fe0d)

Jotta uusi luomamme database saadaan näkyviin admin näkymässä, tämä täytyy vielä rekisteröidä. Komennolla "$ micro crm/admin.py" muokataan admin.py tiedostoa ja syötetään sinne pari pätkää tekstiä joilla saadaan muutokset adminnäkymään. 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/7440116c-77ae-44f1-825d-5776d18b86bd)

Lopuksi katsotaan toimiko muutokset ajamalla serveri komennolla "$ ./manage.py runserver" ja kirjaudutaan taas adminilla tuttuun tapaan.

Tässä tuli errori, sillä olin laittanut admin.py tiedostoon Customer kohdan isolla kirjaimella, vaikka alkuperäisessä tiedostossa se oli pienellä. Muutoksen tehtyä serveri käynnistyi normaalisti.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/556f086e-83a2-4f67-ade6-edb02c64ac3a)

nyt admin näkymässä näkyy uusi "pöytämme"

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/553170e2-792e-4fc5-8b38-d7b162869296)


## c) Tee Djangon tuotantotyyppinen asennus omalle, paikalliselle virtuaalikoneellesi Apachella

Lähtökohta tähän hieman mitäänsanomaton. Molemmat ohjelmat ovat jo periaatteessa asennettu virtuaalikoneelle, niin saa nähdä miten paljon pulmia tässä tulee. Lähtökohtaisesti varmaan etenen Tero karvisen ohjeiden mukaan ja taas ongelmatilanteessa raportoin tarkemmin. Tähän osioon en lisää komentoja, sillä samoja komentoja ollaan käyty läpi jo useammassa raportissa ja kohdassa.

Lähtökohtaisesti aluksi asennetaan apache2, joka löytyy ennestään.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/1b5c51cf-0a5b-46ea-92c6-10befc68ffca)

Tämä kuva vain muistiin, mitä olen aluksi tehnyt.

Seuraavaksi VirtualHost.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/0544a63c-90ae-47ab-83c5-390c9798ef49)

Sitten enable our new website ja disable others :D

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/d91a7dc2-867e-48fe-80f8-3ffba738dc5f)

Tässä mainitaan, että jos on muitakin sivustoja, niin täytyy katsoa toinen ohje. Tämän jätän toiseen kertaan, sillä tiedän että tämä tulee tulevaisuudessa vastaan, jos suljen pois käytöstä edellisten tehtävien serverit /sivustot.

Tässä kohtaa huomasin, että "localhost" toimii, mutta "localhost/static/" antaa virhekoodin "403 forbidden". Selvitellään vähän.

Ongelma toivottavasti löytyi. Jep. Ongelma oli, että virtuaHost koodissa oli ohjeiden mukaisesti teroco oman kansioni sijasta.. Onneksi ei mitään sen vakavampaa.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/292d2110-be66-4034-9777-a9afcecb13bc)

Seuraavaksi asennetaan Django uudelleen. Tätäkään en raportoi sen enempää, ennenkuin tulee ongelmakohtia.

Ohjeiden mukaisesti kaikki ok toistaiseksi, Django asennettu.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/b38ea81a-a4f8-46d3-8b55-eb2f49506943)

Tämän projektin nimeksi tulee "stefan" koska edellinen taisi olla stefanba". Nyt tulee varmasti isoin kohta, eli "Connect Python to Apache using mod_wsgi" Tässä tärkeintä on tietää 3. tiedostopolkua. Laitan ne tähän ylös.
/home/stefanb/publicwsgi/stefan/ (TDIR)
/home/stefanb/publicwsgi/stefan/stefan/wsgi.py/ (TWSGI)
/home/stefanb/publicwsgi/env/lib/python3.11/site-packages/ (TVENV)

Nyt hieman muokataan virtualhost tiedostoa.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/bda25d6c-ddad-4a84-95ec-82c4884df9a6)

Kirjoitin kaiken käsin, niin en ihmettele jos tämän takia ei homma toimi.. ainakin helppo katsoa heti mistä voisi johtua.

Seuraavaksi asennetaan Apache WSGI moduuli, jotta Apache ymmärtää mitä WSGI komennot tarkoittavat.

Eipä asennetakkaan, saan "AH00543: apache2: bad user name stefan" errorin. Tätä selvitellään seuraavaksi. No onneksi kuten yllämainitsin, käsinkirjoituksesta aiheutui harmia. TUSER kohtaan olin laittanut "stefan" vaikka piti laittaa "stefanb". Tämän tehtyä ajoin "$ /sbin/apache2ctl configtest" uudelleen ja sain seuraavan errorin. 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/31260197-e169-4a1a-b0d8-8ed15eb89aaf)

Tämä errori johtui siitä, että TVENV kohdassa ohjeessa on "python 3.9" jonka kopioin siitä suoraan, vaikka piti laittaa oma versioni, eli 3.11.

Saan erroria AH00526 Syntax Error;

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/bc013d6b-9402-4fc0-9fc5-63c5439cd9b7)

Tein muutaman muutoksen, sillä esim static oli eri paikassa kuin muut tiedostot. Tämä ei vaikuttanut, mutta auttaa loppuun tekemisessä. Tällä hetkellä olen käynyt vain koodipätkää läpi ja etsinyt virheitä ja kokeillut kansiot läpi että kaikki toimii. Toistaiseksi tuloksetta.

No ihme ja kumma, kokeilin huvikseen avata virtuaalikoneen selaimella Tero Karvisen sivuston ja kopioida koko koodipätkän ja liittää sen tiedostoon ja muuttaa tarvittavat tiedot ja yllätys yllätys sehän toimi..

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/22ae35ff-596a-44bc-9372-27cb93bd8009)

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/df5838fa-701f-481c-93bf-2bf4bb79366f)

Viimeisenä teen debug osiota, ohjeiden mukaan.. "import os STATIC_ROOT = os.path.join(BASE_DIR, 'static/') antaa "no such file or directory". Varmaan väärästä paikasta haen mutta saa nähdä.

Collect static ei vaan jostain syystä toimi. Tähän luovutan.. Taitaa olla viimeinen kohta tehtävästä muutenkin. Luultavimmin settings.py tiedostossa jokin väärin ja siitä johtuen ei toimi. Palaan tähän ensitunnilla. Kiitos

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/ec316e68-0bdb-4e1d-a58a-e8e02445de8d)

Tyhmä minä, piti laittaa "source env/bin/activate" ja sitten komento, kokeilin aikaisemmin, muttei jostain syystä lähtenyt toimimaan. Nyt lähti mutta poistin "STATIC_URL" kohdan settings.py tiedostosta.. Palautan sen ja kokeilen uudelleen, varmaan toimii sitten..

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/02e216fd-f6b6-49f1-96ca-07a7691aa891)

boom toimi kaikki hyvin jee
