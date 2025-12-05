1. **Què copiar? (Priorització): Quines són les dades més crítiques del servidor? Cal fer còpia dels 10 equips clients? Justifica-ho.**  
   El servidor de fitxers d’Ubuntu s’ha de copiar perquè conté dades importants i crítiques. Les **bases de dades de Comptabilitat i Clients** són les més prioritàries, ja que serien irrecuperables i són essencials per a la continuïtat de la companyia; tenen un **RPO màxim de 4 hores** i un **RTO de menys de 4 hores**, per la qual cosa requereixen còpies molt freqüents. Els **Documents de Projectes** (plànols i especificacions tècniques) i les **carpetes personals dels usuaris** són menys crítiques, però cal copiar-les perquè contenen informació necessària per a la feina diària i poden assumir un **RPO de 24 hores**.  
   Pel que fa als 10 equips Windows 10/11, caldria copiar només la carpeta *Documents*, perquè alguns tècnics hi guarden documents importants, però no és necessari copiar tot l’equip, ja que aquestes dades no són tan crítiques i el seu **RTO i RPO no són estrictes**.  
2. **Periodicitat i Tipus de Còpia: Proposa un calendari bàsic per a la setmana (Diari/Setmanal/Mensual) i quin tipus de còpia aplicaràs (Completa, Diferencial, Incremental) per a les dades crítiques.**

| Tipus de dada | Periodicitat | Tipus de còpia |
| :---- | :---- | :---- |
| **Documents de Projecte** | **Diària** | **Incremental** |
| **Bases de Dades** | **Diària** | **Completa** |
| **Carpetes Personals dels Usuaris** | **Diària** | **Incremental** |

3. **Mitjans i Ubicació: Quin tipus de mitjà de còpia utilitzaries (Discs durs externs, NAS, Cloud, Cintes)? On s'hauria de guardar físicament la còpia més recent (Regla 3-2-1).**

Les còpies es faran combinant un NAS intern per a recuperacions ràpides, es farien còpies incrementals i com a segona mesura un servei de cloud per garantir una còpia off-site es faria completa cada setmana. Segons la regla 3-2-1, la còpia més recent es guardarà al NAS intern, mentre que una segona còpia es mantindrà al núvol per protegir-se de desastres físics.

