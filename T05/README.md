# 🧩 T05: Accés Remot. Connexió via SSH

Com a membres de l’equip tècnic de la consultora **EverPia**, heu rebut una nova tasca que és **crítica per a l’operativa diària**: garantir l’accés remot segur als servidors dels nostres clients i als nostres propis sistemes interns.  
En l’actualitat, els servidors **no es troben físicament al nostre costat**, sinó que estan allotjats en CPDs o al núvol, i l’accés físic és l’excepció, no la norma.  

Per això, la nostra eina principal és **SSH (Secure Shell)**, l’estàndard de la indústria per administrar màquines Linux de manera **xifrada i segura**, evitant riscos de seguretat i permetent una gestió eficient.

---

## 🎯 Objectiu del projecte

- Configurar i provar connexions SSH entre clients i servidors interns i de clients.  
- Establir **bons hàbits de seguretat**, incloent l’ús de claus públiques i privades.  
- Documentar el procés perquè nous becaris puguin ser **operatius des del primer dia**.  
- Crear una **guia interna** que serveixi com a referència per a la base de coneixement de l’equip.

---

## 🧩 Tasques a realitzar

### Fase Teòrica
1. Entendre els conceptes bàsics de SSH i la seva arquitectura.  
2. Conèixer la diferència entre **autenticació per contrasenya** i **autenticació per clau pública/privada**.  
3. Revisar els principals fitxers de configuració (`~/.ssh/config`, `sshd_config`) i permisos recomanats.  
4. Investigar mesures de seguretat addicionals, com **forwarding de ports, restriccions per IP i ús de passphrases**.

### Fase Pràctica
1. Crear dues màquines virtuals per simular un entorn client-servidor.  
2. Configurar el servidor SSH i assegurar que està actiu i escoltant al port correcte.  
3. Generar claus SSH al client i copiar la clau pública al servidor (`ssh-copy-id` o equivalent).  
4. Connectar-se des de **Linux** utilitzant la terminal nativa.  
5. Connectar-se des de **Windows** utilitzant PowerShell o terminals moderns (Windows Terminal, OpenSSH integrat).  
6. Verificar que la connexió es realitza **sense necessitat de contrasenya** (clau pública).  
7. Documentar tot el procés amb **comandes, captures de pantalla i notes de seguretat** dins del fitxer `guia.md`.

---

## 📄 Solució

Un dossier complet amb:

- Documentació tècnica (`Solució`) que inclogui:  
  - Configuració del servidor i del client SSH.  
  - Generació i gestió de claus públiques i privades.  
  - Connexions des de Linux i Windows amb captures i explicacions.  
  - Bones pràctiques de seguretat recomanades.  
- Materials formatius utilitzats (UD04.AA2 – Pràctica SSH, vídeo de clau pública/privada).  

Pots consultar els recursos oficials i la documentació de l’activitat als següents materials:  

👉 [**Guia SSH**](Solució.md)
