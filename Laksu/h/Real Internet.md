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
  
  sudo apt-get upgrade
  
## Weppipalvelimen asennus

## Murtautumisyrityksiä

## Lähteet
https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/



