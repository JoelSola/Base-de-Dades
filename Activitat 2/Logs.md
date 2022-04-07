
https://support.cpanel.net/hc/en-us/articles/360051031694-Enable-MySQL-General-Query-Log

# Exercicis

1. 

**Quins són els logs activats per defecte? Crea un fitxer de configuració anomenat 
logs.cnf a on:**

**Activa els logs que no ho estiguin per defecte i indica les configuracions necessàries 
per activar-los. Indica les rutes dels fitxer de log de General, Slow Query i Binary. Quins 
paràmetres has creat/modificat?**

Com podem veure en les imatges següents l'unic Log activat per defecte és el **'Binary Log'**, el **'General Log'** i el **'Slow Query Log'** haurem d'activarlos

![General Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.1.png)

![Slow Query Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.2.png)

![Binary Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.3.png)

En primer lloc el que haurem de fer serà crear un fitxer anomenat **'logs.cnf'** dins d'una carpeta que es digui **'percona'**

![Creacio Fitxer i Carpeta](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.4.png)

Dins d'aquest fitxer escriurem el següent per activar el **'General Log'**

![General Log 2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.5.png)

Per a que el que haguem escrit anteriorment sigui efectiu haurem d'anar al directori **'etc'** i obrir l'arxiu **'my.cnf'**, abaix d'on posa **'[mysqld]'** posarem !include i la localització del nostre fitxer **'logs.cnf'**, això ho farem per vincular el nostre fitxer amb el fitxer de configuració **'my.cnf'**

![include directory](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.6.png)

Y una vegada fet aquests passos haurem de reiniciar el mysql

Llavors comprovem s'hi han sigut efectius els canvis

![Comprovacio General Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.7.png)


1
https://support.cpanel.net/hc/en-us/articles/360051031694-Enable-MySQL-General-Query-Log
https://docs.cpanel.net/knowledge-base/sql/how-to-enable-the-slow-query-log-in-mysql-or-mariadb/
https://www.thegeekdiary.com/configuring-mysqld-to-log-slow-queries/
https://stackoverflow.com/questions/15695937/how-can-i-add-an-extra-configuration-file-for-mysql-my-cnf
3
https://stackoverflow.com/questions/62893433/disable-binary-logging-in-mysql-8-for-windows
