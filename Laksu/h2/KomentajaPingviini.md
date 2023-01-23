### Tiivistelmä
- Komentoja hakemistoissa liikkumiseen. 
- Tärkeitä hakemistoja.
- Admin komentoja.
https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited
## Tehtävät 
Asenna micro-editori
Listaa testaamasi koneen rauta, asenna lshw tarvittaessa ja selitä ja analysoi listaus.
Apt. Asenna kolme itsellesi uutta komentoriviohjelmaa. Kokeile kutakin ohjelmaa.

### Micro-editor
10:35-10:40 Avasin terminalin 

      sudo apt-get install micro
      
![Kuva-1](t1.png)

### Koneen rauta
10:40-10:45. Asensin lshw:n komennolla

    sudo apt-get install lswh

![Kuva-2](t2.png)

    
    sudo lshw -short -sanitize
    
komento listaa virtuaali koneen käyttössä olevat komponentit.


![Kuva-3](t3.png)

### Apt. Asenna kolme itsellesi uutta komentoriviohjelmaa. 
11:00-11:20
#### Cowsay 
Asensin cowsay:n komennolla

      sudo apt-get install cowsay
      
      
![Kuva-4](t4.png)
cowsay
![Kuva-5](t5.png)

#### Tree hakemistopuu
Asensin tree ohjelman komennolla

     
      sudo apt-get install tree
      
      
![Kuva-6](t6.png)
tree tekee yksinkertaisen hakemistopuun
![Kuva-7](t7.png)

#### Nano text editor
Asensin nano ohjelman komennolla

      sudo apt-get install nano
      
![Kuva-8](t8.png)
Nano on yksinkertainen tekstieditori
![Kuva-9](t9.png)

### FHS.
