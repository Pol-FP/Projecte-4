# 🗂️ T02: DRP: Còpies de Seguretat  
### *Cas pràctic — Implementació i proves de concepte*

Aquesta activitat posa en pràctica la política de còpies de seguretat dissenyada a la T01 per al client **"Muntatges i Serveis Tècnics SL"**.  
L’objectiu és crear **guies tècniques amb proves de concepte** que permetin al personal del client implementar el pla de còpies tant en un entorn **Windows** com en un entorn **Linux**.

L’activitat es divideix en dues parts principals:

---

# 🔹 Part 1 — Còpies de seguretat en Windows (Duplicati)

En aquesta part es simula l’equip Windows del director de l’empresa, que necessita un sistema de còpies de seguretat basat en l’esquema **3-2-1**.

Es crea una màquina virtual Windows 11 amb:
- Un disc principal (SO)
- Un disc secundari de 10 GB per a les còpies locals
- Còpia **cada hora** al disc secundari
- Còpia **a les 18:00** al **Google Drive** (Duplicati)

La guia explica:
- Instal·lació de Duplicati  
- Configuració de les tasques de còpia  
- Funcionament i proves  
- Restauració des de disc local i des del cloud  

---

# 🔹 Part 2 — Còpies de seguretat en Linux (Duplicity + Cron)

En aquesta part es treballa amb un **Ubuntu Server**, afegint un disc de 10 GB per simular una unitat externa.

La guia inclou:
- Inicialització i muntatge del disc  
- Instal·lació de Duplicity  
- Creació d’usuaris i arxius de prova  
- Execució de còpies completes i incrementals  
- Restauracions  
- Automatització amb **scripts** i **cron**  
- Garantir que la unitat de còpia està **desmuntada per seguretat** per defecte  

També incorpora els scripts:
- `fullbackup.sh` → còpia completa (diumenges 23:00)  
- `incrementalbackup.sh` → còpia incremental (dilluns-dissabte 23:00)

---

## 📂 Estructura de carpetes

Dins la carpeta `tasca02` es troben els següents arxius:

- `windows.md`: Guia tècnica amb proves de concepte de com implementar el pla de còpies a Windows.
- `linux.md`: Guia tècnica amb proves de concepte de com implementar el pla de còpies a Linux.

---

## 📎 Documents

Podeu consultar tots els documents fent clic al document corresponent:

- Al arxiu [windows.md](T02_Pol_FORMATO.md) podeu trobar la guia tècnica de Windows.
- Al arxiu [linux.md](T02_POL_LINUX.md) podeu trobar la guia tècnica de Linux.
