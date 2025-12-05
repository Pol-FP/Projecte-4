# 💾 T01: DRP — Còpies de Seguretat  
## Estudi de Cas: *Muntatges i Serveis Tècnics SL*

La companyia *Muntatges i Serveis Tècnics SL*, dedicada a la instal·lació i manteniment d’equips industrials, depèn fortament del seu servidor de documents, bases de dades i equips clients per al funcionament diari. L’empresa necessita establir una **Política de Còpies de Seguretat robusta i fiable** adaptada als requisits de RTO, RPO i retenció d’un mes.

Aquest projecte es realitza en **tres fases cooperatives** per analitzar, consensuar i dissenyar un esquema complet de Backup 3-2-1.

---

## 🎯 Objectiu del projecte

Dissenyar una política de còpies de seguretat completa que garanteixi:

- Protecció de les dades crítiques del servidor.  
- Compliment dels requisits de recuperació RTO i RPO.  
- Implantació d’un sistema de còpia 3-2-1 segur i sostenible.  
- Un cronograma de còpies clar i aplicable a l’empresa.  
- Document final presentable a direcció.

---

## 🧩 Tasques a realitzar

### **Fase 1 — Treball individual**
1. Identificar les dades crítiques del sistema i prioritzar què s’ha de copiar.  
2. Proposar periodicitat i tipus de còpia (completa, diferencial, incremental).  
3. Escollir mitjans i ubicacions aplicant la regla 3-2-1.

---

### **Fase 2 — Treball per parelles**
1. Comparar i consensuar respostes individuals.  
2. Elaborar una **Proposta Unificada d’Esquema 3-2-1**, incloent:
   - Dades crítiques  
   - Periodicitat i tipus de còpia de la BD  
   - Mitjà local i mitjà extern  
   - Justificació clara  

---

### **Fase 3 — Treball en grup**
1. Presentació de propostes per parelles i debat de pros/contres.  
2. Redacció de la **Política de Còpies de Seguretat Definitiva** per lliurar a l’empresa.

---

# 📄 Document Final (Resultat de la Fase 3)

## 1) Dades Objecte de Còpia

### **Servidor (Ubuntu Server)**  
- **Dades crítiques:**  
  - Bases de dades de Comptabilitat i Clients (20 GB) — canvi freqüent  
  - Documents de Projectes: plànols i especificacions (300 GB)  
- **Dades no crítiques:**  
  - Carpetes personals dels usuaris (100 GB)

### **Equips clients (10 PCs Windows)**  
- Còpia només de la carpeta **Documents**, usada per tècnics com espai temporal de fitxers importants.

---

## 2) Cronograma Setmanal Detallat

| Dia | Dades | Tipus de còpia | Mitjà |
|-----|-------|----------------|--------|
| Dilluns | BD + Documents | Incremental | NAS local |
| Dimarts | BD | Incremental | NAS local |
| Dimecres | BD + Documents | Incremental | NAS local |
| Dijous | BD | Incremental | NAS local |
| Divendres | BD + Documents | Diferencial | NAS local |
| Dissabte | Totes les dades del servidor | Completa | Cloud |
| Diumenge | — | Verificació de còpies | — |

---

## 3) Elecció de Mitjans i Ubicació — Regla 3-2-1

- **Mitjà 1 (Local):**  
  NAS d’alta capacitat a la xarxa interna.  
  - Avantatges: alta velocitat, recuperació immediata, ideal per complir RTO.

- **Mitjà 2 (Extern):**  
  Còpia xifrada al núvol (Azure, Google Cloud o AWS).  
  - Avantatges: ubicació fora de lloc, alta disponibilitat, retenció ampliable.

- **Ubicació Fora de Lloc:**  
  Emmagatzematge lògic al Cloud.  
  Responsable: tècnic de TI encarregat de còpies i verificacions setmanals.

---

## 4) Estratègia de Recuperació (RTO/RPO)

- **RTO requerit: 4 hores**  
  - La presència del NAS local permet restaurar ràpidament les BD i documents.

- **RPO requerit: 4 hores (BD)**  
  - Exportacions automàtiques o rèpliques cada 4 hores cap al repositori intern del NAS.  
  - En cas de desastre total, restauració des del Cloud amb pèrdua mínima de dades.

---

## 📦 Solució

La solució final inclou:

- Un **esquema complet de còpies 3-2-1** adaptat a la infraestructura de l’empresa.  
- Un **cronograma setmanal òptim**, balancejat entre cost, rendiment i seguretat.  
- Una **política formal de còpies** llesta per entregar a direcció.

---

