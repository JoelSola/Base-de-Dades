# 📊 Ejercicios de Logs

## 1.

**¿Cuáles son los logs activados por defecto? Crea un archivo de configuración llamado logs.cnf en el que:**

**Activa los logs que no lo estén por defecto e indica las configuraciones necesarias para activarlos. Indica las rutas de los archivos de log de General, Slow Query y Binary. ¿Qué parámetros has creado/modificado?**

- Como podemos ver en las imágenes siguientes los logs activados por defecto son el **'Error Log'** y el **'Binary Log'**, el **'General Log'** y el **'Slow Query Log'** tendremos que activarlos.

![General Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.1.png)

![Slow Query Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.2.png)

![Binary Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.3.png)

- En primer lugar tendremos que crear un archivo llamado **'logs.cnf'** dentro de una carpeta que se llame **'percona'**

![Creación de archivo y carpeta](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.4.png)

- Dentro de este archivo escribiremos lo siguiente para activar el **'General Log'**

![General Log 2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.5.png)

- Para que lo que hayamos escrito anteriormente sea efectivo tendremos que ir al directorio **'etc'** y abrir el archivo **'my.cnf'**, abajo de donde pone **'[mysqld]'** pondremos !include y la localización de nuestro archivo **'logs.cnf'**, esto lo haremos para vincular nuestro archivo con el archivo de configuración **'my.cnf'**

![include directory](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.6.png)

- Y una vez hechos estos pasos tendremos que reiniciar mysql

![Reiniciar](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.7.png)

- Entonces comprobamos si han sido efectivos los cambios

![Comprobación General Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.8.png)

- A continuación habilitaremos el **'Slow Query Log'**, en primer lugar crearemos una carpeta y pondremos como usuario mysql

![1.9](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.9.png)

- Después nos iremos al archivo de configuración **'logs.cnf'** y pondremos lo siguiente (el último parámetro es opcional ya que sirve para cambiar el tiempo de un **'Slow Query Log'**).

![1.10](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.10.png)

- Para que los cambios sean efectivos reiniciaremos mysql

![Comprobación Slow Query Log](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.7.png)

- Entonces comprobamos si han sido efectivos los cambios

![1.11](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.11.png)

## 2

**Comprueba el estado de las opciones de log que has utilizado mediante una sesión de mysql client.**

![2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/2.png)

## 3

**Modifica el archivo de configuración y desactiva los logs de binary, slow query y general. Nota: Simplemente desactívalos no borres otros parámetros como la ruta de los archivos, etc...**

- En primer lugar tendremos que poner **general_log** igual a cero y el **Slow Query Log** igual a cero, después desactivaremos **Binary Log** poniendo **'skip-log-bin'**

![3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/3.png)

- Para que estos cambios sean efectivos reiniciaremos mysql

![Reiniciar3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/1.7.png)

- Entonces verificaremos si se han desactivado

![3.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/3.1.png)

## 4

**Activa los logs en tiempo de ejecución mediante la sentencia SET GLOBAL. También cambia el destino de log general a una tabla (parámetro log_output). ¿Cuáles son las sentencias que has utilizado? ¿En qué tabla se guardan los datos del general log?**

- En primer lugar iremos dentro de nuestro archivo **logs.cnf** y borraremos la parte donde pone **skip-bin-log**, después reiniciaremos MySQL para que sean efectivos los cambios (los **Binary Logs** los he habilitado de esta manera ya que si se intenta con la sentencia **SET GLOBAL** nos saldrá este error)

![4.tres](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/4.dos.png)

- Después para habilitar el **General Log** lo que haremos será poner lo siguiente

![4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/4.png)

- Para habilitar el **Slow Query Log** pondremos lo siguiente

![4.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/4.2.png)

- Entonces una vez habilitados los tres logs nos faltaría cambiar el **log_output** en formato **table**

![4.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/4.3.png)

## 5

**Carga la BD Sakila localizada en la web**

- En primer lugar para instalar la base de datos **Sakila** lo que haremos será utilizar el **wget** para descargar el archivo **sakila-db.tar.gz** desde la página web

![5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/5.png)

- Una vez descargado tendremos que descomprimir el archivo (hago un dir para verificar que lo he descomprimido)

![5.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/5.1.png)

- Ejecutaremos el archivo **'sakila-schema.sql'** para crear la base de datos y el archivo **'sakila-data.sql'** para completar la creación

![5.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/5.2.png)

![5.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/5.3.png)

## 6

**Cuenta el número de sentencias CREATE TABLE dentro del general log mediante una sentencia SQL.**

- Hay 6 sentencias

![6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/6.png)

## 7

**Ejecuta una query mediante la función SLEEP(11) para que se guarde en el log de Slow Query Log. Muestra el contenido del log demostrándolo.**

En primer lugar creamos la sentencia con **'SLEEP(11)'**

![7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/7.png)

Después hacemos un SELECT del **'Slow Query Log'** y podremos ver que nos sale el log de la sentencia anterior

![7.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/7.1.png)

## 8

**Asegúrate de que el Binary Log esté activado y borra todos los logs anteriores mediante la sentencia RESET MASTER.**

![8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.png)

![8.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.uno.png)

**Crea y borra una base de datos llamada foo**

![8.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.1.png)

**Mediante la sentencia SHOW BINLOG EVENTS lista los events y comprueba las sentencias anteriores en qué archivo de log están.**

- Las sentencias anteriores están en el archivo **'binlog.000001'**

![8.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.2.png)

**Realiza un rotate log mediante la sentencia FLUSH LOGS. ¿Qué realiza exactamente esta sentencia?**

- Esta sentencia cierra y vuelve a abrir todos los logs referentes al servidor

![8.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.3.png)

**Crea y borra otra base de datos como el ejemplo anterior del foo. Pero en este caso nombra la base de datos bar**

![8.5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.4.png)

**Lista todos los archivos de log y los últimos cambios mediante la sentencia SHOW. ¿Qué sentencia has utilizado? Muestra el resultado.**

![8.6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.5.png)

**Borra el primer binary log. ¿Qué sentencia has utilizado?**

- He utilizado la sentencia **'PURGE BINARY LOGS'**

![8.7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.7.png)

- Verificamos que el primer archivo se ha borrado

![8.8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/8.8.png)

**Utiliza el programa mysqlbinlog para mostrar el archivo mysql-bin.000002**

## 9

**¿De qué manera podemos desactivar el binary log solo de una sesión en concreto. Imagínate que eres un administrador de la BD y no quieres que las instrucciones que hagas se graben en el binary_log.**

# 📚 Webgrafía

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
