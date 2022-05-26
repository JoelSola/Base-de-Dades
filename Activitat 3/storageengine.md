# STORAGE ENGINE

## Exercicis:

## - Exercici 1

### 1.1

**Indica quins són els motors d’emmagatzematge que pots utilitzar (quins estan actius)? Mostra al comanda utilitzada i el resultat d’aquesta.**

- Els motors d'emmagatzematge que estan actius son tots els següents menys el **FEDERATED**, per saber-los hi ha que posar la següent comanda:

![1.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.1.png)

![1.1 (2)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.1%20(2).png)

### 1.2

**Com puc saber quin és el motor d’emmagatzematge per defecte. Mostra com canviar aquest
paràmetre de tal manera que les noves taules que creem a la BD per defecte utilitzin el motor
MyISAM?**
- Com podem veure en la primera imatge anterior, veiem que el motor d'emmagatzematge per defecte és **InnoDB**.

- Per canviar el motor d'emmagatzematge per defecte a MyISAM posem el següent:

![1.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.2.png)

### 1.3

**Com podem saber quin és el motor d'emmagatzematge per defecte?**

- Amb el que em fet al exercici **1.1**.

### 1.4

**Explica els passos per instal·lar i activar l'ENGINE MyRocks. MyRocks és un motor d'emmagatzematge per MySQL basat en RocksDB (SGBD incrustat de tipus clau-valor). Aquest tipus d’emmagatzematge està optimitzat per ser molt eficient en les escriptures amb lectures
acceptables.**

- Descarreguem el repositori:

![1.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.4.png)

- Activem el MyRocks:

![1.4 (2)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.4%20(2).png)

- Llavors com podem comprovar en la següent imatge ja el tenim llest:

![1.4 (3)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/1.4%20(3).png)


## - Exercici 2

**Documenta i posa exemple de com utilitzar ENGINE CSV.**

![2.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/2.1.png)

![2.1 (2)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/2.1%20(2).png)


## - Exercici 4

**Desactiva l’opció que ve per defecte de innodb_file_per_table**

![4.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.1.png)

- Y reiniciem el mysql posant: **service mysql restart**

**Quins són els permisos i l'usuari i grup de la carpeta que conté el directori de dades (datadir**

![4.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.2.png)

**Mostra quina és la mida del tablespace de sistema (System Tablespace). Per què té aquesta 
mida inicial?**

![4.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.3.png)

**Importa la BD Sakila com a taules InnoDB (https://dev.mysql.com/doc/index-other.html)**

- Primer descarreguem l'arxiu mitjançant web:

![4.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%202/Imatges/5.png)

- Després extraiem el contingut:

![4.4(2)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.4.png)

- Després creem la estructura de la base de dades:

![4.4(3)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.4(2).png)

![4.4(4)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.4(3).png)

- Com podem veure ja la tenim:

![4.4(5)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.4(4).png)

**Quin/quins són els fitxers de dades? A on es troben i quina és la seva mida?**

![4.5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.5.png)

**Canvia la configuració del MySQL per:**
- **Canviar la localització del directori de dades a /hd-mysql/**

- Creem la carpeta

![4.6.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.6.1.png)

- Dins del fitxer **my.cnf** posem els parametres innodb_data_home_dir | innodb_data_file_path | innodb_log_group_home_dir y li asignem la nova localització incloent el datadir

![4.6.1(2)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.6.1(2).png)

![4.6.1(3)](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/4.6.1(3).png)


## - Exercici 5

**Crea un tablespace anomenat 'ts1' situat a /discs-mysql/disc1/ i col·loca les taules 
actor, address i category de la BD Sakila.**

- Creem la tablespace **ts1**

![6.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.2.png)

- Asignem a les taules **actor**, **address** i **category** la tablespace **ts1**

![6.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.4.png)

**Crea un altre tablespace anomenat 'ts2' situat a /discs-mysql/disc2/ i col·loca-hi la 
resta de taules.**


 - Creem la tablespace **ts2**

![6.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.3.png)

- Asignem a les taules **city**, **country**, **customer**, **film**, **inventory**, **language**, **payment**, **rental**, **staff** i **store** la tablespace **ts2**


![6.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.6.png)

- (No he posat les de més perquè hi hauria moltes captures)

- Podem fer sentencies DML:

![6.5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.7.png)

![6.6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/6.8.png)


## - Exercici 5

**Com podem comprovar (Innodb Log Checkpointing):**

![7.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/7.1.png)

![7.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%203/Imatges/7.2.png)

**• LSN (Log Sequence Number)**








# Webgrafia

1

https://dev.mysql.com/doc/refman/8.0/en/storage-engines.html

2

https://dev.mysql.com/doc/refman/8.0/en/storage-engine-setting.html

3

http://myrocks.io/docs/getting-started/

4

https://www.percona.com/doc/percona-server/8.0/myrocks/install.html

activitat 2

1

https://dev.mysql.com/doc/refman/8.0/en/csv-storage-engine.html

activitat 4

1

https://dba.stackexchange.com/questions/61116/migrate-from-innodb-file-per-table-to-off-in-mysql

2

https://dev.mysql.com/doc/mysql-secure-deployment-guide/5.7/en/secure-deployment-permissions.html

3

https://dev.mysql.com/doc/refman/5.6/en/innodb-system-tablespace.html
https://dev.mysql.com/doc/refman/8.0/en/innodb-init-startup-configuration.html

4

Canviar localització

https://www.digitalocean.com/community/tutorials/how-to-move-a-mysql-data-directory-to-a-new-location-on-ubuntu-16-04

