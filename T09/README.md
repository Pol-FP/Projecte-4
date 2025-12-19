# 📁 T09: Servidor de fitxers Linux — NFS
## Tasca individual · EverPia

En aquesta activitat es realitza una **Prova de Concepte (PoC)** per implementar un **servidor de fitxers centralitzat en entorns Linux** mitjançant **NFS (Network File System)**. La documentació servirà per demostrar al client el funcionament, els avantatges i les limitacions de la solució proposada.

---

## 📌 Introducció

Molt bé, equip de consultors júniors.  
En el marc del nostre projecte, ens trobem amb un requisit tècnic molt habitual: la **centralització de dades en entorns Linux**. Aquesta necessitat és clau per millorar la col·laboració, el control de versions i l’eficiència dels equips de desenvolupament.

---

## 🏢 El cas del client: *DevOptimize Solutions*

*DevOptimize Solutions* és una petita startup de desenvolupament de programari que treballa exclusivament amb sistemes **GNU/Linux**. Actualment pateixen un problema crític:

- El codi font i els actius (documents, scripts, recursos de disseny) estan distribuïts en equips locals.
- Cada desenvolupador manté còpies pròpies dels fitxers.
- Això provoca errors constants de versions i una pèrdua important d’eficiència.

Per solucionar-ho, el client ens ha contractat per implementar un **servidor de fitxers centralitzat**.

---

## 🎯 Objectiu de la tasca

Dissenyar i implementar una demostració funcional que permeti:

- Centralitzar fitxers en un servidor Linux mitjançant **NFSv3**.
- Mostrar com els clients Linux accedeixen als recursos compartits.
- Simular un entorn real sense autenticació centralitzada.
- Demostrar el control d’accés mitjançant permisos de sistema i opcions d’exportació.
- Identificar les limitacions de NFS en absència d’un sistema d’identitat centralitzat.

---

## 🧩 Abast tecnològic

La solució es basa en les següents tecnologies:

- **NFS (Network File System) versió 3**
- Servidor Linux (Ubuntu Server)
- Client Linux (Ubuntu Desktop o equivalent)
- Autenticació local basada en:
  - Usuaris i grups del sistema
  - Permisos POSIX (`chmod`, `chown`)
  - Configuració d’exportacions a `/etc/exports`

El client ha especificat que **no disposa d’un sistema d’autenticació centralitzada** (LDAP, Active Directory, etc.) ni té previst implementar-lo a curt termini.

---

## 🛠️ Tasques a realitzar

### **Fase única — Treball individual (PoC)**

1. Preparar l’entorn de proves amb:
   - Un servidor Linux amb servei NFS.
   - Un client Linux que consumeixi els recursos compartits.
2. Instal·lar i configurar el **servidor NFS (NFSv3)**.
3. Crear els directoris compartits i definir les exportacions a `/etc/exports`.
4. Crear usuaris i grups locals per simular l’entorn del client.
5. Aplicar permisos i propietats als directoris:
   - `chmod`
   - `chown`
6. Configurar el client NFS i muntar els recursos compartits.
7. Demostrar el control d’accés segons usuari i grup.
8. Analitzar les limitacions del sistema sense autenticació centralitzada.

---

## 📦 Resultat esperat

Guia amb explicacions

[](T09.md)

---

💡 *Aquesta PoC ha de permetre al client entendre tant els avantatges de NFS com les seves limitacions en absència d’un sistema d’identitat centralitzat.*
