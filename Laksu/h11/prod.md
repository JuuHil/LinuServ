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
10:10
Aloitin päivittämällä paketit ``sudo apt-get update`` ja asensin micro bash texti editorin ``sudo apt-get -y install micro bash-completion`` ja vaihdoin sen ensisijaiseksi tekstieditoriksi ``export EDITOR=micro``

Loin esimerkki sisältöä sivulle

![image](https://user-images.githubusercontent.com/122887067/222375625-90b70d52-e4bb-4f3d-a569-a05cd7b580ac.png)

#### Uusi VirtualHost sudolla.
10:20
Muokkasin tiedostoa komennolla.
``sudoedit /etc/apache2/sites-available/juudj.conf``

![image](https://user-images.githubusercontent.com/122887067/222376887-389a9834-4f03-4a80-8a45-54d9d565cec0.png)

Laitoin uuden configin käyttöön ja otin edellisen pois käytöstä.
10:30
![image](https://user-images.githubusercontent.com/122887067/222378153-acd25020-4fcf-468a-a118-46ac67eae001.png)

Configtestissä tuli erroria DocumentRootista.
10:40
![image](https://user-images.githubusercontent.com/122887067/222379002-534a0bfb-0312-47bc-b0fb-85ca6d46fda6.png)

Confissa oli väärän käyttäjän hakemistot ja Alias puuttui 
![image](https://user-images.githubusercontent.com/122887067/222380166-4271c8b4-1867-40fd-8edc-0c13b9c784a8.png)

![image](https://user-images.githubusercontent.com/122887067/222379049-014adf12-5bbb-4a73-9661-fad8eddb5467.png)

Tarkistin curlilla toimiiko kaikki. 10:50
![image](https://user-images.githubusercontent.com/122887067/222381169-01cc299b-7359-46b1-9c22-21eacdf65ca9.png)

#### Virtualenv
Virtualenvin asennus 11:00

``sudo apt-get -y install virtualenv``

![image](https://user-images.githubusercontent.com/122887067/222382192-878a6eb7-c7d7-456d-9e1d-a8269d5a5569.png)

Aktivoin virtualenvin ja tarkistin missä olen.

![image](https://user-images.githubusercontent.com/122887067/222382448-4c86b9db-a87c-4ac6-864e-1029a2b4dad0.png)

Tein mikrolla tekstitiedoston johon kirjoitin django ja asensin sen. Tarkistin myös minkä version latasin.

![image](https://user-images.githubusercontent.com/122887067/222382926-c708558b-e60c-4d12-95d9-aeadc482e8c7.png)

#### Connect Python to Apache using mod_wsgi

Komennolla ``sudoedit /etc/apache2/sites-available/juudj.conf`` menin muokkaamaan conf tiedosta ja kopion https://terokarvinen.com/2022/deploy-django/ sivulta pohjan ja muokkasin sitä.

![image](https://user-images.githubusercontent.com/122887067/222387695-be74ebcf-550b-41b7-8a6b-6a98e5b48e14.png)

Asensin WSGI moduulin ja tein configtestin.

![image](https://user-images.githubusercontent.com/122887067/222384240-521acbd6-e7d4-41cd-9dc3-de7fd20a58c6.png)

11:10
En saanut sivua toimimaan ja ihmettelen jonkin aikaa ratkaisua.

![image](https://user-images.githubusercontent.com/122887067/222391100-3e436de7-983e-4ba6-8d88-9141b6fc564d.png)

11:45
Ratkaisu löytyi, muistin Teron luennolta rakennusteline keskustelun :) , tein uuden kansion ja tein aikaisemmin tehdyt asiat. Tiivistettynä.

        rm-r juudj/
        django-admin startproject juudj
        sudoedit /etc/apache2/sites-available/juudj.conf
        curl -s localhost|grep title
        
![image](https://user-images.githubusercontent.com/122887067/222393168-cc0c39e5-52fa-4d70-9943-4e1117244ca4.png)

11:50
Tein käyttäjän jolla pääsen kirjautumaan localhosta/admin/

        ./manage.py makemigrations
        ./manage.py migrate
        ./manage.py createsuperuser

Tein käyttäjän
![image](https://user-images.githubusercontent.com/122887067/222395212-133ef18b-941f-4ce0-9bab-fa3f5b4744ab.png)
Otin debugin poist päältä
![image](https://user-images.githubusercontent.com/122887067/222395835-39a60b2f-c297-4625-814c-871f98df10e2.png)
Käynnistin apache2 uudestaan
![image](https://user-images.githubusercontent.com/122887067/222396362-a22de406-6713-41db-9652-6de42dd5427b.png)
12:05 Tyyli kuntoon
![image](https://user-images.githubusercontent.com/122887067/222398373-f44d24fa-17fe-4d07-ab2b-acf7bd13f1e1.png)


## Lähteet

https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/

https://terokarvinen.com/2022/deploy-django/
