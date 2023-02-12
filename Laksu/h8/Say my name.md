# Say my name

## Tehtävät
![image](https://user-images.githubusercontent.com/122887067/218321807-d71d6934-c3c6-4e55-855e-950d6dffa348.png)

## Rauta

    Koneen rauta ja käyttöjärjestelmä
    CPU:  i7-13700K 5,4GHz
    RAM:  32GB DDR5 5200Mhz
    GPU:  RTX 3080 OC 10G
    OS:   Windows 10 Pro, Versio 21H2
    
    Versiot. 
    VirtualBox -7.0.6-155176.
    debian-live -11.6.0

## Vuokraa domainnimi ja aseta se osoittamaan virtuaalipalvelimeesi.* 
18.00-18.05
Minulla oli jo ennestään domaini ostettuna https://www.zone.ee/en/ sivulta.

Kirjauduin sivulle ja kävin lisäämässä virtuaalipalvelimen ip-osoitteen.

![image](https://user-images.githubusercontent.com/122887067/218322346-7894bcdf-bdd4-4d9e-ab20-229704990f65.png)

![image](https://user-images.githubusercontent.com/122887067/218321995-5d3bac76-0080-4a80-ab72-b5e51a2d4e8d.png)

http://klog.fi/

## Tutki oman nimesi tietoja 'host' ja 'dig' -komennoilla. Analysoi tulokset.
18.05-18.20

![image](https://user-images.githubusercontent.com/122887067/218322409-a0ecdcdf-3162-44f9-8d7b-b5a2cc83792d.png)

host komento kertoo vain sivun ip-osoitteen minun sivulla.

![image](https://user-images.githubusercontent.com/122887067/218322604-c8cf4bde-3476-4b28-b97e-d47093dc45ba.png)

Asensin dig komennon, koska se puuttui.

    sudo apt-get install dnsutils

![image](https://user-images.githubusercontent.com/122887067/218322691-a416c5e3-df61-4e6c-885d-618a197e79e4.png)

"ANSWER SECTION"issa lukee www-osoite, 3600 joka on Time to Live, IN = internet, A = DNS tietueen tyyppiä ja palvelimen ip-osoite 139.144.71.210

"Query time" kertoo, että vastauksen saamiseen kesti 4 millisekunttia

"WHEN" kertoo milloin kysely tehtiin. Sunnuntai Helmiku 12.päivä kello 18:12:18 Eastern European Time (+2) Vuonna 2023
## Lähteet

https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/

https://www.zone.ee/en/

https://phoenixnap.com/kb/linux-dig-command-examples
