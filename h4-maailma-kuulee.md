# h4 Maailma Kuulee

## x) Tiivistelmä

Sivulla käydään läpi askelettain, kuinka luodaan uusi virtuaali palvelin. Idea on luoda uusi virtuaalipalvelin DigitalOceanilla ja määrittää DNS-nimi NameCheapilla.
* Opiskelijana voit saada ilmaisen GitHub Education -opiskelijapaketin
* Käytä aina vahvoja salasanoja
*  Kirjaudu sisään ensinmäisellä kerralla komennolla "$ ssh root@10.0.0.1"
*  Määäritä palomuuri komennoilla "$ sudo ufw allow 22/tcp" joka sallii SSH-yhteyden ja aktivoi palomuuri komennolla "$ sudo ufw enable"
* Luo uusi käyttäjä komennolla "$ sudo adduser XXX"
* Lukitse juurikäyttäjä komennolla "$ sudo usermod --lock root"
* Päivitä ohjelmisto komennolla "$ sudo apt-get upgrade"

## a) Vuokraa oma virtuaalipalvelin

Opiskeluun kuuluu etuja. Yksi niistä on Github Education-paketti jonka saa käyttöönsä täyttämällä hakemuksen [Githu](https://education.github.com/)https://education.github.com/ sivustolla. Kun hakemus on hyväksytty, saat käyttöösi "Student Developer Pack offers" kohdasta erilaisia sovelluksia tietyksi ajaksi. Sieltä tarvitsemme käyttöömme DigitalOceanin, jonka avulla saamme vuokrattua virtuaalipalvelimen ilmaiseksi. Kun tarvittavat tiedot ollaan täytetty, on Debian dropplet valmis.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/78cc928c-8a1f-4b8b-80d8-3e6042cd4474)

## b) Alkutoimet

Seuraavaksi avataan Debian virtuaalipalvelin ja aina aluksi käydään läpi päivitykset, eli "$ sudo apt-get update" ja "$ sudo apt-get upgrade". Sen jälkeen asennetaan SSH komennolla "$ sudo apt-get install openssh-client". Asennuksen jälkeen luodaan yhteys virtuaalipalvelimeemme, joka onnistuu komennolla "$ ssh root@165.22.20.135"  (ip löytyy DigitalOceanin sivustolta). Monen yes kysymyksen jälkeen syötetään aikaisemmin luotu salasana ja päästään sisään palvelimeen.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/01627097-0acb-4176-aad8-19f694e004c1)

Seuraavaksi asennetaan ja kytketään firewall päälle.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/ef68eb10-e343-4328-a827-760ebb2b3ba3)

Sitten lisätään käyttäjä.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/5c222cc1-385a-45ad-ad07-d982dd5c1bb0)

Lopuksi lukitaan root-käyttäjä ja poistetaan käytöstä root-käyttäjällä kirjautuminen SSH:n kautta.

Tajusin, etten antanut käyttäjälle oikeuksia. Korjasin tämän avaamalla DIgitaloceanissa consolen ja syöttämällä komennon "sudo adduser stefan sudo".

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/a2490921-c845-4e59-b61a-1ada6cf11030)

Nyt voin poistaa käytöstä PermitRootLogin ja lopuksi sudo service ssh restart.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/1d684aa2-087e-440b-a7e0-03a7b575c65b)

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/66628a0f-e7c1-49c1-b19a-c99ebc8bf53b)

## c) Asenna weppipalvelin virtuaalipalvelimellesi

Aloitetaan asentamalla apache komennolla "sudo apt-get install -y apache2". Sen jälkeen käynnistetään apache. Sitten luodaan reikä palomuuriin komennolla "sudo ufw allow 80/tcp". Kun nämä vaiheet on tehty, kokeillaan luoda yhteys sivustoomme. Kokeilin omalla kotitietokoneellani ja virtuaalipalvelimella. Molemmat toimi.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/0c20213d-7652-46c2-a271-7e02facc86ff)

Sivusto ok (y).
## b) murtautumisyritykset :o

Yritin ohjeissa mainittuja komentoja: 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/a85817f2-ef2e-439c-8b3a-f5931efc2e9c)

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/19be4d35-8886-4bdd-b780-633bc9e82234)

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/6c982e6c-ad28-4ff9-9306-2b7738c90601)

##Lähteet: 

Linux palvelimet 2023 alkusyksy, (Tero Karvinen, 2023). Luettavissa: https://terokarvinen.com/2023/linux-palvelimet-2023-alkusyksy/

First Steps on a New Virtual Private Server - an Example on DigitalOcean and Ubuntu 16.04 LTS,(Tero Karvinen,2017. Luettavissa: https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/
