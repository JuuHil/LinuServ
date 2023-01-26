### Tiivistelmä
- Komentoja hakemistoissa liikkumiseen. 
- Tärkeitä hakemistoja.
- Admin komentoja.

https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited

## Rauta

    Koneen rauta ja käyttöjärjestelmä
    Intel i7-13700K 5,4GHz
    Corsair Vengeance 32GB DDR5 5200Mhz
    Strix GeForce RTX 3080 OC 10G
    Windows 10 Pro, Versio 21H2
    
    Versiot. 
    VirtualBox -7.0.6-155176.
    debian-live -11.6.0

## Tehtävät 
![Tehtävänanto](https://user-images.githubusercontent.com/122887067/214021140-d4ef2081-3470-4de4-a9ee-67ef6dd64938.png)

### Micro-editor
10:35-10:40 Avasin terminalin 

      sudo apt-get install micro
      
![Kuva-1](t1.png)

### Koneen rauta
10:40-10:45. Asensin lshw:n komennolla

    sudo apt-get install lswh

![Kuva-2](t2.png)

    
    sudo lshw -short -sanitize
    
komento listaa virtuaalikoneen käyttössä olevat komponentit, annoin virtuaalikoneelle käyttöön  4GB muistia ja sekin näkyy 


![Kuva-3](t3.png)



### Apt. Asenna kolme itsellesi uutta komentoriviohjelmaa. 
11:00-11:20
#### Cowsay 
Asensin cowsay:n komennolla

      sudo apt-get install cowsay
      
      
![Kuva-4](t4.png)
cowsay
![Kuva-5](t5.png)

#### Tree hakemistopuu
Asensin tree ohjelman komennolla

     
      sudo apt-get install tree
      
      
![Kuva-6](t6.png)
tree tekee yksinkertaisen hakemistopuun
![Kuva-7](t7.png)

#### Nano text editor
Asensin nano ohjelman komennolla

      sudo apt-get install nano
      
![Kuva-8](t8.png)
Nano on yksinkertainen tekstieditori
![Kuva-9](t9.png)

### FHS. Esittele "Important directories" kansiot.
11.45-12.00

            ls /
            
Juurihakemisto, tiedostojärjestelmän yläosa.
            
            ls /home/
            
Kotihakemistot kaikille käyttäjille.
            
            ls /home/juuhil/

Käyttäjän "juuhil" kotihakemisto.           
            
            ls /etc/
           
Järjestelmän laajuiset asetukset.

![Kuva-10](t10.png)

            ls /media/

Irotettavat mediat. Esim usbtikku

            ls /var/log/
            
Järjestelmänlaajuiset lokit.
![Kuva-11](t11.png)

### Grep komento.
12.00-12.30
Grep komennolla voi etsiä erilaisia merkkijonoja.
Esimerkki 1. 

![Kuva-12](https://user-images.githubusercontent.com/122887067/214014185-86fc0e8d-4803-4bf8-8acc-174dfeac1ea8.png)

Haen "hostnamectl" tiedostosta sanaa "kernel". -i ennen kernel:iä etsii isolla tai pienellä kirjoitettua. 

Esimerkki 2.

![Kuva-13](https://user-images.githubusercontent.com/122887067/214020092-090d35d9-7c9a-4bd9-b1f6-e3090f714fc9.png)

Etsin linus.txt tiedostosta sanoja missä on t kirjain. Niitä löytyi 5.

