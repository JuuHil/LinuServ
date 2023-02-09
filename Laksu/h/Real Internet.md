# Real Internet

## Tehtävät
![image](https://user-images.githubusercontent.com/122887067/217754218-572b9ce0-27e1-4e02-bf2a-cc4c4c8fa772.png)


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
https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/


## Virtuaalipalvelimen vuokraus
10:20-10:55
Vuokrasin virtuaapalvelimen https://www.linode.com/ sivuilta. Kirjauduin sisään ja loin virtuaalipalvelimen.
Asetuksiin valitsin
- Distribution: Debian 11
- Region: Frankfurt 
- Linode Plan: Nanode 1 GB
   - 1 CPU
   - 1 GB RAM
   - 1 TB Transfer
   - 40 Gbps In / 1 Gbps Out
Asetin root salasanan ja SSH Keyn.
SSH Keyn saa komennoilla

      ssh-keygen -t rsa
      
      cd /home/juuhil/.ssh
      
      micro id_rsa.pub
    
## Alkutoimet virtuaalipalvelimella
Yhdistin virtuaalipalvelimelle komennolla

    ssh root@139.144.71.210
    
Ensiksi päivitin pakeit 

       sudo apt-get update
  
ja
  
       sudo apt-get upgrade
       
Asensin muutaman ohjelman komennolla  `sudo apt-get install x`, asensin micron, ufw ja apache2.

Ennenkuin käynnistin palomuurin tein itselleni reiän, jotta pääsen vielä itse kirjautumaan sisään

    sudo ufw allow 22/tcp
    
ja 

    sudo ufw allow 80/tcp
   
Sitten laitoin palomuurin päälle 

    sudo enable ufw

## Weppipalvelimen asennus
10:55-11:10

Asensin apachen alkutoimissa ja päästin sen palomuurin läpi joten se toimii jo, kun sen käynnistää komennolla

    sudo systemctl start apache2
    
Nyt sivu näkyy, mutta siellä on vielä apachen "default page". 

    cd /var/www/html
    micro index.html

![image](https://user-images.githubusercontent.com/122887067/217767641-fc8d0fd7-4b81-4237-997d-fa988b329be6.png)

## Murtautumisyrityksiä
11:17-11:30

Menin katsomaan /var/log/auth.log

auth.logista lyötyi paljon failed password 

![image](https://user-images.githubusercontent.com/122887067/217772413-9cae29ca-4008-4cb8-9a34-86164a0ffc09.png)

69.50.138.96 osoitteesta tuli 26 "Failed password for ..." yritystä jonka jälkeen uudet 26 "Connection closed by invalid ..."
Kaikki nämä yritykset tapahtui samalla sekunnilla 8:58:05. Hän yritti myös eri porteista.
## Lähteet

https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/

https://www.linode.com/

https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/




