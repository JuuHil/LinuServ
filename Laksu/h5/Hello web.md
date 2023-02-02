# Hello web

## Tehtävät
![hwork](https://user-images.githubusercontent.com/122887067/216271052-69745423-eb54-4218-9395-ed9ce29d8fb4.png)

## Rauta

    Koneen rauta ja käyttöjärjestelmä
    CPU:  i7-13700K 5,4GHz
    RAM:  32GB DDR5 5200Mhz
    GPU:  RTX 3080 OC 10G
    OS:   Windows 10 Pro, Versio 21H2
    
    Versiot. 
    VirtualBox -7.0.6-155176.
    debian-live -11.6.0

## Tiivistelmä 10:00-11:00
Kuuntelin Indie Hackers podcastin uusimman jakson "#266 – Lessons Learned Building a $37k/mo Business in 2.5 Years with Mat De Sousa of WideBundle"
https://share.transistor.fm/s/940ae75e

- Jakso kertoo Mat De Sousan:n epäonnistuneista ja onnistuneista starupeista. 
- Sousan mukaan ei tarvitse olla paras, kunhan pystyy luomaan edes jotain, mikä on muille ihmisille hyödyllistä.
- Shopify on alustana hyvä, koska se on jo käyttäjien luottama alusta. 
- Sousan aloitti monet startuppinsa palautteen pohjalta, mitä käyttäjät antoivat hänen luonnoksista ja ideoistaan.

## Esimerkkisivu
11:10-11:20
Vaihdoin esimerkki sivun lyhyeen sivuun. 
Ensiksi menin oikeaan kansioon komennolla.

    cd /var/www/html
    
Josta avasin `index.html` tiedoston ja muokkasin sitä komennolla    
    
    sudo micro index.html
    
![sudolocal](https://user-images.githubusercontent.com/122887067/216282328-8ca30f8b-2248-4412-96f0-f849f0940efe.png)

Nyt localhost etusivu näyttää tältä. 

![local](https://user-images.githubusercontent.com/122887067/216282400-7302a0fe-b612-4c56-b2dc-707d8ea2bdc7.png)

## Käyttäjien kotisivut
11:20-11:30
Menin käyttäjäni public_html kansioon komennolla.

    cd /home/juuhil/public_html/
    
ja loin sinne index.html nimisen tiedoston komennolla.

    sudo micro index.html
    
![sudojuuhil](https://user-images.githubusercontent.com/122887067/216285576-6f679c24-588a-41c8-bead-a5923759cf4f.png)

Nyt `localhost/~juuhil` näyttää tältä.

![juuhil](https://user-images.githubusercontent.com/122887067/216285965-24073487-edca-431f-918b-aa27b9b49850.png)

   
## Uusi käyttäjä
11:30-11:50

Aloitin komennolla

    sudo adduser hilt
    
![image](https://user-images.githubusercontent.com/122887067/216287208-6992c7aa-cdf9-49e0-a1d4-bae9c4df0015.png)

Uusi käyttäjä on nyt luotu.

![image](https://user-images.githubusercontent.com/122887067/216287825-c0ec8d65-11e7-4a20-b96a-cc160b1f3a90.png)

Vaihdoin käyttäjää ja annoin salasanan. su = switch user

![image](https://user-images.githubusercontent.com/122887067/216288125-f37f8fe6-328e-4e3e-95d7-f73c8088f6f2.png)

Tein uudelle käyttäjälle kotisivun. 

![hilthome](https://user-images.githubusercontent.com/122887067/216291460-2e62e0b8-e943-4a80-92ba-1c645b969876.png)

Jos oikein ymmärsin tätä sivua ei tarvinnut vaihtaa.
 
## Validi HTML5 sivu
11:50-12:05
Vaihoin takaisin pääkäyttäjälleni.
Siirryin public_html kansioon komennolla
    
    cd /home/juuhil/public_html

Muokkasin aiemmin tehtyä index.html komennolla

    micro index.html

Nyt käyttäjän kotisivu näyttää tältä.

![image](https://user-images.githubusercontent.com/122887067/216294673-d9a273c5-8594-4c5e-b530-aa440f5e1c14.png)

Validor sanoi, että `Document checking completed. No errors or warnings to show.`

![validi](https://user-images.githubusercontent.com/122887067/216294399-20baaa16-5e64-4e9b-8a55-a01a2d4c1bbe.png)

## Yhteenveto
Tehtävien tekoon meni 10:00-12:10
Erityisiä vaikeuksia ei ollut.

## Lähteet
https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/
https://www.indiehackers.com/podcasts
https://www.freecodecamp.org/news/basic-html5-template-boilerplate-code-example/
https://unix.stackexchange.com/questions/3568/how-to-switch-between-users-on-one-terminal
