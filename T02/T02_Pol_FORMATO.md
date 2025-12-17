# T02: Còpies de Seguretat amb Duplicati (Windows) i Duplicity (Linux)

#### 

## 1. Configuració i còpies de seguretat a Windows amb Duplicati
Aqui tenim les especificacions de la maquina Windows 11.

![imagen01](img/image1.png)

Instalarem Duplicati.
Obrirem Duplicati i ens sortirà una finestra al nostre navegador predeterminat, dins la finestra li donarem ara no gràcies.

![imagen02](img/image2.png)  

Li donarem a add en backups.

![imagen03](img/image3.png)

Donarem a Add a new Backup.

![imagen04](img/image4.png)  

Aqui farem la configuracio general de la copia de seguretat com el nom del backup la seva descripcio i el seu xifrat i asignarem una contrasenya a la copia.

![imagen05](img/image5.png)

En el desti de on vulem que sigui el nostre backup posarem la file system per que volem la copia al nostre propi sistema.

![imagen06](img/image6.png)

Seleccionarem on volem que vagi la nostra copia de seguretat i li donarem continue.

![imagen07](img/image7.png)

Li donarem a skip test.

![imagen08](img/image8.png)  

Ara podrem seleccionar a que li volem fer el backup una vegada seleccionat a que li volem fer backup donarem continue.

![imagen09](img/image9.png)  

Aqui podrem seleccionar cada quant volem fer la copia de seguretat i desde quant comença a fer les copies, en aquest cas cada hora i començara el 9 a les 20:00.

![imagen10](img/image10.png)  

Aqui podrem seleccionar en quants archius volem que sigui feta la copia de seguretat.

![imagen11](img/image11.png)  
![imagen12](img/image12.png)  

una vegada acabat tot ens sortira la seguent finestra mostrant que s’ha creat el backup correctament.

![imagen13](img/image13.png)  

Per fer la copia de seguretat al nuvol (Google drive) tornarem a repetir el process fins el apartat de desti del backup.

![imagen14](img/image14.png)  
![imagen15](img/image15.png)  
![imagen16](img/image16.png)  

Aqui en comptes de posar file system li donarem a google Drive.

![imagen17](img/image17.png)  

Una vegada li donem a google drive li donarem a AuthID i fem login amb Google.

![imagen18](img/image18.png)  
![imagen19](img/image19.png)  

Aceptarem els termes de duplicat.

![imagen20](img/image20.png)  

Posarem la ruta del nostre google drive on volem que vagi el nostre backup.

![imagen21](img/image21.png)  

Posarem de que carpeta volem que es fagi el backup i donarem continuar.

![imagen22](img/image22.png)  

Configurarem la hora i el dia en aquest cas volem que es fagi cada dia a les 18:00.

![imagen23](img/image23.png)  

A la part de opcions deixarem les opcions default.

![imagen24](img/image24.png)  

Com podem veure tenim els 2 backups els del disc local D: i els de Google Drive.

![imagen25](img/image25.png)  

Per fer la comprovacio que funciona correctament la copie de segureta local del disc D esborrarem el contingut de la carpeta documents.

![imagen26](img/image26.png)  
![imagen27](img/image27.png)  

Li donarem a Restaurar.

![imagen28](img/image28.png)  

Restaurarem desde la copia de seguretat local.

![imagen29](img/image29.png)  

Li donarem a continue.

![imagen30](img/image30.png)  

Ens preguntara a on volem restaurar els arxius i posarem a la seva posició original i que sobreescrigui els arxius a dins de la carpeta.

![imagen31](img/image31.png)  

Una vegada li donem submit restaurarem tot.

![imagen32](img/image32.png)  

Farem el mateix process per restaurar-la en google drive.

![imagen33](img/image33.png)  
![imagen34](img/image34.png)  
![imagen35](img/image35.png)  
![imagen36](img/image36.png)  
![imagen37](img/image37.png)  

## 2. Configuració i còpies de seguretat a Linux amb Duplicity
Maquines Virtuals.

![imagen38](img/image38.png)  

Crearem una nova partició al disc.
```bash
sudo fdisk /dev/sdb
```
n (nova partició).

p (primària).

ENTER (valors per defecte).

ENTER (valors per defecte).

ENTER (valors per defecte).

w (guardar).

![imagen39](img/image39.png)

Podem comprobar que s’ha creat correctament amb.
```bash
sudo fdisk \-l
```

![imagen40](img/image40.png) 

Ara li donarem format XFS.
```bash
sudo mkfs.xfs /dev/sdb1
```

![imagen41](img/image41.png) 

Crearem la carpeta on muntarem el disc la carpeta a /media/backup.
```bash
sudo mkdir \-p /media/backup
```
Muntarem el disc a la carpeta amb.
```bash
sudo mount /dev/sdb1 /media/backup
```
Instal·larem Duplicity.

![imagen42](img/image42.png)

Crearem un parell d’usuaris més amb carpeta personal.
```bash
sudo useradd \-m \-s /bin/bash usuari2 && sudo useradd \-m \-s /bin/bash usuari3
```
Comprovarem que s’hagin creat correctament les carpetes personals.
```bash
ls \-a /home  
```

![imagen43](img/image43.png)

```bash
fallocate \-l 10MB arxiu1  
fallocate \-l 10MB arxiu2  
fallocate \-l 10MB arxiu3  
fallocate \-l 10MB arxiu4  
```
Crearem 4 arxius a la carpeta home del nostre usuari principal amb fallocate.

  
![imagen44](img/image44.png)

Farem una copia de seguretat de la nostra carpeta home ens demanara el GnuPG degut a que duplicity vol xifrar el backup i ens demanara una contrasenya podem posar la que volguem o podem deixarla en blanc..
```bash
sudo duplicity full /home/user/ file:///media/backup/
```

![imagen45](img/image45.png)

Ara esborrarem tots els arxius que vam crear i comprovarem que s’han esborrat amb.
```bash
rm arxiu*  
ls
```

![imagen46](img/image46.png)

Farem la restauracio amb el backup que em posat a la carpeta de /media/backup i comprovarem que s’hagin restaurat els arxius.
```bash
sudo duplicity restore file:///media/backup/ /home/user/restored/
ls
```

![imagen47](img/image47.png)

Per fer una copia incremental primer afegirem un nou arxiu pero aquesta vegada de 4MB.

![imagen48](img/image48.png)

Posarem la comanda sense cap mena d'argument el que farà que detecti que ja hi ha un backup i es farà una còpia incremental.
```bash
sudo duplicity /home/user/ file:///media/backup/
```

![imagen49](img/image49.png)

Desmuntem el disc.
```bash
sudo umount /media/backup
```

Crearem el script fullbackup.sh

```bash
sudo nano fullbackup.sh

\!/bin/bash  
    
export PASSPHRASE="user"  
    
mount /dev/sdb1 /media/backup  
    
duplicity full /home/user file:///media/backup/homebackup  
    
umount /media/backup  
```
    
Donarem permisos de execucio al script amb.
```bash
sudo chmod \+x [fullbackup.sh](http://fullbackup.sh)
```
Utilitzarem sudo contrab com a root pq es pugui executar correctament l’script i configurarem pq se executi els diumenges a les 23:00.
```bash
sudo crontab \-e
```

![imagen50](img/image50.png)

Creem l’script incrementalbackup.sh per a còpies incrementals.
```bash
sudo nano [fullbackup.sh](http://fullbackup.sh)

\#\!/bin/bash  
    
export PASSPHRASE="user"  
    
mount /dev/sdb1 /media/backup  
    
duplicity full /home/user/ file:///media/backup  
    
umount /media/backup
```  
li donem permisos de execució.
```bash
sudo chmod \+x [incrementalbackup.sh](http://incrementalbackup.sh)
```
Utilitzarem sudo contrab com a root pq es pugui executar correctament l’script i configurarem pq se executi de dilluns a dissabte a les 23:00.
```bash
sudo crontab \-e
```

![imagen51](img/image51.png)
