# 🐬 Instalación de MySQL

- En primer lugar, vamos a la web y descargamos MySQL mediante el siguiente comando:

![mysql1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/mysql1.1.png)

- En segundo lugar instalamos MySQL:

![mysql2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/mysql2.png)

- Después tenemos que deshabilitar el módulo mysql:

![mysql3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/mysql3.png)

- Por último, una vez deshabilitado MySQL podemos instalarlo:

![mysql4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/mysql4.png)

Solo pude hacer captura de esto porque no podía subir arriba:

![mysql5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/mysql5.png)

## ❓ Preguntas

**¿Dónde se encuentran físicamente los archivos de datos?**

- Los archivos de datos se encuentran en el directorio **"/var/lib/mysql/"**.

**¿Dónde se encuentra el archivo de configuración? ¿Cuál es su contenido?**

- El archivo de configuración se encuentra en el directorio **"/etc/my.cnf"**. El contenido del archivo de configuración es el siguiente:

![p2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/pregunta%20MySQL%202.1.png)
![p22](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/pregunta%20MySQL%202.2.png)

**El proceso de mysqld escucha en el puerto 3306. ¿Qué modificación/pasos serían necesarios para cambiar este puerto a 33306 por ejemplo? Importante: No realices los cambios. Solo indica los pasos que harías.**

- Primero deshabilitaríamos el **"mysqld"**.

![port1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port2.1.png)

- Abrimos el archivo **"my.cnf"**.

![port2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port2.3.png)








