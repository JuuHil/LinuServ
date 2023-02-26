# DJ Ango

## Tehtävät

![image](https://user-images.githubusercontent.com/122887067/221422325-a22ef7dd-367e-4e7f-8d4c-d7fff86988d3.png)

## Rauta

    Koneen rauta ja käyttöjärjestelmä
    CPU:  i7-13700K 5,4GHz
    RAM:  32GB DDR5 5200Mhz
    GPU:  RTX 3080 OC 10G
    OS:   Windows 10 Pro, Versio 21H2
    
    Versiot. 
    VirtualBox -7.0.6-155176.
    debian-live -11.6.0
    
## Tietokantasovellus
18:20
Asensin ``virtualenv``in ja valitsin minkä nimiseen kansioon env laitetaan.

    sudo apt-get update
    sudo apt-get install virtualenv python3-pip
    mkdir django
    cd django/
    virtualenv -p python3 env/
    virtualenv -p python3 --system-site-packages env/
    ls

Laitoin sen käyntiin komennolla

    source env/bin/activate
    
18:30 

Loin ``requirements.txt`` tiedoston, jossa määritin mitä paketteja asennettaan, kirjoitin .txt tiedoston sisään ``django``.

    micro requirements.txt
    pip install -r requirements.txt
    
Tein juudj projektin/webbisiten ja laitoin sen päälle.

    django-admin startproject juudj
    cd juudj/
    ./manage.py runserver # NOT FOR PROD

Ja se käynnistyi. 
![image](https://user-images.githubusercontent.com/122887067/221423559-c238cd67-25cd-4b10-b3f5-3dc4370290db.png)

18:40

Avasin uuden terminalin ja menin takaisin (env) juuhil@pug:~/django/juudj
Päivitin tietokannat

    ./manage.py makemigrations
    ./manage.py migrate

Tein käyttäjän juuhil

    ./manage.py createsuperuser

![image](https://user-images.githubusercontent.com/122887067/221424175-5d501767-0298-4355-b09a-f0ec215a3a0f.png)

18:50
Loin mallin johon DJAngo pystyy tehdä tietokannan

    ./manage.py startapp products

Lisäsin asennettujen sovellusten listaan juuri luodun ``products``

    micro juudj/settings.py
    
![image](https://user-images.githubusercontent.com/122887067/221424592-8c0cfc04-cf40-4105-8efc-52de5ac5368d.png)

19:00

Tein tauluja johon voi lisätä tuotteiden nimen, hinnan ja kuvauksen

    micro products/models.py
  
![image](https://user-images.githubusercontent.com/122887067/221425183-5212e01a-2e1b-4fc7-993e-c245dd2035bf.png)

19:10

Päivitin tietokannat.
   
    ./manage.py makemigrations
    ./manage.py migrate

Rekisteröin tietokannan

    micro products/admin.py
    
![image](https://user-images.githubusercontent.com/122887067/221425039-59d0494d-e030-4659-82d9-de214441d00c.png)

19:15

Yhteenveto, kaikki toimivat hyvin ja nyt pystyn lisätä tuotteita listaan.

![image](https://user-images.githubusercontent.com/122887067/221425458-65caa528-d8e4-4183-9da7-919a678092f1.png)

![image](https://user-images.githubusercontent.com/122887067/221425548-2ea9f340-135d-4179-ae50-22fc721155dd.png)
