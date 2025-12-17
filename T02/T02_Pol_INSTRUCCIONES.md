# T02: Còpies de Seguretat amb Duplicati (Windows) i Duplicity (Linux)



#### 

## Configuració i còpies de seguretat a Windows amb Duplicati
Aqui tenim les especificacions de la maquina Windows 11.
  ![](img/image1.png)   
Instalarem Duplicati.
Obrirem Duplicati i ens sortirà una finestra al nostre navegador predeterminat, dins la finestra li donarem ara no gràcies.
  ![](img/image2.png)  
Li donarem a add en backups.
  ![](img/image3.png)  
Donarem a Add a new Backup.
  ![](img/image4.png)  
Aqui farem la configuracio general de la copia de seguretat com el nom del backup la seva descripcio i el seu xifrat i asignarem una contrasenya a la copia.
  ![](img/image5.png)  
En el desti de on vulem que sigui el nostre backup posarem la file system per que volem la copia al nostre propi sistema.
  ![](img/image6.png)  
Seleccionarem on volem que vagi la nostra copia de seguretat i li donarem continue.
  ![](img/image7.png)  
Li donarem a skip test.
  ![](img/image8.png)  
Ara podrem seleccionar a que li volem fer el backup una vegada seleccionat a que li volem fer backup donarem continue.
  ![](img/image9.png)  
Aqui podrem seleccionar cada quant volem fer la copia de seguretat i desde quant comença a fer les copies, en aquest cas cada hora i començara el 9 a les 20:00.
  ![](img/image10.png)  
Aqui podrem seleccionar en quants archius volem que sigui feta la copia de seguretat.
  ![](img/image11.png)  
  ![](img/image12.png)  
una vegada acabat tot ens sortira la seguent finestra mostrant que s’ha creat el backup correctament.
  ![](img/image13.png)  
Per fer la copia de seguretat al nuvol (Google drive) tornarem a repetir el process fins el apartat de desti del backup.
  ![](img/image14.png)  
  ![](img/image15.png)  
  ![](img/image16.png)  
Aqui en comptes de posar file system li donarem a google Drive.
  ![](img/image17.png)  
Una vegada li donem a google drive li donarem a AuthID i fem login amb Google.
  ![](img/image18.png)  
  ![](img/image19.png)  
Aceptarem els termes de duplicat.
  ![](img/image20.png)  
Posarem la ruta del nostre google drive on volem que vagi el nostre backup.
  ![](img/image21.png)  
Posarem de que carpeta volem que es fagi el backup i donarem continuar.
  ![](img/image22.png)  
Configurarem la hora i el dia en aquest cas volem que es fagi cada dia a les 18:00.
  ![](img/image23.png)  
A la part de opcions deixarem les opcions default.
  ![](img/image24.png)  
Com podem veure tenim els 2 backups els del disc local D: i els de Google Drive.
  ![](img/image25.png)  
Per fer la comprovacio que funciona correctament la copie de segureta local del disc D esborrarem el contingut de la carpeta documents.
  ![](img/image26.png)  
  ![](img/image27.png)  
Li donarem a Restaurar.
  ![](img/image28.png)  
Restaurarem desde la copia de seguretat local.
  ![](img/image29.png)  
Li donarem a continue.
  ![](img/image30.png)  
Ens preguntara a on volem restaurar els arxius i posarem a la seva posició original i que sobreescrigui els arxius a dins de la carpeta.
  ![](img/image31.png)  
.
Una vegada li donem submit restaurarem tot.
  ![](img/image32.png)  
Farem el mateix process per restaurar-la en google drive.
  ![](img/image33.png)  
  ![](img/image34.png)  
  ![](img/image35.png)  
  ![](img/image36.png)  
  ![](img/image37.png)  
    
    
    
    
    
    
    
    
    
    
    
  


## Configuració i còpies de seguretat a Linux amb Duplicity
Maquines Virtuals.
  ![](img/image38.png)  
Crearem una nova partició al disc.
  sudo fdisk /dev/sdb  
n (nova partició).
p (primària).
ENTER (valors per defecte).
ENTER (valors per defecte).
ENTER (valors per defecte).
w (guardar).
  ![](img/image39.png)  
Podem comprobar que s’ha creat correctament amb.
  sudo fdisk \-l  
  ![](img/image40.png)  
Ara li donarem format XFS.
  sudo mkfs.xfs /dev/sdb1  
  ![](img/image41.png)  
Crearem la carpeta on muntarem el disc la carpeta a /media/backup.
  sudo mkdir \-p /media/backup  
Muntarem el disc a la carpeta amb.
  sudo mount /dev/sdb1 /media/backup  
Instal·larem Duplicity.
  ![](img/image42.png)  
Crearem un parell d’usuaris més amb carpeta personal.
  sudo useradd \-m \-s /bin/bash usuari2 && sudo useradd \-m \-s /bin/bash usuari3  
Comprovarem que s’hagin creat correctament les carpetes personals.
  ls \-a /home  
  ![](img/image43.png)  
Crearem 4 arxius a la carpeta home del nostre usuari principal amb fallocate.
  fallocate \-l 10MB arxiu1  
  fallocate \-l 10MB arxiu2  
  fallocate \-l 10MB arxiu3  
  fallocate \-l 10MB arxiu4  
  ![](img/image44.png)  
Farem una copia de seguretat de la nostra carpeta home ens demanara el GnuPG degut a que duplicity vol xifrar el backup i ens demanara una contrasenya podem posar la que volguem o podem deixarla en blanc..
  sudo duplicity full /home/user/ file:///media/backup/  
  ![](img/image45.png)  
Ara esborrarem tots els arxius que vam crear i comprovarem que s’han esborrat amb.
  rm arxiu\*  
  ls  
  ![](img/image46.png)  
Farem la restauracio amb el backup que em posat a la carpeta de /media/backup i comprovarem que s’hagin restaurat els arxius.
  sudo duplicity restore file:///media/backup/ /home/user/restored/  
  ls  
  ![](img/image47.png)  
Per fer una copia incremental primer afegirem un nou arxiu pero aquesta vegada de 4MB.
  ![](img/image48.png)  
Posarem la comanda sense cap mena d'argument el que farà que detecti que ja hi ha un backup i es farà una còpia incremental.
  sudo duplicity /home/user/ file:///media/backup/  
  ![](img/image49.png)  
Desmuntem el disc.
  sudo umount /media/backup  
Crearem el script [fullbackup.sh](http://fullbackup.sh).
  sudo nano [fullbackup.sh](http://fullbackup.sh)  
  \!/bin/bash  
    
  export PASSPHRASE="user"  
    
  mount /dev/sdb1 /media/backup  
    
  duplicity full /home/user file:///media/backup/homebackup  
    
  umount /media/backup  
    
Donarem permisos de execucio al script amb.
  sudo chmod \+x [fullbackup.sh](http://fullbackup.sh)  
Utilitzarem sudo contrab com a root pq es pugui executar correctament l’script i configurarem pq se executi els diumenges a les 23:00.
  sudo crontab \-e

  ![](img/image50.png)  
Creem l’script incrementalbackup.sh per a còpies incrementals.
  sudo nano [fullbackup.sh](http://fullbackup.sh)  
  \#\!/bin/bash  
    
  export PASSPHRASE="user"  
    
  mount /dev/sdb1 /media/backup  
    
  duplicity full /home/user/ file:///media/backup  
    
  umount /media/backup  
li donem permisos de execució.
  sudo chmod \+x [incrementalbackup.sh](http://incrementalbackup.sh)  
Utilitzarem sudo contrab com a root pq es pugui executar correctament l’script i configurarem pq se executi de dilluns a dissabte a les 23:00.
  sudo crontab \-e  
  ![](img/image51.png)
