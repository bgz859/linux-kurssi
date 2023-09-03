# H2 Komentaja Pingviini

## x) Lue ja tiivistä
(note opettajalle; en kääntänyt suomeksi, sillä hakeminen englanniksi helpompaa.)
## Moving and Looking around

- $ pwd (Prints the working directory)
- $ ls (List files in working directory)
- $ cd ... (Change directory to "...")

## File Manipulation

- $ nano FOO.TXT (text editor)
- $ mkdir NEWFOLDER (Create a new directory ie. folder)
- $ mv OLDNAME NEWNAME (Move or rename directory or file If NEWNAME does not exist, oldname is renamed to newname.)
- $ mv SOMEFILE NEWDIR/ (If both parameters are files, NEWNAME is overwritten, if target is a directory, OLDNAME is moved there)
- $ cp -r ORIGINAL COPY (Copy ORIGINAL to COPY. "-r" means recursive, ORIGINAL is copied with contets if it is a directory.)
- $ rmdir EMPTYDIR (Remove an empty directory)
- $ rm JUNK (Remove file named junk)
- $ rm -r FOLDEROFJUNK (Remove FOLDEROFJUNK/ and its contents.)

## Help

- $ man ls (Show manual page of a command)
- $ ls --help (Manual page is shown in 'less') 
- $ wget -h (Many commands have a short builtin help)

## Administrative commands

Operations requiring high privileges are run with 'sudo'. These commands gain ulimited privileges.
- $ sudo apt-get update (Update list of available packages(Important: Run apt-get update before giving other apt comamnds.))
- $ apt-cache search dungeon adventure (Search for software with keywords, no sudo needed)
- $ sudo apt-get -y install nethack-console (Package name is the part before dash '-' It is needed when installing.)
- $ dpkg --listfiles nethack-console (Many programs are shown in the applications menu. For most command line applications, you have to find out the right command.)
- /usr/lib/games/nethack
- $ nethack (Usually the command is the file in one of the bin/ or game/ directiories.)
- $ sudo apt-get purge nethack (Removes the game and it's system wide settings to avoid addiction (referring to teacher.)) 


## A) Micro

Asenna micro-editori. Tehtävää x) tehdessä jää väkisinkinkin (hassu sana :D) komentoja mieleen ja ajattelin, että lähestyn tehtäviä käyttämällä alustavasti vain tehtävään x) merkittyjä omasta mielestäni tärkeitä komentoja. Täten näen, jos tiivistelmästäni uupuu tärkeitä komentoja.

Aloitin ajamalla Terminaalissa "sudo apt-get update", muistiinpanoihini olen laittanut "important: Run apt-get update before giving other apt commands". Kun tämä oli valmis, kirjoitin "apt-cache search micro". Lopputulos oli turhan pitkä lista eri sovelluksia, joten lähestymistapani oli selkeästi väärä.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/a24f6fb7-4fb2-4bdb-9cdc-37555de77caf)

Tai ei ollutkaan. Lisäsin perään vielä editor, eli koko komento oli "apt-cache search micro editor". Lista lyheni huomattavasti ja sieltä löytyikin micro - modern and ituitive terminal-based text editor.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/c5a1e98c-4131-4fe8-b2c6-e9276c4bba26)

Viimeiseksi laitoin "sudo apt-get -y install micro" ja asennus oli valmis.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/417ecb38-e4e7-4022-b8b8-f01865d021ff)
(testasin vielä toimiko micro, kirjoitin vain terminaaliin "micro" ja text-editor aukesi. Tästä ei ole kuvaa.)
## B) Rauta

Seuraavaksi listataan koneen rauta. Listaamiseen käytetään komentoa "sudo lshw -short -sanitize" jonka syötettyä kysytään salasanaa. Salasanan syötön jälkeen ikävästi tulee vastaus "sudo: lshw: command not found".

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/889a2459-f658-4f0b-b22d-1d6362bfc786)

Tähän ratkaisuksi löytyi komento: "sudo apt-get -y install lshw" jonka asentamisen jälkeen yllämainittu komentoi toimii.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/2e714472-0960-45a1-a8d7-f924f4270ec9)

-> Tehtäväksi anto oli listata koneen rauta, mutta kuva kertoo enemmän kuin tuhat sanaa.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/2299e462-acf0-494c-93e5-a1093f68ad79)


## C) Kolme komentoriviohjelmaa

1. Terminator
   - Mahdollistaa monen terminaali-ikkunan samanaikaisen käytön.
   
![image](https://github.com/bgz859/linux-kurssi/assets/143337738/39c5722e-bf63-4d72-9403-bbba73927fe7)

2. Tilda Terminal
   - Naapurissa asui joskus tyttö nimeltä Tilda.
   - Voi luoda keybindeja.
   - Vaikuttaa helppokäyttöiseltä. Config löytyy napin painalluksella.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/338bb0fb-1bbe-4fed-8106-7f7d8891efa1)

3. Kitty
  - Hauska nimi
  - open-source GPU_accelerated terminal.
  - "Kitty is written in C and Python programming languages, and it is one of few terminal emulators with GPU support along with Alacritty" -Ravi Saive, https://www.tecmint.com/linux-terminal-emulators/
  - Oli maininta, että nopea. Varmasti, kun ei mitään ylimääräisiä ominaisuuksia.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/0792b4de-dba0-498d-9417-9b842a36ef04)


## D) FHS
Esittele kansiot, jotka on listattu "Command Line Basics Revisited" kappaleessa "important directories" "https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited"

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/5a9c88b8-56ad-498c-aca1-78d79bd9b54a)

En nyt ole ihan varma rehellisesti mikä oli tehtävän idea, varmaan vaan matkustaa terminaalissa ja tavallaan sisäistää komentoja, joilla edetään paikasta toiseen.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/2c6df2b8-798e-45d7-9bf2-cc818904313c)

## E) The Friendly M

Näytä 2-3 kuvaavaa esimerkkiä grep-komennon käytöstä.
Ei varmaan fiksuinta, mutta mitä olen tähän mennessä tehnyt aina ensinmäiseksi, on että olen avannut terminalin ja kirjoittanut sinne, mistä puhutaan. Kirjoitin "grep" ja sain vastaukseksi "Try "grep --help" for more information. Ilmeisesti kyseessä on erilaiset tukikomennot jotka helpottavat tiedostojen selaamista.

Esimerkkiä en saanut luotua, mutta googlesta löysin aika hyvän esimerkin, joka oli komento "grep boo /etc/passwd" joka hakee passwd nimisestä tiedostosta käyttäjän nimeltä "boo". Yritin toteuttaa tämän luomalla aikaisemmin ladattuun Micro texteditoriin tiedoston, johon kirjoitin tekstiä ja etsiä sitä grep komentoja käyttämällä, mutta en tiedä mihin Micro tallentaa tiedostot, niiiin se tyssäsi aika nopeasti siihen...

## F) Pipe

Googlammalla selvisi, että putkella meinataan merkkiä, jonka avulla voidaan "putkittaa" komentoja. Voidaan siis syöttää useampi komento, siten, että komennon jälkeen tapahtuu heti seuraava komento (?) järkevästi selitettynä :D.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/d1533f23-56c0-4ebf-a75a-a14f4395cf27)

## G) Tukki

Kaksi tapahtumaa lokiin, yksi hyvä yksi paha. Näitä tehtäviä tehdessä jos olisi samantien avannut lokin olisi varmaan saanut 100 virheilmoitusta lokiin samantien. Toivottavasti lokiin tallentuu aikaisemmat tapahtumat, niin saan sieltä virhekoodeja loppuelämäksi.

Ensinmäinen toimenpide taisi olla kielletty, laitoin "cd /var/log" ja sen jälkeen "ls" ja pääsin logeihin. Sieltä kokeilin avata aluksi kansiota, joka ei suostunut aukeamaan. Koska käytin less komentoa. Yritin sen jälkeen toista tiedostoa. kirjoitin "less /var/log/boot.log" johon tuli vastaukseksi:"/var/log/boot.log: Permission denied." Yritin tunkea läpi käyttämällä sudo komentoa aluksi. Lopputulos oli se, että kyseessä oli "binary file" joten avaaminen on turhaa jos logeja etsii. 

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/8e529561-29f9-4d1f-8cec-a00baf324241)

Kävin aika monta .log tiedostoa auki, kunnes löysin jonkin joka oli oikeasti logi. Avasin "vboxadd-install.log" tiedoston, joka tarvitsi taas oikeuksia, niin loppukomennoksi tuli "sudo less /var/log/vboxadd-install.log ja sain auki ilmeisesti jonkin asennus login. Tämä lasketaan sitten varmaan onnistuneeksi logiksi, kun debian tässä pyörii päällä.

![image](https://github.com/bgz859/linux-kurssi/assets/143337738/a341e714-4317-41aa-8410-40d2a692ba7a)


## Lähteet
24 Useful Terminal Emulators for Linux Desktop in 2023, Ravi Saive.
https://www.tecmint.com/linux-terminal-emulators/. Luettu 03.09.2023.

Piping in Unix or Linux, rishabh1322.
https://www.geeksforgeeks.org/piping-in-unix-or-linux/. Luettu 03.09.2023.

Command Line Basics Revisited, Tero Karvinen.
https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited. Luettu 03.09.2023.

grep command In Linux / UNIX with practical examples, Vivek Gite.
https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/ Luettu 03.09.2023.
