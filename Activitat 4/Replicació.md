# 🔄 Replicación

## Ejercicios:

## - Actividad 1

### CONFIGURACIÓN MASTER

**Verifica que el parámetro server-id tiene un valor numérico (por defecto es 1).**

- Para ver el valor numérico que tiene el server-id ponemos el siguiente comando:

![1.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.1.png)

**Haz un FLUSH DE LOS LOGS utilizando el comando FLUSH LOGS dentro de MySQL**

- Hacemos un FLUSH LOG:

![1.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.2.png)

**Realiza una comprobación de los logs como master mediante SHOW MASTER LOGS**

- Nos sale lo siguiente:

![1.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.3.png)

**Realiza una copia de la máquina virtual donde tengas SGBD MySQL. Esta nueva máquina será la que hará de esclava.**

**Averigua cuál es la IP de cada una de las máquinas (master, slave)**

Creamos otro servidor y a partir del comando **ifconfig** podemos saber la dirección IP de nuestra máquina

MASTER

![master](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/ordenador%20entrada.png)

SLAVE

![slave](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/ordenador%20salida.png)

**Crea un backup de la BD en la máquina master utilizando**

- Hacemos la siguiente comando:

![1.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.4.png)

**Edita el archivo master_backup.sql y busca la línea que comience por --CHANGE MASTER TO.... y busca los valores MASTER_LOG_FILE y MASTER_LOG_POS.**

- Editamos el siguiente archivo:

![1.5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.5.png)

- Dentro de este archivo podemos encontrar esta línea:

![1.6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.6.png)

!

### SLAVE

**Para el servicio de MySQL.**

![1.7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.7.png)

**Comenta los parámetros log-bin y binlog_format. De esta manera desactivaremos el sistema de log-bin**

![1.8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.9.png)

**Asigna un valor al parámetro server-id (diferente que el del Master)**

Dentro del archivo **/etc/my.cnf** abajo de **[mysqld]** ponemos **server_id = (numero diferente que el del Master)**

**Vuelve a encender el servicio MySQL.**

![1.10](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.10.png)

### MASTER

**Añade el usuario slave con la IP de la máquina slave**

- Cambiamos las credenciales de la contraseña para poder poner **patata**

![1.11](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.12.png)

**Añade el permiso de REPLICATION SLAVE al usuario que acabas de crear.**

![1.12](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.13.png)

![1.13](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.14.png)

**En la máquina SLAVE ejecuta la siguiente comando ayudándote de los datos del paso 3 y 4**

- Antes de hacer este paso lo que haremos será deshabilitar el firewall en el Slave y en el Master

![Firewall](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/desactivar%20firewall.png)

- También modificaremos el usuario slave en la máquina Master, pondremos

**ALTER USER 'slave'@'192.168.56.109' IDENTIFIED WITH mysql_native_password BY 'patata';**

- Entonces ya podremos hacer este paso

![1.14](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.15.png)

- Entonces ponemos **START SLAVE;** y vemos en **SHOW SLAVE STATUS \G;** para ver si todo está correcto. Si todo ha salido bien solo haría falta crear una base de datos en el master y ver en el Slave si está creada

![1.15](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%204/Imatges/1.16.png)

# 📚 Webgrafía

https://stackoverflow.com/questions/49194719/authentication-plugin-caching-sha2-password-cannot-be-loaded
