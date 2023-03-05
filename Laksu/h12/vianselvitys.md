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
Alkutilanne

![image](https://user-images.githubusercontent.com/122887067/222976341-02f37186-3b0e-401a-83c3-184d0803206e.png)

Siirsin projektikansion pois.

![image](https://user-images.githubusercontent.com/122887067/222976872-46be1457-8872-4cde-a11f-7916492802c9.png)
![image](https://user-images.githubusercontent.com/122887067/222976889-9e8bee8e-f247-4678-9083-7ba23e80f429.png)

Lopputulos

![image](https://user-images.githubusercontent.com/122887067/222976913-08f0f8ce-7484-4b84-88f2-21307529325a.png)

Siirsin projektikansion takaisin ``/home/juuhil/publicwsgi/juudj``

### c) Projektikansiolla väärät oikeudet ('chmod ugo-rwx teroco/', 'chmod u+rx teroco/')

![image](https://user-images.githubusercontent.com/122887067/222984802-4dfe668d-757b-4a16-a9bf-08485adf085a.png)

![image](https://user-images.githubusercontent.com/122887067/222984888-e4e4aa5d-08c6-4809-af76-8096092af0b0.png)

![image](https://user-images.githubusercontent.com/122887067/222989025-32e7844b-88d1-48ed-9abe-5c05b3f8faaf.png)


### d) Kirjoitusvirhe Apachen asetustiedostossa (/etc/apache2/sites-available/terokarvinen.conf tms)

### e) Apachen WSGI-moduli puuttuu ('sudo apt-get purge libapache2-mod-wsgi-py3' tms)

### f) Väärät domain-nimet ALLOWED_HOSTS-kohdassa (settings.py, ja DEBUG=False)


