# REPLICACIÓ

## Exercicis:

## - Activitat 1

### CONFIGURACIÓ MASTER

**Verifica que el paràmetre server-id té un valor numèric (per defecte és 1).**

- Per veure el valor numeric que té el server-id posem la següent comanda:

![1.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.1.png)

**Fes un FLUSH DELS LOGS utilitzant la comanda FLUSH LOGS dins del MySQL**

- Fem un FLUSH LOG:

![1.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.2.png)

**Realitza una comprovació dels logs com a master mitjançant SHOW MASTER LOGS**

- Em surt el següent:

![1.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.3.png)

**Realitza una còpia de la màquina virtual a on tinguis SGBD MySQL. Aquesta nova màquina serà 
que farà d'eslau.**

**Esbrina quina IP tenen cadascuna de les màquines (master, slave)**

Creem un altre servidor i a partir de la comanda **ifconfig** podem saber la adreça ip de la nostra maquina

MASTER

![master](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/ordenador%20entrada.png)

SLAVE 

![slave](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/ordenador%20salida.png)

**Crea un backup de la BD a la màquina master utilitzant**

- Fem la següent comanda:

![1.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.4.png)

**Edita el fitxer master_backup.sql i busca la línia que comenci per --CHANGE MASTER TO.... i 
busca els valors MASTER_LOG_FILE i MASTER_LOG_POS.**

- Editem el següent fitxer:

![1.5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.5.png)

- Dins d'aquest fitxer podem trobar aquesta linia:

![1.6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.6.png)

!


### SLAVE

**Para el servei de MySQL.**

![1.7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.7.png)

**Comenta els paràmetres log-bin i binlog_format. D'aquesta manera 
desactivarem el sistema de log-bin**

![1.8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.9.png)

**Assigna un valor al paràmetre server-id (diferent que el del Master)**

Dins del fitxer **/etc/my.cnf** abaix de **[mysqld]** posem **server_id = (numero diferent que el del Master)**

**Torna engegar el servei MySQL.**

![1.10](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.10.png)


### MASTER

**Afegeix l'usuari slave amb la IP de la màquina slave**

- Canviem les credencials de la contrasenya per poder posar **patata**

![1.11](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.12.png)

**Afegix el permís de REPLICATION SLAVE a l'usuari que acabes de crear.**

![1.12](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.13.png)

![1.13](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.14.png)

**A la màquina SLAVE executa la següent comanda ajudant-te de les dades del pas 3 i 4**

- Abans de fer aquest pas el que farem serà deshabilitar el firewall al Slave i al Master

![Firewall](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/desactivar%20firewall.png)

- També modificarem l'usuari slave en la maquina Master, posarem 

**ALTER USER 'slave'@'192.168.56.109' IDENTIFIED WITH mysql_native_password BY 'patata';**

- Llavors ja podrem fer aquest pas

![1.14](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.15.png)

- Llavors posem **START SLAVE;** i veiem en **SHOW SLAVE STATUS \G;** per veure si tot esta correct. Si tot a sortit bé només caldria crear una base de dades al master i veure al Slave si esta creada

![1.15](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.16.png)









# Webgrafia

https://stackoverflow.com/questions/49194719/authentication-plugin-caching-sha2-password-cannot-be-loaded
- 







