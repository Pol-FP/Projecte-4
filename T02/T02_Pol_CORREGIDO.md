# T02: Còpies de Seguretat amb Duplicati a Windows i Linux

## 1. Especificacions de la màquina Windows 11

![][image1]

## 2. Instal·lació i configuració de Duplicati a Windows

### Pas 1: Instal·larem Duplicati

### Pas 2: Obrirem Duplicati i seleccionarem **Ara no, gràcies**

### Pas 3: Afegirem una nova còpia de seguretat (Add a new Backup)

### Pas 4: Configurarem el nom, descripció i xifrat amb contrasenya

### Pas 5: Seleccionarem el destí com a File System per còpia local

### Pas 6: Definirem la carpeta de destinació i continuarem

### Pas 7: Saltarem la prova (Skip test)

### Pas 8: Seleccionarem els fitxers a copiar i continuarem

### Pas 9: Programarem la freqüència (cada hora, inici el dia 9 a les 20:00)

### Pas 10: Definirem opcions per defecte i finalitzarem la configuració

## 3. Configuració de còpia al núvol (Google Drive)

Seguiu el mateix procés fins al destí, però seleccioneu Google Drive, autentiqueu amb AuthID i definiu la carpeta.

## 4. Restauració de còpies

Comprovarem la restauració tant en còpia local com en Google Drive.

## 5. Configuració a Linux amb Duplicity

### Creació de partició i muntatge

```bash
sudo fdisk /dev/sdb
# n (nova partició)
# p (primària)
# ENTER (valors per defecte)
# w (guardar)
```

Format XFS:

```bash
sudo mkfs.xfs /dev/sdb1
```

Muntatge:

```bash
sudo mkdir -p /media/backup
sudo mount /dev/sdb1 /media/backup
```

### Instal·lació de Duplicity

```bash
sudo apt install duplicity
```

### Creació d'usuaris i arxius de prova

```bash
sudo useradd -m -s /bin/bash usuari2
sudo useradd -m -s /bin/bash usuari3
fallocate -l 10MB arxiu1
fallocate -l 10MB arxiu2
fallocate -l 10MB arxiu3
fallocate -l 10MB arxiu4
```

### Còpia completa i restauració

```bash
sudo duplicity full /home/user/ file:///media/backup/
rm arxiu*
sudo duplicity restore file:///media/backup/ /home/user/restored/
```

### Còpia incremental

```bash
sudo duplicity /home/user/ file:///media/backup/
```

### Scripts i programació amb CRON

Script fullbackup.sh:

```bash
#!/bin/bash
export PASSPHRASE="user"
mount /dev/sdb1 /media/backup
duplicity full /home/user file:///media/backup/homebackup
umount /media/backup
```

Permisos i cron:

```bash
sudo chmod +x fullbackup.sh
sudo crontab -e
```

