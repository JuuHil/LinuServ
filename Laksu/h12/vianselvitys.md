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
    
### a) Kirjoitusvirhe Python-tiedostossa
![image](https://user-images.githubusercontent.com/122887067/222976341-02f37186-3b0e-401a-83c3-184d0803206e.png)

![image](https://user-images.githubusercontent.com/122887067/222976323-7890ad1e-4ed8-4621-8ae3-28a0955bd98a.png)

### b) Django-projektikansio väärässä paikassa (siis se, jossa on manage.py)

21:45-22:05

Alkutilanne

![image](https://user-images.githubusercontent.com/122887067/222976341-02f37186-3b0e-401a-83c3-184d0803206e.png)

Siirsin projektikansion pois.

![image](https://user-images.githubusercontent.com/122887067/222976872-46be1457-8872-4cde-a11f-7916492802c9.png)
![image](https://user-images.githubusercontent.com/122887067/222976889-9e8bee8e-f247-4678-9083-7ba23e80f429.png)

Lopputulos

![image](https://user-images.githubusercontent.com/122887067/222976913-08f0f8ce-7484-4b84-88f2-21307529325a.png)

Siirsin projektikansion takaisin ``/home/juuhil/publicwsgi/juudj``

### c) Projektikansiolla väärät oikeudet ('chmod ugo-rwx teroco/', 'chmod u+rx teroco/')
22:05-22:30

Otin rwx (read, write, execute) pois käytöstä. Ja sain paljon virheilmoituksia

![image](https://user-images.githubusercontent.com/122887067/222984802-4dfe668d-757b-4a16-a9bf-08485adf085a.png)

Annoin oikeudet takaisin

![image](https://user-images.githubusercontent.com/122887067/222984888-e4e4aa5d-08c6-4809-af76-8096092af0b0.png)

Loputilanne

![image](https://user-images.githubusercontent.com/122887067/222989025-32e7844b-88d1-48ed-9abe-5c05b3f8faaf.png)

### d) Kirjoitusvirhe Apachen asetustiedostossa (/etc/apache2/sites-available/terokarvinen.conf tms)
10:00-10:15

![image](https://user-images.githubusercontent.com/122887067/223052712-b7418710-4928-4a95-9f72-2ca1860bb4ca.png)

        sudo systemctl restart apache2
        
![image](https://user-images.githubusercontent.com/122887067/223053687-6910baae-0567-49eb-bbc4-1a37ad44dd15.png)

Kävin poistamassa # ja ajoin ``sudo systemctl restart apache2``

Lopputilanne

![image](https://user-images.githubusercontent.com/122887067/223054054-a0ec8b7f-c5eb-4bf3-a4fe-a723acd3d417.png)

### e) Apachen WSGI-moduli puuttuu ('sudo apt-get purge libapache2-mod-wsgi-py3' tms)

![image](https://user-images.githubusercontent.com/122887067/223055237-018d2003-3db0-408e-924c-6259ea664ab2.png)

![image](https://user-images.githubusercontent.com/122887067/223055407-0fb0594b-16df-4d56-ac2f-9c1b03d4d586.png)

``sudo apt-get install libapache2-mod-wsgi-py3``

### f) Väärät domain-nimet ALLOWED_HOSTS-kohdassa (settings.py, ja DEBUG=False)


