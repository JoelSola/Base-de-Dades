# Exercicis

## 1. 

**Quins són els logs activats per defecte? Crea un fitxer de configuració anomenat 
logs.cnf a on:**

**Activa els logs que no ho estiguin per defecte i indica les configuracions necessàries 
per activar-los. Indica les rutes dels fitxer de log de General, Slow Query i Binary. Quins 
paràmetres has creat/modificat?**

- Com podem veure en les imatges següents els Logs activats per defecte és el **'Error Log'** i el **'Binary Log'**, el **'General Log'** i el **'Slow Query Log'** haurem d'activarlos

![General Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.1.png)

![Slow Query Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.2.png)

![Binary Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.3.png)

- En primer lloc el que haurem de fer serà crear un fitxer anomenat **'logs.cnf'** dins d'una carpeta que es digui **'percona'**

![Creacio Fitxer i Carpeta](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.4.png)

- Dins d'aquest fitxer escriurem el següent per activar el **'General Log'**

![General Log 2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.5.png)

- Per a que el que haguem escrit anteriorment sigui efectiu haurem d'anar al directori **'etc'** i obrir l'arxiu **'my.cnf'**, abaix d'on posa **'[mysqld]'** posarem !include i la localització del nostre fitxer **'logs.cnf'**, això ho farem per vincular el nostre fitxer amb el fitxer de configuració **'my.cnf'**

![include directory](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.6.png)

- Y una vegada fet aquests passos haurem de reiniciar el mysql

![Reiniciar](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.7.png)

- Llavors comprovem s'hi han sigut efectius els canvis

![Comprovacio General Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.8.png)

- A continució habilitarem el **'Slow Query Log'**, en primer lloc crearem una carpeta i posarem com usuari mysql 

![1.9](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.9.png)

- Després ens anirem al fitxer de configuracio **'logs.cnf'** i posarem el següent (l'últim parametre és opcional ja que serveix per cambiar el temps d'un **'Slow Query Log'**).

![1.10](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.10.png)

- Per a que els canvis siguin efectius reiniciarem el mysql

![Comprovacio Slow Query Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.7.png)

- Llavors comprovem s'hi han sigut efectius els canvis

![1.11](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.11.png)



## 2

**Comprova l'estat de les opcions de log que has utilitzat mitjançant una sessió de mysql 
client.**

![2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/2.png)



## 3

**Modifica el fitxer de configuració i desactiva els logs de binary, slow query i genral. Nota: 
Simplament desactiva'ls no borris altres paràmetres com la ruta dels fitxers, etc...**

- En primer lloc el que haurem de fer serà posar **general_log** igual a zero i el **Slow Query Log** igual a zero, després desactivarem **Binary Log** posant **'skip-log-bin'**

![3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/3.png)

- Per a que aquests canvis siguin efectius reiniciarem el mysql

![Reiniciar3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.7.png)

- Llavors verificarem si s'han desactivat

![3.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/3.1.png)



## 4

**Activa els logs en temps d'execució mitjançant la sentència SET GLOBAL. També canvia 
el destí de log general a una taula (paràmetre log_output). Quines són les sentències que 
has utilitzat? A quina taula es guarden els dels del general log?**

- En primer lloc anirem dins del nostre fitxer **logs.cnf** i borrarem la part on posa **skip-bin-log**, després reiniciarem el MySQL per a que siguin efectius els canvis (els **Binary Logs** els he habilitat d'aquesta manera ja que si s'intenta amb la sentencia **SET GLOBAL** ens sortirà aquest error)

![4.tres](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/4.dos.png)

- Després per habilitar el **General Log** el que farem serà posar el següent

![4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/4.png)

- Per habilitar el **Slow Query Log** posarem el següent

![4.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/4.2.png)

- Llavors un cop habilitat els tres logs ens faltaria canviar el **log_output** en format **table**

![4.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/4.3.png)



## 5

**Carrega la BD Sakila localitzada a la web**

- En primer lloc per instal·lar la base de dades **Sakila** el que farem serà utilitzar el **wget** per descargar el fitxer **sakila-db.tar.gz** des de la pagina web

![5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/5.png)

- Un cop descarregat haurem de descomprimir el fitxer (faig un dir per verificar que ho he descomprimit)

![5.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/5.1.png)

- Executarem el fitxer **'sakila-schema.sql'** per crear la base de dades i el fitxer **'sakila-data.sql'** per completar la creació

![5.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/5.2.png)

![5.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/5.3.png)


## 6

**Compte el numero de sentències CREATE TABLE dins del general log mitjançant una sentència SQL.**

- Hi han 6 sentencies

![6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/6.png)



## 7

**Executa una query mitjançant la funció SLEEP(11) per tal de que es guardi en el log de 
Slow Query Log. Mostra el contingut del log demostrant-ho.**

En primer lloc creem la sentencia amb **'SLEEP(11)'** 

![7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/7.png)

Després fem un SELECT del **'Slow Query Log'** i podrem veure que ens surt el log de la sentencia anterior

![7.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/7.1.png)



## 8

**Assegura't que el Binary Log estigui activat i borra tots els logs anteriors mitjançant la 
sentència RESET MASTER.**

![8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.png)

![8.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.uno.png)

**Crea i esborra una base de dades anomenada foo**

![8.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.1.png)

**Mitjançant la sentència SHOW BINLOG EVENTS llista els events i comprova les sentències anteriors en quin fitxer de log estan.**

- Les sentències anteriors estan en el fitxer **'binlog.000001'**

![8.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.2.png)

**Realitza un rotate log mitjançant la sentència FLUSH LOGS. Què realitza exactament 
aquesta sentència?**

- Aquesta sentència tanca i torna a obrir tots els logs referents al servidor

![8.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.3.png)

**Crea i esborra una altra base de dades com l'exemple anteior del foo. Però en aquest 
cas anomena la base de dades bar**

![8.5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.4.png)

**Llista tots els fitxers de log i els últims canvis mitjançant la sentència SHOW. Quina 
sentència has utilitzat? Mostra'n el resultat.**

![8.6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.5.png)

**Esborra el primer binary log. Quina sentència has utilitzat?**

- He utillitzat la sentència **'PURGE BINARY LOGS'**

![8.7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.7.png)

- Verifiquem que el primer fitxer s'ha esborrat

![8.8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.8.png)

**Utilitza el programa mysqlbinlog per mostrar el fitxer mysql-bin.000002**



# Webgrafia


### 1
https://support.cpanel.net/hc/en-us/articles/360051031694-Enable-MySQL-General-Query-Log
https://docs.cpanel.net/knowledge-base/sql/how-to-enable-the-slow-query-log-in-mysql-or-mariadb/
https://www.thegeekdiary.com/configuring-mysqld-to-log-slow-queries/
https://stackoverflow.com/questions/15695937/how-can-i-add-an-extra-configuration-file-for-mysql-my-cnf

### 3
https://stackoverflow.com/questions/62893433/disable-binary-logging-in-mysql-8-for-windows

### 4
https://tableplus.com/blog/2018/10/how-to-show-queries-log-in-mysql.html

### 5

https://dev.mysql.com/doc/sakila/en/sakila-installation.html

### 7

https://stackoverflow.com/questions/4284524/how-and-when-to-use-sleep-correctly-in-mysql

### 8

https://dev.mysql.com/doc/refman/8.0/en/purge-binary-logs.html


### SSL

https://linuxhint.com/disable-firewall-centos-8/

