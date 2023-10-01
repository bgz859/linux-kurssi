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

Opiskeluun kuuluu etuja. Yksi niistä on Github Education-paketti jonka saa käyttöönsä täyttämällä hakemuksen [Githu](https://education.github.com/)https://education.github.com/
