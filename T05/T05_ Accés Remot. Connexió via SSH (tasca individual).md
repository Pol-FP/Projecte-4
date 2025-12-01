

#### 

- Màquines Virtuals (IMPORTANT 2 INTERFÍCIES DE XARXA)  
![imagen1](img/1.png)
![imagen2](img/2.png)

- Amb la següent comanda instal·larem el servei SSH:  
  sudo apt install ssh  
![imagen3](img/3.png)
- A la nostra màquina Linux utilitzarem la següent comanda per saber la seva IP:  
  ip a  
![imagen4](img/4.png)
- Ens connectarem per SSH des de la nostra màquina Windows. Quan introduïm l’usuari i la IP, ens indicarà que la clau del servidor SSH no té cap altre registre i ens preguntarà si estem segurs que ens hi volem connectar. Direm que **sí** i ens advertirà que ha afegit el servidor de manera permanent a la llista de servidors coneguts.  
![imagen5](img/5.png)
![imagen6](img/6.png)
- Habilitarem l’usuari *root* posant-li una contrasenya.  
![imagen7](img/7.png)
- Al final de l’arxiu de configuració `/etc/ssh/sshd_config` afegirem la següent línia.  
![imagen8](img/8.png)
- Després farem login localment amb l’usuari *root*.  
![imagen9](img/9.png)
- Intentarem fer SSH des de la nostra màquina Windows amb l’usuari *root* i veurem que ens retorna *access denied*.  
![imagen10](img/10.png)
- Amb la següent comanda a la nostra màquina Windows generarem un parell de claus RSA.  
![imagen11](img/11.png)
- Després, amb la comanda `ls`, comprovarem que tenim els arxius necessaris. L’arxiu que hem de copiar al nostre servidor és el que acaba en `.pub`. El copiarem amb la comanda `scp`.  
![imagen12](img/12.png)
![imagen13](img/13.png)
- Crearem al nostre servidor Linux el següent arxiu dins la carpeta `.ssh`:
![imagen14](img/14.png)
- A continuació, copiarem dins d’aquest arxiu la clau `id_rsa.pub`.
![imagen15](img/15.png)
- Comprovarem des de la màquina Windows 11 que podem fer SSH sense necessitat d’introduir la contrasenya.  
![imagen16](img/16.png)
- Per poder tenir el nostre servidor OpenSSH a Windows 11, anirem a:  
- **Configuració → Sistema → Característiques opcionals**  
   Premem el botó blau **"Veure característiques"**.  
- Dins d’aquest apartat cercarem **OpenSSH Server**, marcarem la casella i premem **Afegeix**.  
![imagen17](img/17.png) 
- Per encendre el servei SSH:  
![imagen18](img/18.png)
- Per fer que s'activi automàticament a l’inici:  
![imagen19](img/19.png)

- Com podem veure, si fem una connexió SSH ens podrem connectar de Linux a Windows.
![imagen20](img/20.png)
![imagen21](img/21.png)
- Si no podem establir la connexió SSH, caldrà deshabilitar temporalment el firewall de Windows.

- A la nostra màquina Windows executarem la següent comanda. **NO TANQUEM AQUESTA CONNEXIÓ SSH.**

- Si afegim l’opció `-D` a la comanda SSH, es crea un proxy SOCKS dinàmic al port que especifiquem.  
  \`\`\`bash  
  ssh \-D 9876 usuari@192.168.56.102  
  \`\`\`  
![imagen22](img/22.png)
- Entrarem a **Opcions d’Internet** i seguirem els passos per crear el túnel SSH.  
![imagen23](img/23.png)
- Anirem a:  
- **Connexions → Configuració de LAN**  
![imagen24](img/24.png)
- Deixarem les opcions tal com apareixen a la captura i premem **Opcions avançades**.  
![imagen25](img/25.png)
- A l’apartat *SOCKS*, posarem la IP de la nostra màquina local (client SSH) i el port **9876**. Finalment, acceptarem tots els canvis.  
![imagen26](img/26.png)
- Instal·larem l’aplicació [Wireshark](https://www.wireshark.org/) a Windows 11\.

- Podrem apreciar com la informació viatja encriptada.  
![imagen28](img/28.png)

