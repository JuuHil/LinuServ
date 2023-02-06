# Hello web

## Tehtävät
![hwork](https://user-images.githubusercontent.com/122887067/216919650-f0db593e-ee6f-43d5-8308-da867e8dc954.png)


## Rauta

    Koneen rauta ja käyttöjärjestelmä
    CPU:  i7-13700K 5,4GHz
    RAM:  32GB DDR5 5200Mhz
    GPU:  RTX 3080 OC 10G
    OS:   Windows 10 Pro, Versio 21H2
    
    Versiot. 
    VirtualBox -7.0.6-155176.
    debian-live -11.6.0

## Lue ja tiivistä

## Apachelle uusi etusivu
 10:20-11:20

Menin apachen kansioon kirjoittamalla komennon

    cd /etc/apache2/sites-available

Loin kansion ja muokkasin sitä

    sudoedit frontpage.conf

![image](https://user-images.githubusercontent.com/122887067/216923722-37b0b07c-5a38-459a-8d4b-e6851af92de8.png)

Laitoin uuden sivun päälle (frontpage) ja sammutin vanhan (000-default) komennoilla

    sudo a2ensite frontpage.conf
    sudo a2dissite 000-default.conf


![image](https://user-images.githubusercontent.com/122887067/216923428-1ecd14fe-eec9-462a-a6c1-3d3b0efd2476.png)

Tämän jälkeen käynnistin apachen uudestaan komennolla

    sudo systemctl restart apache2

Sivu antoi "Forbidden"

![image](https://user-images.githubusercontent.com/122887067/216924339-08860e87-ac97-4a64-9731-3ce66f78b221.png)

/home/juuhil/public_sites kansiota ei ollut, joten kävin luomassa sellaisen ja lisäsin sinne index.html tiedoston

    mkdir public_sites
    micro index.html
    
![image](https://user-images.githubusercontent.com/122887067/216926913-cbcc1ae1-7789-4e38-9051-ad96d8e5a52d.png)

Vaihdetaan käyttäjä ja testataan.

    su hilt
    cd /home/juuhil/public_sites
    micro index.html
    
![image](https://user-images.githubusercontent.com/122887067/216929601-f05cf6a0-3e6a-4cd1-b002-7dae3ed4698c.png)

Permission denied.
Muokkasin frontpage.conf

![image](https://user-images.githubusercontent.com/122887067/216930417-83bb3782-9749-4cb1-8a32-dca50265b1db.png)

ja toisen käyttäjän public_site index.html tiedostoa

![image](https://user-images.githubusercontent.com/122887067/216932339-27e3336d-a8a1-4e3f-a290-591713441746.png)

Kirjauduin takaisin pääkäyttäjällä ja käynnistin apachen uudestaan ja toimii.

![image](https://user-images.githubusercontent.com/122887067/216932550-882b0f50-8e69-4f0f-9a66-d18a660b612a.png)


    
## Kirjoitusvirhe
Kävin luomassa kirjoitusvirheen /etc/apache/sites-available/frontpage.conf tiedostoon. 
Poistin pari kirjainta 
![image](https://user-images.githubusercontent.com/122887067/216933875-3f705e0e-af32-4d2b-9854-6c493009637a.png)


## Lähteet
https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/
