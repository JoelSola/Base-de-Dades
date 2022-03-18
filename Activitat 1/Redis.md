# Instal·lació

- Primer de tot actualitzem els Repositoris:

![R1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Redis1(estesi).png)
![R2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Redis1.png)
U
- Una vegada actualitzat, instalarem el Redis

![R3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis3(3).png)
![R4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Redis3.png)

- Ara el procés d'instalació ja ha acabat, només faltaria activar el Redis amb la següent comanda

![R5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis5.png)

- Quan hagem acabat de activar el Redis hem de configurar el Redis per que es pugi accedir de forma remota, posarem **"nano /etc/redis.conf"** per accedir a la configuracio, una vegada dintre haurem de trobar la linia on posa **bind 127.0.0.1"**

![R6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis6.png)

- Un cop dintre només haurem de modificar el **"127.0.0.1"** per **"0.0.0.0"**

![R7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis7.png)

- Per a que els canvis anteriors siguin efectius el que haurem de fer serà posar la següent comanda

![R8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis8.png)

- Per comprovar si hem establert connexiò farem ping amb la seguent comanda

![R9](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis9.png)

Per accedir remotament al servidor hi haurà que modificar el Firewall amb les següents comandes

![R10](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis10.png)
![R11](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis11.png)

En aquest punt ja podriem connectar-nos amb el servidor

![R12](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/redis12.png)

![R13]()

![R14]()
