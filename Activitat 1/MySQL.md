# Instal·lació                                                                                                 

- En primer lloc, anem a la web i descarreguem el MySQL mitjançant la següent comanda:

![mysql1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/mysql1.1.png)

- En segon lloc instalem el MySQL:

![mysql2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/mysql2.png)

- Despres tenim que deshabilitar el modul mysql;

![mysql3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/mysql3.png)

- Per ultim una vegada deshabilitat el mysql podem instalar-lo

![mysql4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/mysql4.png)

Només he pogut fer captura d'aixo perque no podia pujar amunt

![mysql5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/mysql5.png)



# Preguntes

**A on es troben físicament els fitxers de dades?**

- Els fitxers de dades es troben en el directori **"/var/lib/mysql/"**


**A on es troba el fitxer de configuració? Quin és el seu contingut?

- El fitxer de configuració es troba en el directori **"/etc/my.cnf"**. El contingut del fitxer de configuracio es el següent:

![p2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/pregunta%20MySQL%202.1.png)
![p22](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/pregunta%20MySQL%202.2.png)


**El procés de mysqld escolta al port 3306. Quina modificació/passos caldrien fer per canviar 
aquest port a 33306 per exemple? Important: No realitzis els canvis. Només indica els 
passos que faries.

- Primer de tot deshabilitariem el **"mysqld"

![port1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port2.1.png)

- Obrim l'arxiu **"my.cnf"

![port2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port2.3.png)

- Ens portarà al següent fitxer on abaix del tot tindrem que posar **"port=3306"** en el cas que no estigui el **"port=3306"** com ha sigut el meu cas, en el cas que si aparegui posat el **"port=3306"** només hi haurà que cambiar-lo

![port3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port2.2.png)


**Un cop finalitzada la instal·lació i veure que funciona, mostra el resultat de la comanda: (ps -ef | grep mysql)

![p3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/pregunta3.png)









