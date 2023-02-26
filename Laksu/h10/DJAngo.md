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
    
Loin ``requirements.txt`` tiedoston, jossa määritin mitä paketteja asennettaan, kirjoitin .txt tiedoston sisään ``django``.

    micro requirements.txt
    pip install -r requirements.txt
    
Tein juudj projektin/webbisiten ja laitoin sen päälle.

    django-admin startproject juudj
    cd juudj/
    ./manage.py runserver # NOT FOR PROD

Ja se käynnistyi. 
![image](https://user-images.githubusercontent.com/122887067/221423559-c238cd67-25cd-4b10-b3f5-3dc4370290db.png)

    
 
