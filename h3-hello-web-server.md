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
