# H3 Hello Web Server

## x) Tiivistelmä
Sivulla on esitetty miten voidaan asentaa Apache Web Server:
* sudo apt-get install apache2: Asentaa apache2.
* http://localhost: Voidaan löytää oma palvelin selaimesta.
* sudo a2enmod usedir: Annetaan oikeudet käyttäjälle luoda oma sivusto.
* sudo systemctl restart apache2: Komennon avulla käynnistetään apache2 uudelleen, jotta saadaan oikeudet voimaan.
* mkdir public_html: Tämän avulla voidaan testata, että sivusto toimii. Seilaimeen syötetään "http://localhost/~omanimi/".

## a) Asenna Apache webbipalvelin

Tehtävien aloittaessa on aina hyvä muistaa aluksi syöttää komento "sudo apt-get update". Tällä varmistetaan, että ollaan ajantasalla, eikä sen vuoski tule vikakoodeja, joita myöhemmin joudutaan selvitellä.
Kun päivitykset ollaan suoritettu, voidaan aloittaa. Ensinmäiseksi syötetään komento "sudo apt-get install apache2". Tällä komennolla asennamme Apache Web serverin meidän debianiimme.

Kun asennus on valmis, kokeilemme sen toimivuutta syöttämällä selaimemme hakupalkkiin "http://localhost" tai ohjeiden mukaan "$ firefox "http://localhost".

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/0882e099-87ba-404a-bdf2-f8d4cb8242a7)

Ilmeisesti jos asennus on onnistunut ja tähdet ovat kohillaan, aukeaa nettisivulle localhost, jossa lukee "It works!"

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/920b0025-f00e-4b3d-ba94-1a3aa45adcd0)

Apachen Web Serverin asennus on valmis.

## b) Lokit

Seuraavaksi etsimme lokista rivit, jotka syntyvät, kun lataamme omalta palvelimeltamme sivun. Syötin komentoriviin "$ firefox "http://localhost/~stefanb/" ja lopputulos oli "Not Found". Yllättävää..

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/bead8445-2275-43ab-b908-f53811789006)

Lokeihin pääsemme syöttämällä komennon "sudo tail -F /var/log/apache2/access.log". Access login avulla näemme pyynnöistä jotka tulevat serverille, mitä sivustoja ihmiset katsovat, onnistuiko pyynnöt ja kuinka kauan pyyntöön kesti vastata:

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/e1a2dbec-4e84-431e-8582-62ef4e41eac1)

sekä
"sudo tail -F /var/log/apache2/error.log" Error login avulla näemme, mitkä pyynnöt eivät onnistuneet.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/12a917ab-e3a3-462a-bdaa-968c3db5563a)

En itse suoranaisesti osaa error logista sanoa, mitä tapahtui. Tiedän vain, ettei palvelimellani ole mitään sisältöä, enkä omista vielä maksullista palvelinta, joten sivusto ei vain toimi.

Logeissa virhekoodien avulla kuitenkin voidaan helposti internetin avustuksella selvittää ongelmatilanteet syöttämällä virhekoodi.

## c) Vaihda Apachen esimerkkisivu

Seuraavaksi muutamme esimerkkisivun. Tämä onnistuu siten, että menemme terminaalissa var > www > html ja muokkaamme index.html tiedostoa. Syötin komennon "cd /var/www/html" ja "micro index.html" Micro on viimeksi lataamamme tekstinkäsittely ohjelma, jonka avulla muokkaamme index.html tiedostoa.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/a9c5fe7f-ea1f-4f31-ad1d-6c23a9e67929)

Kun komennot on syötetty aukeaa editori ja voimme muokata sivustoamme mieleiseksemme.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/d51476c1-2d9e-42e6-b134-60d95e94e65d)

Käytin kaiken luovuuteni ja muutin sivuston siten, että sivustosta käy ilmi, että kyseessä on minun sivusto.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/9e1c9651-3a3f-44f1-871d-786f45db94e2)

Ja näin.

## d) ja e) Käyttäjien kotisivut ja HTML5 sivuston luonti

Seuraavaksi luodaan käyttäjille omat kotisivut. Tämä onnistuu syöttämällä seuraavat komennot temrinaaliin: "sudo a2enmod userdir" "systemctl restart apache2" "mkdir public_html". 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/18a96684-b435-4860-ba2f-dbd37438aa98)

Seuraavaksi syötetään komento "micro index.html" jonka avulla luomme ja samalla muokkaamme kotisivustoa.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/4e680abf-ae81-4a9b-b729-1b671a2e14bb)

Jotta sivustolle saadaan sisältöä, lainaamme terolta "Short HTML5 page" pohjaa "https://terokarvinen.com/2012/short-html5-page/".

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/5bc375df-6027-485e-9475-5cda20fbf345)

Kun sivu on valmis, tallennamme "ctrl + s" ja voimme tarkistaa toimiiko sivustomme syöttämällä terminaaliin 
"$ firefox "http://localhost/~stefanb"

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/788e4b2a-949e-46b6-97ec-7c83dc095d20)

Ja näin olemme onnistuneesti luoneet oman toimivan hienon kotisivuston.

Lopuksi tuli vielä tarkistaa, onko weppisivu validi käyttämällä "http://vlaidator.w3.org" sivustoa. 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/674691df-2de6-493c-8788-a3df29555eef)

Kaikki ok.

## f) curl-I ja curl komennot

Kuten aikaisemmin, ei näistäkään komennoista ole minulle kumpikaan ennestään tuttuja, joten aloitin syöttämällä terminaaliin "curl-I" komennon ja katsomalla, mitä käy.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/93e097db-f09f-4bb4-8dba-594c79eeb2c1)

Harmi. Googlaamalla ja kaverin naurun jälkeen tajusin, että pelkkä curl komento ei riitä. Curlin avulla voidaan tuoda dataa "from the server to client" ja toisinpäin. lisäsin curl komennon loppuun localhost/~stefanb eli "curl "http://localhost/~stefanb" ja alkoi tapahtua.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/0ae7cd02-5e23-4684-a3d8-8960357faea9)

Seuraavaksi kokeilin komentoa curl -l "http://localhost/~stefanb" ja katsoin mitä käy. No komentoa ei ole edes olemassa, tajusin, että kyseessä on iso i eikä L. Heh. Syötin siis "curl -I "http://localhost/~stefanb""

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/97d4c036-d377-411b-9765-855762cb1397)

curl -I komento tulostaa HTTP pyynnön, päivämäärän, serverin, sivuston ja tyypin.

## Lähteet

Install Apache Web Server on Ubuntu, Tero Karvinen. https://terokarvinen.com/2008/05/02/install-apache-web-server-on-ubuntu-4/ Luettu 11.9.2023

Access and Error Logs, Solarwinds. https://www.loggly.com/ultimate-guide/access-and-error-logs/ Luettu 11.9.2023

