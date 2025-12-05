# **Proposta de Còpies – Muntatges i Serveis Tècnics SL**

## **1\) Dades Objecte de Còpia**

| Origen | Dades | Crítiques | Freqüència de còpia |
| :---- | :---- | :---- | :---- |
| **Servidor** | Bases de Dades (Comptabilitat i Clients) | Sí | Incremental cada 4 hores \+ Completa diària; còpia completa setmanal diumenge |
| **Servidor** | Documents de Projectes | No | Incremental diària \+ Completa setmanal |
| **Servidor** | Carpetes Personals dels Usuaris | No | Incremental diària \+ Completa setmanal |
| **Clients** | Carpeta “Documents” dels equips | Sí/No (segons importància dels fitxers) | Incremental diària \+ Completa setmanal |

**Justificació:**  
Les **bases de dades** són crítiques perquè tenen canvis constants i només poden perdre fins a 4 hores de dades. Els **Documents de Projectes** i **Carpetes Personals** són importants, però poden tolerar una pèrdua de fins a 24 hores. La **carpeta Documents dels clients** es copia parcialment, ja que alguns tècnics hi deixen informació rellevant.

## **2\) Cronograma Setmanal Detallat**

| Dia | Dades | Tipus de còpia | Mitjà |
| :---- | :---- | :---- | :---- |
| Dilluns | Bases de Dades | Incremental cada 4 h \+ completa diària | NAS |
|  | Documents de Projectes | Incremental | NAS |
|  | Carpetes Personals | Incremental | Disco Duro Extern |
| Dimarts | Bases de Dades | Incremental cada 4 h \+ completa diària | NAS |
|  | Documents de Projectes | Incremental | NAS |
|  | Carpetes Personals | Incremental | Disco Duro Extern |
| Dimecres | Bases de Dades | Incremental cada 4 h \+ completa diària | NAS |
|  | Documents de Projectes | Incremental | NAS |
|  | Carpetes Personals | Incremental | Disco Duro Extern |
| Dijous | Bases de Dades | Incremental cada 4 h \+ completa diària | NAS |
|  | Documents de Projectes | Incremental | NAS |
|  | Carpetes Personals | Incremental | Disco Duro Extern |
| Divendres | Bases de Dades | Incremental cada 4 h \+ completa diària | NAS |
|  | Documents de Projectes | Incremental | NAS |
|  | Carpetes Personals | Incremental | Disco Duro Extern |
| Dissabte | Bases de Dades | Incremental cada 4 h \+ completa diària | NAS |
|  | Documents de Projectes | Incremental | NAS |
|  | Carpetes Personals | Incremental | Disco Duro Extern |
| Diumenge | Bases de Dades | Còpia completa setmanal | Cloud |
|  | Documents de Projectes | Còpia completa setmanal | Cloud |
|  | Carpetes Personals | Còpia completa setmanal | Cloud |

Les còpies incrementals es fan diverses vegades al dia per les bases de dades, mentre que la resta només una vegada diària.

## **3\) Elecció de Mitjans i Ubicació (Regla 3-2-1)**

* **Mitjà 1 (Local):**

  * **NAS intern**.  
  * **Justificació:** Permet restaurar dades de manera ràpida en cas de fallada del servidor. És el suport principal per a còpies diàries i incrementals.

* **Mitjà 2 (Extern):**

  * **Cloud Backup** (proveïdor suggerit: Google Cloud o Backblaze B2).  
  * **Justificació:** Ofereix còpia fora de l’empresa amb alta disponibilitat i seguretat. També es poden usar **discs durs externs** com a suport físic setmanal per reforçar la seguretat de la informació crítica.

* **Ubicació Fora de Lloc:**

  * Les còpies al **Cloud** queden fora de l’empresa de forma segura.  
  * Els **discs durs externs** es poden guardar en una altra ubicació física, com un altre despatx de l’empresa o un arxiu segur.  
  * **Responsable de gestió:** El responsable IT de l’empresa comprova que les còpies es sincronitzen correctament, que són completes i que l’històric es manté.

## **4\) Estratègia de Recuperació (RTO/RPO)**

* **RPO (Pèrdua de dades admissible):**

  * Les **bases de dades de Comptabilitat i Clients** es copien incrementalment cada 4 hores, assegurant que la pèrdua màxima de dades no superi les 4 hores, tal com exigeix el requisit.

* **RTO (Temps màxim de recuperació):**

  * Les còpies locals al **NAS** permeten recuperar les dades crítiques ràpidament, en menys de 4 hores, en cas de fallada del servidor.  
  * Les còpies al **Cloud** o **Discs Externs** garanteixen restauració encara que hi hagi una pèrdua total de l’equip físic, assegurant disponibilitat contínua de la informació.

**Conclusió:**  
 Amb aquesta combinació de mitjans i ubicacions, es compleixen tots els requisits de la regla 3-2-1, i es garanteix que les dades més crítiques sempre estiguin disponibles dins del temps màxim permès i amb mínim risc de pèrdua.

