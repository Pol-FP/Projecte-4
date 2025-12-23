## **Fase 1: Anàlisi Comparativa i Selecció de la Solució**

El primer pas és decidir quina eina utilitzarà EverPia. Heu de fer una anàlisi de mercat i presentar un breu informe comparatiu.

Tasques:

Investigar quatre alternatives populars d'assistència remota. (Exemples obligatoris: TeamViewer, AnyDesk, Google Remote Desktop. Heu d'afegir-ne una quarta de la vostra elecció.

Crear una Taula Comparativa que avaluï cada solució basant-se en els següents criteris clau:

·         Facilitat d'ús (per al client): Requereix instal·lació? És portable? Com de senzill és per a un usuari no tècnic passar-nos l'ID?

·         Disponibilitat (Sistemes Operatius): Funciona a Windows? macOS? Linux? (Vital per a EverPia, ja que donem suport a entorns mixtos).

·         Model de Preu (Llicència): És gratuït per a ús comercial? Quant costa una llicència per a tècnic? Quines limitacions té la versió gratuïta?

Presentar una Recomanació: Basant-vos en la vostra taula, heu de recomanar oficialment una de les eines per a l'adopció a EverPia, justificant per què és la millor opció (equilibri entre facilitat, funcionalitat i cost).

| APLICACIONS D'ASSISTÈNCIA REMOTA | TeamViewer | AnyDesk | Google Remote Desktop | Zoho Assist |
| :---- | :---- | :---- | :---- | :---- |
| Facilitat d'ús (per al client) | Interfície completa però pot ser complexa per a usuaris no tècnics; configuració simple però amb moltes opcions. Usuari a Reddit es queixa de bloquejos inesperats pel “ús comercial” i frustració amb el sistema de llicències.  | Ràpid i lleuger; fàcil d’instal·lar i utilitzar per accés remot bàsic; alguns usuaris el troben menys intuïtiu que altres. | Molt senzill i intuïtiu; només cal entrar amb Google i un codi per connectar-se, pensat per a usuaris no tècnics. 100% **gratuit.** | Interfície fàcil, especialment per a petites empreses i tècnics; basat en navegador amb accés directe. Més senzill que TeamViewer segons opinions. |
| Disponibilitat(Sistemes Operatius) | Compatible amb Windows, macOS, Linux, iOS, Android, Chrome OS i Raspberry Pi (ampli suport multiplataforma).  | Compatible amb Windows, macOS, Linux, iOS i Android. | Funciona amb Windows, macOS, Linux i Chrome OS a través del navegador o app. | Compatible amb Windows, macOS, Linux, iOS i Android; sessions poden iniciar-se des de navegador. |
| Model de Preu (Llicència) | Gratuït per a ús personal; plans comercials pagats (començen 65,9$/mes per usuari). Sol considerar-se car per a empreses. | Gratuït per a ús persona**l**; plans pagats més assequibles comparats amb TeamViewer.  | Totalment gratuït (no requereix subscripció). | Gratuït amb funcions bàsiques; plans pagats des d’uns 8–10 €/mes per tècnic aproximadament (segons planificació de Zoho). |

### **Recomanació: AnyDesk**

Es recomana **AnyDesk** com a eina d’assistència remota per a EverPia perquè ofereix un **excel·lent equilibri entre facilitat d’ús, rendiment i cost**. És una aplicació lleugera i ràpida, que pot executar-se sense instal·lació, fet que facilita molt l’accés per a clients no tècnics. La seva interfície és simple i mostra l’ID de connexió de manera clara, reduint errors i temps d’assistència. A més, és compatible amb Windows, macOS i Linux, essencial per a entorns mixtos, i el seu model de llicència és més assequible que altres com TeamViewer, convertint-la en una opció eficient i econòmica per a EverPia.



---



# Guia 1: Manual per al Tècnic (Intern d'EverPia) (jan)

Aquesta guia serà per als futurs becaris i tècnics que s'incorporin a l'empresa.

Ha d'explicar el flux de treball des del punt de vista del consultor. Ha d'incloure (amb captures de pantalla):

- Com instal·lar la versió completa/tècnica de l'eina.
  
- Com iniciar una sessió de suport.
  
- Com gestionar funcions clau (transferència d'arxius, canvi de pantalla, reinici remot).
  
- Bones pràctiques de seguretat (p. ex., tancar sempre la sessió, no desar contrasenyes de clients).

---

## 1. Instal·lació d’AnyDesk (versió tècnica)

### 1.2 Descàrrega de l’aplicació

1. Obre el navegador web
2. Accedeix a: **[https://anydesk.com](https://anydesk.com)**
3. Clica **Download / Descarregar**
4. Selecciona la versió corresponent al teu sistema operatiu
   
<img width="1327" height="569" alt="image" src="https://github.com/user-attachments/assets/f9be1e14-de15-4927-aaa6-9433cff6e7aa" />


---

### 2. Instal·lació

1. Executa el fitxer descarregat

<img width="327" height="125" alt="image" src="https://github.com/user-attachments/assets/6f2b7c66-0853-4e0b-8f2a-1548b395e90c" />

2. Si és necessari, selecciona **Install AnyDesk** i Finalitza la instal·lació

<img width="721" height="610" alt="image" src="https://github.com/user-attachments/assets/7017f138-dc4f-41b1-8e62-e95a134168cd" />

<img width="565" height="241" alt="image" src="https://github.com/user-attachments/assets/15289e0f-3969-4fde-b983-4e760988ba46" />

AnyDesk pot funcionar sense instal·lació, però **es recomana instal·lar-lo** per a suport professional.

---

## 3. Iniciar una sessió de suport remot

### Identificador d’AnyDesk

Cada dispositiu disposa d’un **AnyDesk ID** únic.

1. Primer ens reegistrarem i una vegada fet iniciarem sessió:

<img width="472" height="621" alt="image" src="https://github.com/user-attachments/assets/beec33b3-118d-48d0-a30d-c9e88f32da0e" />

2. Demanar al client el seu AnyDesk ID que sortira a la part de dalt de la aplicació 

<img width="1014" height="573" alt="image" src="https://github.com/user-attachments/assets/de41497f-5024-4f2b-8772-185240eb53d1" />

3. Introdueix-lo al camp **Remote Address**

<img width="743" height="113" alt="image" src="https://github.com/user-attachments/assets/325651f9-7978-4998-b4c1-815a1e88ad65" />

4. Clica **Connect**

<img width="983" height="113" alt="image" src="https://github.com/user-attachments/assets/4ecdb5bc-ab5c-43a3-9bc8-136dcba46934" />

5. Ens sortira que faltaran permisos de captura de pantalla al dispositiu remot

<img width="912" height="412" alt="image" src="https://github.com/user-attachments/assets/fac1a0f0-7f58-4e7f-9780-ff7fa0276c1f" />

6. al altre dispositiu haurem de desactivar a predeterminat la opció de bloquear mi dispositivo

<img width="829" height="679" alt="image" src="https://github.com/user-attachments/assets/84dc05b0-aa0f-44af-8ad0-d515e9c13bbd" />

---

### 4. Acceptació del client

El client ha d’acceptar la connexió i pot:

* Permetre o denegar control del teclat i ratolí
* Autoritzar la transferència d’arxius
* Limitar l’accés a funcions concretes

<img width="510" height="672" alt="image" src="https://github.com/user-attachments/assets/908f9ca0-6757-4edc-b005-a5cb1f091b45" />


---

## 5. Gestió de funcions clau a AnyDesk

---

### 5.1 Transferència d’arxius

Permet enviar i rebre arxius de manera segura.

**Passos:**

### 1. Accedeix al menú **File Transfer**
   
<img width="603" height="305" alt="image" src="https://github.com/user-attachments/assets/6f3bd7a8-7002-4041-9084-09e8c7329e55" />

### 2. Selecciona l’arxiu origen i destinació

Després de connectar amb un altre equip de manera remota, selecciona l'arxiu que desitges transferir i fes clic sobre aquest amb el botó dret del ratolí. Una vegada fet això apareixerà un menú desplegable on has de prémer el botó “Copiar”. Alternativament pots utilitzar la drecera de teclat Ctrl + C.

<img width="613" height="477" alt="image" src="https://github.com/user-attachments/assets/65a44be6-d414-402d-9f0c-4962a2771cfb" />


### 3. Inicia la transferència

Ara simplement accedeix a l'ordinador remot i cerca la carpeta on vols desar l'arxiu. Una vegada en ella, fes clic amb el botó dret del ratolí i prem el botó “Pegar”. Si ho prefereixes, pots utilitzar la drecera de teclat Ctrl + V. Després d'això simplement espera al fet que l'arxiu es transfereixi del teu ordinador a un altre.

<img width="284" height="281" alt="image" src="https://github.com/user-attachments/assets/b121f4d7-008b-4472-88ac-492a700f0899" />

---

### 5.2 Canvi de pantalla / visualització

Si el client disposa de diverses pantalles:

### 1. Obre el menú de **Display / Pantalla**

<img width="2454" height="258" alt="image" src="https://github.com/user-attachments/assets/a712fdcc-b9fe-408e-bd89-6631473ab445" />

### 2. Selecciona la pantalla que vols visualitzar

<img width="261" height="513" alt="image" src="https://github.com/user-attachments/assets/3d1494b4-7ed7-44bc-98b7-33cde19186f2" />

---

### 5.3 Reinici remot

AnyDesk permet reiniciar el dispositiu remot mantenint la connexió.

**Passos:**

1. Accedeix a **Actions / Accions** i Selecciona **Restart**

<img width="1500" height="2000" alt="image" src="https://github.com/user-attachments/assets/69d82cf6-145f-4841-a30f-95fb5e6dd33b" />

3. Confirma el reinici

<img width="923" height="859" alt="image" src="https://github.com/user-attachments/assets/2cfe83a2-0c93-4d7a-99ab-af95d98e00b3" />


---

## 6. Finalització de la sessió

Quan la incidència estigui resolta:

### 1. Comunica al client les accions realitzades

<img width="389" height="491" alt="image" src="https://github.com/user-attachments/assets/57407f1f-0c43-4f60-bb88-cd7ef406026f" />


### 2. Tanca la connexió clicant **Disconnect**

<img width="699" height="516" alt="image" src="https://github.com/user-attachments/assets/c4f25d51-0b8b-487e-9b49-46474ffd6f40" />

---

## 7. Bones pràctiques de seguretat

### 7.1 Gestió de sessions

* Tanca sempre la connexió en acabar
* No reutilitzis connexions actives
* Evita sessions obertes sense supervisió

---

### 7.2 Credencials i permisos

* No demanis ni desis contrasenyes de clients
* Utilitza permisos temporals
* Respecta les limitacions definides pel client

---

### 7.3 Dades i confidencialitat

* No guardis arxius del client sense autorització
* Elimina qualsevol fitxer un cop finalitzat el suport
* Compleix la normativa de protecció de dades (RGPD)

---

## 8. Responsabilitat del tècnic

El tècnic és responsable de:

* L’ús professional d’AnyDesk
* La seguretat de la connexió
* La confidencialitat de la informació tractada
* El compliment dels protocols interns d’EverPia
