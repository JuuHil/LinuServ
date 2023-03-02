# Prod

## Rauta

    Koneen rauta ja käyttöjärjestelmä
    CPU:  i7-13700K 5,4GHz
    RAM:  32GB DDR5 5200Mhz
    GPU:  RTX 3080 OC 10G
    OS:   Windows 10 Pro, Versio 21H2
    
    Versiot. 
    VirtualBox -7.0.6-155176.
    debian-live -11.6.0
    

## a) Djangon tuotantoasennus

Aloitin päivittämällä paketit ``sudo apt-get update`` ja asensin micro bash texti editorin ``sudo apt-get -y install micro bash-completion`` ja vaihdoin sen ensisijaiseksi tekstieditoriksi ``export EDITOR=micro``

Loin esimerkki sisältöä sivulle

![image](https://user-images.githubusercontent.com/122887067/222375625-90b70d52-e4bb-4f3d-a569-a05cd7b580ac.png)

Uusi VirtualHost sudolla.

Muokkasin tiedostoa komennolla.
``sudoedit /etc/apache2/sites-available/juudj.conf``

![image](https://user-images.githubusercontent.com/122887067/222376887-389a9834-4f03-4a80-8a45-54d9d565cec0.png)

Laitoin uuden configin käyttöön ja otin edellisen pois käytöstä.

![image](https://user-images.githubusercontent.com/122887067/222378153-acd25020-4fcf-468a-a118-46ac67eae001.png)

Configtestissä tuli erroria DocumentRootista.

![image](https://user-images.githubusercontent.com/122887067/222379002-534a0bfb-0312-47bc-b0fb-85ca6d46fda6.png)

Confissa oli väärän käyttäjän hakemistot ja Alias puuttui 
![image](https://user-images.githubusercontent.com/122887067/222380166-4271c8b4-1867-40fd-8edc-0c13b9c784a8.png)

![image](https://user-images.githubusercontent.com/122887067/222379049-014adf12-5bbb-4a73-9661-fad8eddb5467.png)

Tarkistin curlilla toimiiko kaikki.
![image](https://user-images.githubusercontent.com/122887067/222381169-01cc299b-7359-46b1-9c22-21eacdf65ca9.png)

#### Virtualenv

## Lähteet

https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/

https://terokarvinen.com/2022/deploy-django/
