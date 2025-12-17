# T02: Còpies de Seguretat amb Duplicity (Linux)
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
sudo fdisk -l
```

![imagen40](img/image40.png) 

Ara li donarem format XFS.
```bash
sudo mkfs.xfs /dev/sdb1
```

![imagen41](img/image41.png) 

Crearem la carpeta on muntarem el disc la carpeta a /media/backup.
```bash
sudo mkdir -p /media/backup
```
Muntarem el disc a la carpeta amb.
```bash
sudo mount /dev/sdb1 /media/backup
```
Instal·larem Duplicity.

![imagen42](img/image42.png)

Crearem un parell d’usuaris més amb carpeta personal.
```bash
sudo useradd -m -s /bin/bash usuari2 && sudo useradd -m -s /bin/bash usuari3
```
Comprovarem que s’hagin creat correctament les carpetes personals.
```bash
ls -a /home  
```

![imagen43](img/image43.png)

Crearem 4 arxius a la carpeta home del nostre usuari principal amb fallocate.

```bash
fallocate -l 10MB arxiu1  
fallocate -l 10MB arxiu2  
fallocate -l 10MB arxiu3  
fallocate -l 10MB arxiu4  
```
  
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

#!/bin/bash  
    
export PASSPHRASE="user"  
    
mount /dev/sdb1 /media/backup  
    
duplicity full /home/user file:///media/backup/homebackup  
    
umount /media/backup  
```
    
Donarem permisos de execucio al script amb.
```bash
sudo chmod +x fullbackup.sh
```
Utilitzarem sudo contrab com a root pq es pugui executar correctament l’script i configurarem pq se executi els diumenges a les 23:00.
```bash
sudo crontab -e
```

![imagen50](img/image50.png)

Creem l’script incrementalbackup.sh per a còpies incrementals.
```bash
sudo nano fullbackup.sh

#\!/bin/bash  
    
export PASSPHRASE="user"  
    
mount /dev/sdb1 /media/backup  
    
duplicity full /home/user/ file:///media/backup  
    
umount /media/backup
```  
li donem permisos de execució.
```bash
sudo chmod +x incrementalbackup.sh
```
Utilitzarem sudo contrab com a root pq es pugui executar correctament l’script i configurarem pq se executi de dilluns a dissabte a les 23:00.
```bash
sudo crontab -e
```

![imagen51](img/image51.png)
