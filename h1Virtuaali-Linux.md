### Virtuaali Linux
Tein harjoituksen 18.1.2023.

        Koneen rauta ja käyttöjärjestelmä
        Intel i7-13700K 5,4GHz
        Corsair Vengeance 32GB DDR5 5200Mhz
        Strix GeForce RTX 3080 OC 10G
        Windows 10 Pro, Versio 21H2
        
        Versiot. 
        VirtualBox -7.0.6-155176.
        debian-live -11.6.0
        

### 1. Lataa VirtualBox
https://www.virtualbox.org/wiki/Downloads > Windows hosts.

VirtualBoxin setupista, Next, Next, Yes, Yes, Install, Finish. 

### 2. Lataa Debian GNU/Linux.
https://cdimage.debian.org/images/unofficial/non-free/images-including-firmware/current-live/amd64/iso-hybrid/

Debianin sivulta 3. Alin vaihtoehto "debian-live-11.6.0-amd64-xfce+nonfree.iso".

### 3. VirtualBox käyttöön
Avaa VirtualBox ja paina "New"

![Kuva-1](vbyks.png) 

Nimeä Virtuaali kone. Valitse aiemmin ladattu Debian.iso tiedosto ISO IMAGE kohtaan.
"Next"

![Kuva-2](vbkaks.png)

Vaihda username ja password.
"Next"

![Kuva-3](vbkolme.png) 

Laita Base Memory kohtaan 4G=4096 MB RAM:ia.
"Next"

![Kuva-4](vbnelja.png)

Laita Disk Size 60 GB
"Next"

Viimeiseen kohtaan paina "Finish"

### 4. Debianin Asennus

VirtualBoxin pitäisi aukaista itsestään juuri luotu virtuaalikone. 
Jos virtuaalikone ei ole auki, valitse VirtualBox Managerista juuri luotu virtuaalikone ja "Start"

Valitse työpöydältä "Install Debian" ja avaa se

db1.png

- Welcome sivulta American English ja "Next".
- Location sivulta Helsinki tai missä ikinä oletkaan ja "Next".
- Keyboard sivulta Finnish ja Default ja "Next".
- Partitions sivulta. Erase disk ja "Next".
- Users sivulle täytä tiedot. Computer Name kohtaan älä laita omaa nimeäsi tai mitään muuta josta sinua voitaisiin tunnistaa. "Next"  
db2.png 

- Summary, jos alapalkki katoaa laita Installer kokoruudulle ja "Install"
- Install kestää jonkin aikaan. 

