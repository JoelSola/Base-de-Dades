# Exercicis

**Quins són els logs activats per defecte? Crea un fitxer de configuració anomenat
logs.cnf a on:**

**Activa els logs que no ho estiguin per defecte i indica les configuracions necessàries
per activar-los. Indica les rutes dels fitxer de log de Binary, Slow Query i General. Quins
paràmetres has creat/modificat?**

- Com podem veure en les següents imatges veiem que l'unic activat per defecte es el **"Binary Log"**, el **'General Log'** i el **'Slow Query Log'** hem d'activar-los.

![BL](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Es%20el%20Primero.png)

![GL](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/1.2.png) 

![SL](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/1.3.png)

- Abans de tot crearem un fitxer .cnf anomenat logs així ordenarem en un sol fitxer les ordres que hi posem dels logs. Haurem de fer un include i posar la localització del fitxer **"logs.cnf"** dins del fitxer **"my.cnf"** abaix d'on posa **"[mysqld]"**

![Carpeta](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/1.1.png)
![include dir](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/1.6.png)

- Una vegada fet els anteriors passos ja podrem començar. En primer lloc el que farem per activar el **'General Log'** serà


https://docs.cpanel.net/knowledge-base/sql/how-to-enable-the-slow-query-log-in-mysql-or-mariadb/
https://www.thegeekdiary.com/configuring-mysqld-to-log-slow-queries/
https://stackoverflow.com/questions/15695937/how-can-i-add-an-extra-configuration-file-for-mysql-my-cnf
