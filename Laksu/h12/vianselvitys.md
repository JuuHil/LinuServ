# Vianselvitys

## Tehtävät
![image](https://user-images.githubusercontent.com/122887067/222975909-6a9a3e50-3eda-4a77-a33b-3eea0448826c.png)


## Rauta

    Koneen rauta ja käyttöjärjestelmä
    CPU:  i7-13700K 5,4GHz
    RAM:  32GB DDR5 5200Mhz
    GPU:  RTX 3080 OC 10G
    OS:   Windows 10 Pro, Versio 21H2
    
    Versiot. 
    VirtualBox -7.0.6-155176.
    debian-live -11.6.0

### b) Django-projektikansio väärässä paikassa (siis se, jossa on manage.py)

21:45-22:05

Alkutilanne

![image](https://user-images.githubusercontent.com/122887067/222976341-02f37186-3b0e-401a-83c3-184d0803206e.png)

Siirsin projektikansion pois /publicwsgi alta.

![image](https://user-images.githubusercontent.com/122887067/222976872-46be1457-8872-4cde-a11f-7916492802c9.png)
![image](https://user-images.githubusercontent.com/122887067/222976889-9e8bee8e-f247-4678-9083-7ba23e80f429.png)

Sivu antaa nyt forbiddeniä.

![image](https://user-images.githubusercontent.com/122887067/222976913-08f0f8ce-7484-4b84-88f2-21307529325a.png)

Siirsin projektikansion takaisin ``/home/juuhil/publicwsgi/juudj``
Nyt sivu toimii jälleen. 

![image](https://user-images.githubusercontent.com/122887067/223056701-0980bc56-7c68-46b3-95f4-4941d6bda2c1.png)


### c) Projektikansiolla väärät oikeudet ('chmod ugo-rwx teroco/', 'chmod u+rx teroco/')
22:05-22:30

Otin rwx (read, write, execute) pois käytöstä. 
Kokeilen runserver, mutta sain paljon virheilmoituksia

![image](https://user-images.githubusercontent.com/122887067/222984802-4dfe668d-757b-4a16-a9bf-08485adf085a.png)

Annoin oikeudet takaisin

![image](https://user-images.githubusercontent.com/122887067/222984888-e4e4aa5d-08c6-4809-af76-8096092af0b0.png)

Loputilanne

![image](https://user-images.githubusercontent.com/122887067/222989025-32e7844b-88d1-48ed-9abe-5c05b3f8faaf.png)

### d) Kirjoitusvirhe Apachen asetustiedostossa (/etc/apache2/sites-available/terokarvinen.conf tms)
10:00-10:15

Kävin muokkaamassa TDIR /etc/apache2/sites-available/juu50

![image](https://user-images.githubusercontent.com/122887067/223055910-2d473d30-1894-4003-beb9-b32385429960.png)
Käynnistin apachen uudestaan komennolla

        sudo systemctl restart apache2
        
Sivu antoi forbiddeniä        
![image](https://user-images.githubusercontent.com/122887067/223053687-6910baae-0567-49eb-bbc4-1a37ad44dd15.png)

Kävin poistamassa # ja ajoin ``sudo systemctl restart apache2``

Lopputilanne, kaikki toimii jälleen.

![image](https://user-images.githubusercontent.com/122887067/223054054-a0ec8b7f-c5eb-4bf3-a4fe-a723acd3d417.png)

### e) Apachen WSGI-moduli puuttuu ('sudo apt-get purge libapache2-mod-wsgi-py3' tms)
10:15-10:30

Menin projekti kansioon ja poistin ``libapache2-mod-wsgi-py3``
![image](https://user-images.githubusercontent.com/122887067/223055237-018d2003-3db0-408e-924c-6259ea664ab2.png)

Yritin käynnistää apache2 uudestaan, mutta se ei onnistunut

![image](https://user-images.githubusercontent.com/122887067/223055407-0fb0594b-16df-4d56-ac2f-9c1b03d4d586.png)

Asensin ``libapache2-mod-wsgi-py3`` takaisin komenolla

``sudo apt-get install libapache2-mod-wsgi-py3``

Lopputilanne, sivu toimii jälleen.

![image](https://user-images.githubusercontent.com/122887067/223057563-8b01bc24-6a5b-467f-bc61-9556644f3c22.png)

### a) Kirjoitusvirhe Python-tiedostossa f) Väärät domain-nimet ALLOWED_HOSTS-kohdassa (settings.py, ja DEBUG=False)
10:30-10:55

Menin ``setting.py`` tiedostoon ja muokkasin ``ALLOWED_HOSTS`` kohtaa.

![image](https://user-images.githubusercontent.com/122887067/223057912-8c001f76-8e79-4dba-8238-642491cb0cbc.png)

Käynnistin apachen uudestaan

``sudo systemctl restart apache2``

Avasin selaimen ja sain ``Bad Request 400``

![image](https://user-images.githubusercontent.com/122887067/223058296-5fb8fb00-3ea6-46ae-b87a-5c40e4b41485.png)

Kävin muokkamassa ``settings.py`` tiedoston kuntoon ja käynnistin apachen uudelleen, nyt sivu toimii taas.


## Lähteet
https://terokarvinen.com/2022/deploy-django/

https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/

