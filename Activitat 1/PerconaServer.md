# 🔧 Instalación de Percona Server

## 📝 Registro y suscripción de la cuenta

- Previamente hay que suscribir nuestra cuenta a Red Hat, lo que hice yo:
  Accedí a esta ["página"](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux?extIdCarryOver=true&sc_cid=701f2000001OH6fAAG)

- En segundo lugar di en **"Try It"** y después seguí lo que me dijo.

- Después iniciamos la máquina y ponemos lo siguiente:
  **subscription-manager register** (Entonces nos pedirá nuestra cuenta de Red Hat)
  **subscription-manager refresh** (Para actualizar los datos)
  **subscription-manager attach --auto** (para verificar que estamos activos en la suscripción)

## 🛠️ Instalación de Percona en la máquina

- Utilizaremos el siguiente comando para instalar el repositorio de Percona:

![Instalar repositorio de Percona](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/repository%20install.png)

- Una vez instalado el repositorio lo activaremos:

![2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/sudo%20percona-release%20setup%20ps80.png)

- Por último instalaremos los paquetes:

![3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/sudo%20yum%20install%20percona-server-server.png)

### 1

**Una vez realizada la instalación realiza una securización de la misma. ¿Qué programa realiza esta tarea? Realiza una securización de la instalación indicando que la contraseña de root sea patata.**

Primero de todo utilizaremos esta comando para crear una contraseña:

![Securitzacio1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Securitzacio%201.png)

Después pondremos la siguiente comando y nos pedirá la contraseña que nos ha dado anteriormente:

![Securitzacio2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%202.png)

Una vez puesta la contraseña nos pedirá poner una nueva, es claro con los requisitos por defecto de mysql:

![Securitzacio3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%203.png)

Cuando la ponemos ya podremos entrar al mySQL con la contraseña creada por nosotros:

![Securitzacio3.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%203.5.png)

Poniendo la siguiente comando podremos ver cuáles son los requisitos mínimos por defecto de MySQL:

![Securitzacio4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Securitzacio%204.png)

Entonces ahora toca cambiar los requisitos, con la siguiente comando cambiaremos el nivel de seguridad de la contraseña:

![Securitzacio5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%205.png)

Con la siguiente comando cambiaremos los dígitos necesarios para que valide:

![Securitzacio6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%206.png)

Como podemos ver ahora respecto a la anterior tabla han cambiado dos apartados:

![Securitzacio7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%207.png)

Por último podremos cambiar la contraseña a **patata**:

![Securitzacio8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%208.png)

### 2

**¿Cuáles son las instrucciones para arrancar / verificar status / apagar servicio de la base de datos de Percona Server en el sistema operativo?**

- Para arrancar Percona-Server:

![Iniciar Percona](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Iniciar%20Percona.png)

- Para verificar status:

![Status](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Status.png)

- Para apagar servicio:

![Parar Percona](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/parar%20percona.png)

[PaginaAjuda](https://www.percona.com/doc/percona-server/8.0/installation/yum_repo.html)

### 3

**¿Dónde se encuentra y qué nombre recibe el archivo de configuración del SGBD Percona Server?**

- El nombre que recibe el archivo de configuración del SGBD Percona Server es **"my.cnf"** y se encuentra en el directorio **"/etc/my.cnf"**

### 4

**¿Dónde se encuentran físicamente los archivos de datos (por defecto). ¿Cómo lo has sabido?**

- Los archivos de datos (por defecto) se encuentran en el directorio **"/var/lib/mysql/"**

### 5

**Crea un usuario llamado asix en el sistema operativo y en SGBD de tal manera que este usuario del sistema operativo no haya de introducir el usuario y password cada vez que llamemos al cliente mysql.**

- Para crear un usuario y ponerle una contraseña en el sistema operativo:

![5.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.1.png)

![5.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.2.png)

- Para crear un usuario y ponerle una contraseña en MySQL a partir de nuestro cuenta **'root'**:
(Como en el primer ejercicio cambié los requisitos de la política de seguridad me deja poner **'patata'**, pero si no he hecho anteriormente estos pasos no nos dejará)

![5.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.3.png)

- Para poder comprobar que se han hecho los cambios correctamente pondremos la siguiente comando y nos habrá de salir el usuario **'asix'**

![5.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.4.png)

- Ahora para poder acceder al MySQL con el usuario **'asix'** sin que nos pida la contraseña crearemos el siguiente archivo

![5.5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.5.png)

- Pondremos lo siguiente

![5.6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.6.png)

- Aseguraremos el archivo creado

![5.7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.6.1.png)

- Comprobaremos si podemos entrar al MySQL con el usuario **'asix'** sin contraseña

![5.8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.7.png)

[PaginaAjuda](https://tecadmin.net/mysql-commands-without-password-prompt/)

### 6

**El servicio de MySQL (mysqld) escucha al port 3306. ¿Qué modificación/pasos caldrían hacer para cambiar este port a 33306 por ejemplo? Importante: No realices los cambios. Solo indica los pasos que harías.**

Primero de todo lo que tendremos que hacer será parar el MySQL:

![Port1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port%201.png)

Después nos iremos al siguiente archivo:

![Port2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port%203.png)

Nos llevará al siguiente archivo donde abajo del todo tendremos que poner port=33306 en el caso que no esté el port=3306 como ha sido mi caso, en el caso que si aparezca puesto el port=3306 solo habrá que cambiarlo

![Port3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port%202.png)

### 7

**Enseña al profesor que te puedes conectar al SGBD.**

## 📚 Webgrafía

Ejercicio 1

[Pagina1](https://tecadmin.net/change-mysql-password-policy-level/)

Ejercicio 5

[Pagina2](https://tecadmin.net/mysql-commands-without-password-prompt/)


