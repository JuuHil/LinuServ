# Tukki
## Tehtävät
![tehtavat](https://user-images.githubusercontent.com/122887067/215345281-cbd1ac7d-43d9-4c72-8a64-b519801d9843.png)


## Rauta

    Koneen rauta ja käyttöjärjestelmä
    CPU:  i7-13700K 5,4GHz
    RAM:  32GB DDR5 5200Mhz
    GPU:  RTX 3080 OC 10G
    OS:   Windows 10 Pro, Versio 21H2
    
    Versiot. 
    VirtualBox -7.0.6-155176.
    debian-live -11.6.0


## Tiivistelmä
![image](https://user-images.githubusercontent.com/122887067/215345338-e9be1757-9756-4335-9aef-c136396c3b36.png)
- Artikkelissa näytettiin kuinka Linux komentokehote auttaa sinua pelaamaan Wordle-sanapeliä.

- Wordle pelissä on kuusi yritystä arvata satunnainen viisikirjaiminen sana.
- Sana muuttuu joka päivä, ja voit pelata vain kerran päivässä
- Jokaisen arvauksen jälkeen jokainen arvauksesi kirjain on korostettu eri väreillä
    - Harmaa tarkoittaa, että kirjain ei esiinny sanassa
    - Keltainen tarkoittaa, että kirjain on sanassa, mutta väärässä kohdassa.
    - Vihreä tarkoittaa, että kirjain on sanassa ja se on oikeasssa kohdassa. 
    - Esimerkki. ![image](https://user-images.githubusercontent.com/122887067/215345522-3b981dae-20aa-4e27-bc04-feeb96fa3975.png)
- Tarvittiin vain tiedosto, jossa on todella paljon eri sanoja ja ```grep```
- ```grep```:in avulla päästiin ensimmäisen arvauksen jälkeen 15 000 mahdollisesta sanasta, 1200 sanaan. 
- Kolmannella yrityksellä vaihtoehtoja jäi jäljelle enää 7. 
Artikkeli: https://opensource.com/article/22/1/word-game-linux-command-line!

## Tukki
21:05-21:50
### 1 `/var/log/syslog`
Ajoin komennon

    sudo cat /var/log/syslog

valitsin lokin

`Jan 30 21:06:47 pug systemd[1]: Startup finished in 3.905s (kernel) + 1.393s (userspace) = 5.298s`

Ensimmäisenä on päivämäärä ja kellonaika. ```pug``` on tietokoneen nimi. ```Startup finished... = 5.298s``` kertoo kuinka nopeasti virtuaalikone boottasi. 
### 2 `/var/log/auth.log`
Ajoin komennon
    
    sudo cat /var/log/auth.log

valitsin lokin

`Jan 30 21:06:46 pug systemd-logind[477]: New set seat0.`

Ensimmäisenä on päivämäärä ja kellonaika. ```pug``` on tietokoneen nimi.
Loput lokista ilmoittaa, että kirjautumis hallinta käynnistyi onnistuneesti.  ```seat0``` on oletus"seat" systemd:ssä ja se luodaan käynnistyksen yhteydessä.

### 3 `/var/log/apache2/access.log`
`No such file or director` ennenkuin käynnistin apachen komennolla `sudo systemctl start apache2.service`
Vieläkään access.log:issa ei ole mitään ennenkuin avasin selaimesta localhostin ja tein lokeja.
Ajoin komennon

    sudo cat /var/log/apache2/access.log
    
valitsin lokin
    
`127.0.0.1 - - [30/Jan/2023:21:20:18 +0200] "GET /testi123 HTTP/1.1" 404 488 "-" "Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0"`

Ensimmäisenä on IP-osoite (127.0.0.1). Sitten päivämäärä ja aika + aikavyöhyke. Tämän jälkeen mitä käyttäjä kirjoitti (/testi123), jonka perässä 404, koska sivua ei löytynyt. Jonka jälkeen tietoa selaimesta ja käyttäjän käyttöjärjestelmästä. 

### 4 `/var/log/error.log`
Ajoin komennon

    sudo cat /var/log/error.log

valitsin lokin

`[Mon Jan 30 21:18:39.598452 2023] [mpm_event:notice] [pid 913:tid 140693681413440] AH00492: caught SIGWINCH, shutting down gracefully`

Ensimmäisenä on päivämäärä ja kellonaika. ```mpm_event``` ilmoittaa että kyseessä on ```notice``` eli ilmoitus. ```[pid 913...] ``` numerosarja liittyy ilmoituksen tunnistamiseen. ```SIGWINCH``` tarkoittaa SIGNAL WINDOWS CHANGE, eli kun pääte (terminal) havaitsee muutoksen ikkunan koossa, se ilmoittaa siitä ja piirtää sen uudelleen.

## Lokiin kaksi eri tapahtumaa
21:50-22:00

Tein `var/log/apache2/access.log`iin kaksi eri tapahtumaa. Yhden onnistuneen ja yhden epäonnistuneen. 
### Onnistunut 
Kirjoitin selaimeen `localhost/` jolloin avautui onnistuneesti debianin default page ja terminaliin tuli loki 


`127.0.0.1 - - [30/Jan/2023:21:20:13 +0200] "GET / HTTP/1.1" 200 3380 "-" "Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0"`


### Epäonnistunut
Kirjoitin selaimeen `localhost/testi123` jolloin Firefoxissa avautui sivu jossa luki 

    Not Found
    The requested URL was not found on this server
    
Terminaliin tuli tästä tieto, jossa ilmenee virheilmoitus-404.
`127.0.0.1 - - [30/Jan/2023:21:20:18 +0200] "GET /testi123 HTTP/1.1" 404 488 "-" "Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0"`

## Lähteet
https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/#h4-tukki

https://wiki.ubuntu.com/Multiseat

https://stackoverflow.com/questions/780853/what-is-in-apache-2-a-caught-sigwinch-error

