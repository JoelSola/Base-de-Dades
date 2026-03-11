# ⚡ Instalación de Redis

- Primero de todo actualizamos los repositorios:

![R1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Redis1(estesi).png)
![R2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Redis1.png)

- Una vez actualizado, instalaremos Redis:

![R3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis3(3).png)
![R4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Redis3.png)

- Ahora el proceso de instalación ya ha acabado, solo faltaría activar Redis con el siguiente comando:

![R5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis5.png)

- Cuando hayamos acabado de activar Redis tenemos que configurar Redis para que se pueda acceder de forma remota, pondremos **"nano /etc/redis.conf"** para acceder a la configuración, una vez dentro tendremos que encontrar la línea que pone **bind 127.0.0.1"**

![R6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis6.png)

- Una vez dentro solo tendremos que modificar el **"127.0.0.1"** por **"0.0.0.0"**

![R7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis7.png)

- Después volveremos al mismo archivo anterior y un poco más abajo de donde encontramos el **bind 127.0.0.1** veremos otra línea que pone **protected-mode yes**

![RO1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redisO2.png)

- Esta línea la editaremos y en lugar de **yes** pondremos **no**

![RO2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Redis03.png)

- Tendremos que reiniciar Redis:

![R8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis8.png)

- Para comprobar si hemos establecido conexión haremos ping con el siguiente comando:

![R9](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis9.png)

Para acceder remotamente al servidor habrá que modificar el Firewall con las siguientes comandos:

![R10](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis10.png)
![R11](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis11.png)

En este punto ya podríamos conectarnos con el servidor.

## ❓ Preguntas

**¿Qué tipo de SGBD es Redis?**

- Redis es un tipo de SGBD NoSQL.

## 📚 Webgrafía

Instalación

[Pagina Instalación](https://linuxconfig.org/install-redis-on-redhat-8)
