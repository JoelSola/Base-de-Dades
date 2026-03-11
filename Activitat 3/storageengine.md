# 🗂️ Storage Engines

## - Ejercicio 1

### 1.1

**Indica cuáles son los storage engines que puedes utilizar (cuáles están activos)? Muestra el comando utilizado y el resultado de este.**

- Los storage engines que están activos son todos los siguientes menos el **FEDERATED**, para saberlos hay que poner el siguiente comando:

![1.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.1.png)

![1.1 (2)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.1%20(2).png)

### 1.2

**¿Cómo puedo saber cuál es el storage engine por defecto. Muestra cómo cambiar este parámetro de tal manera que las nuevas tablas que creemos en la BD por defecto utilicen el motor MyISAM?**

- Como podemos ver en la primera imagen anterior, vemos que el storage engine por defecto es **InnoDB**.

- Para cambiar el storage engine por defecto a MyISAM ponemos lo siguiente:

![1.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.2.png)

### 1.3

**¿Cómo podemos saber cuál es el storage engine por defecto?**

- Con lo que hice en el ejercicio **1.1**.

### 1.4

**Explica los pasos para instalar y activar el ENGINE MyRocks. MyRocks es un storage engine para MySQL basado en RocksDB (SGBD incrustado de tipo clave-valor). Este tipo de almacenamiento está optimizado para ser muy eficiente en las escrituras con lecturas aceptables.**

- Descargamos el repositorio:

![1.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.4.png)

- Activamos MyRocks:

![1.4 (2)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.4%20(2).png)

- Entonces como podemos comprobar en la siguiente imagen ya lo tenemos listo:

![1.4 (3)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.4%20(3).png)

## - Ejercicio 2

**Documenta y pon ejemplo de cómo utilizar ENGINE CSV.**

![2.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/2.1.png)

![2.1 (2)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/2.1%20(2).png)

## - Ejercicio 3

**Desactiva la opción que viene por defecto de innodb_file_per_table**

![4.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.1.png)

- Y reiniciamos el mysql poniendo: **service mysql restart**

**¿Cuáles son los permisos y el usuario y grupo de la carpeta que contiene el directorio de datos (datadir)?**

![4.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.2.png)

**Muestra cuál es el tamaño del tablespace de sistema (System Tablespace). ¿Por qué tiene este tamaño inicial?**

![4.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.3.png)

**Importa la BD Sakila como tablas InnoDB (https://dev.mysql.com/doc/index-other.html)**

- Primero descargamos el archivo mediante web:

![4.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/5.png)

- Después extraemos el contenido:

![4.4(2)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.4.png)

- Después creamos la estructura de la base de datos:

![4.4(3)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.4(2).png)

![4.4(4)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.4(3).png)

- Como podemos ver ya la tenemos:

![4.4(5)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.4(4).png)

**¿Cuál/cuáles son los archivos de datos? ¿Dónde se encuentran y cuál es su tamaño?**

![4.5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.5.png)

**Cambia la configuración del MySQL para:**
- **Cambiar la localización del directorio de datos a /hd-mysql/**

- Creamos la carpeta

![4.6.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.6.1.png)

- Dentro del archivo **my.cnf** ponemos los parámetros innodb_data_home_dir | innodb_data_file_path | innodb_log_group_home_dir y le asignamos la nueva localización incluyendo el datadir

![4.6.1(2)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.6.1(2).png)

![4.6.1(3)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.6.1(3).png)

## - Ejercicio 4

**Crea un tablespace llamado 'ts1' situado en /discs-mysql/disc1/ y coloca las tablas actor, address y category de la BD Sakila.**

- Creamos la tablespace **ts1**

![6.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.2.png)

- Asignamos a las tablas **actor**, **address** y **category** la tablespace **ts1**

![6.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.4.png)

**Crea otro tablespace llamado 'ts2' situado en /discs-mysql/disc2/ y colócalo en la resta de tablas.**

- Creamos la tablespace **ts2**

![6.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.3.png)

- Asignamos a las tablas **city**, **country**, **customer**, **film**, **inventory**, **language**, **payment**, **rental**, **staff** y **store** la tablespace **ts2**

![6.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.6.png)

- (No he puesto las de más porque habría muchas capturas)

- Podemos hacer sentencias DML:

![6.5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.7.png)

![6.6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.8.png)

## - Ejercicio 5

**¿Cómo podemos comprobar (Innodb Log Checkpointing):**

![7.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/7.1.png)

![7.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/7.2.png)

**• LSN (Log Sequence Number)**

- Podemos ver que el Log Sequence Number es el primero que podemos ver 27514124

**• El último LSN actualizado a disco**

- Podemos ver que el último LSN actualizado a disco es el mismo 27514124

**• ¿Cuál es el último LSN que se le ha hecho Checkpoint?**

- El último LSN al que se le ha hecho Checkpoint también ha sido el 27514124

# 📚 Webgrafía

1

https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html

2

https://dev.mysql.com/doc/refman/8.0/en/storage-engine-setting.html

3

http://myrocks.io/docs/getting-started/

4

https://www.percona.com/doc/percona-server/8.0/myrocks/install.html

actividad 2

1

https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html

actividad 4

1

https://dba.stackexchange.com/questions/61116/migrate-from-innodb-file-per-table-to-off-in-mysql

2

https://dev.mysql.com/doc/mysql-secure-deployment-guide/5.7/en/secure-deployment-permissions.html

3

https://dev.mysql.com/doc/refman/5.6/en/innodb-system-tablespace.html
https://dev.mysql.com/doc/refman/8.0/en/innodb-init-startup-configuration.html

4

Cambiar localización

https://www.digitalocean.com/community/tutorials/how-to-move-a-mysql-data-directory-to-a-new-location-on-ubuntu-16-04

