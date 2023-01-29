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
20:00-20:
### 1 `/var/log/syslog`
Jan 29 20:00:28 pug systemd[1]: Startup finished in 3.905s (kernel) + 1.393s (userspace) = 5.298s

### 2 `/var/log/auth.log`

### 3 `/var/log/access.log`

### 4 `/var/log/error.log`

