# Instal·lacio:

## Registre i subscripció del compte

- Previament hi haurà que suscribir la nostre compte al redhat, el que vaig fer jo:
  Vaig accedir a aquesta ["pagina"](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux?extIdCarryOver=true&sc_cid=701f2000001OH6fAAG)
  
- En segon lloc vaig donar-li on posa **"Try It"** i després vaig seguir el que em va dir.

- Després iniciarem la maquina i posarem el següent:
**subscription-manager register** (Llavors ens demanarà la nostre compte de RedHat)
**subscription-manager refresh** (Per actualizar les dades)
**subscription-manager attach --auto** (per verificar que estem actius en la suscripció)






## Instal·lacio del Percona a la maquina

- Utilitzarem la següent comanda per instalar el Percona repository:

![Instalar Percona repository](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/repository%20install.png)


- Una vegada instalat el repository ho activarem

![2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/sudo%20percona-release%20setup%20ps80.png)

- Per ultim instalarem els paquets

![3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/sudo%20yum%20install%20percona-server-server.png)








### 1

**Un cop realitzada la instal·lació realitza una securització de la mateixa. Quin programa realitza
aquesta tasca? Realitza una securització de la instal·lació indicant que la contrasenya de root
sigui patata.**

Primer de tot utilitzarem aquesta comanda per crear una contraseña:

![Securitzacio1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Securitzacio%201.png)

Despres posarem la segùent comanda i ens demanara la contrasenya que ens a donat anteriorment:

![Securitzacio2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%202.png)

Una vegada posada la contrasenya ens demanarà posar una de nova, es clar amb els requisits per defecte de mysql:

![Securitzacio3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%203.png)

Quan la posem ja podrem entrar al mySQL amb la contrasenya creada per nosaltres:

![Securitzacio3.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%203.5.png)

Posant la segúent comanda podrem veure quins son els requisits minims per defecte de MySQL:

![Securitzacio4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Securitzacio%204.png)

Llavors ara toca cambiar els requisits, amb la segúent comanda cambiarem el nivell de seguretat de la contrasenya:

![Securitzacio5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%205.png)

Amb la segúent comanda cambiarem els digits necessaris per a que validi:

![Securitzacio6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%206.png)

Com podem veure ara respecte l'anterior taula han cambiat dos apartats:

![Securitzacio7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%207.png)

Per ultim podrem cambiar la contrasenya a **patata**:

![Securitzacio8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/securitzacio%208.png)


[PaginaAjuda](https://tecadmin.net/change-mysql-password-policy-level/)








### 2

**Quines són les instruccions per arrancar / verificar status / apagar servei de la base de dades
de Percona Server en el sistema operatiu?**

- Per arrancar Percons-Server:

![Iniciar Percona](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Iniciar%20Percona.png)

- Per verificar status:

![Status](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/Status.png)



- Per apagar servei: (Poner captura)

![Parar Percona](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/parar%20percona.png)


[PaginaAjuda](https://www.percona.com/doc/percona-server/8.0/installation/yum_repo.html)



### 3

**A on es troba i quin nom rep el fitxer de configuració del SGBD Percona Server?**

- El nom que rep el fitxer de configuracio del SGBD Percona Server és **"my.cnf"** i es troba en el directori **"/etc/my.cnf"**

### 4

**A on es troben físicament els fitxers de dades (per defecte). Com ho has sabut?**

- Els fitxers de dades (per defecte) es troben en el directori **"/var/lib/mysql/"**



### 5

**Crea un usuari anomenat asix en el sistema operatiu i en SGBD de tal manera que aquest
usuari del sistema operatiu no hagi d'introduir l'usuari i password cada vegada que cridem al
client mysql?**

- Per crear un usuari i posar-li una contrasenya en el sistema operatiu:

![5.1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.1.png)

![5.2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.2.png)

- Per crear un usuari i posar-li una contrasenya en MySQL a partir del nostre compte **'root'**:
(Com en el primer exercici vaig cambiar els requisits de la politica de seguretat em deixa posar **'patata'**, pero si no em fet anteriorment aquests pasos no ens deixarà)

![5.3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.3.png)

- Per poder comprovar que s'han fet els canvis correctament posarem la següent comanda i ens haurà de sortir l'usuari asix

![5.4](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.4.png)

- Ara per poder accedir al MySQL amb l'usuari **'asix'** sense que ens demani la contrasenya crearem el segúent fitxer

![5.5](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.5.png)

- Posarem el segúent

![5.6](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.6.png)

- Asegurarem el fitxer creat

![5.7](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.6.1.png)

- Comprovarem si podem entrar al MySQL amb l'usuari **'asix'** sense contrasenya

![5.8](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/5.7.png)


[PaginaAjuda](https://tecadmin.net/mysql-commands-without-password-prompt/)

### 6 

**El servei de MySQL (mysqld) escolta al port 3306. Quina modificació/passos caldrien fer per
canviar aquest port a 33306 per exemple? Important: No realitzis els canvis. Només indica els
passos que faries.**

Primer de tot el que tindrem que fer serà parar el MySQL:

![Port1](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port%201.png)

Desprès ens anirem al següent fitxer:

![Port2](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port%203.png)

Ens portarà al següent fitxer on abaix del tot tindrem que posar port=33306 en el cas que no estigui el port=3306 com ha sigut el meu cas, en el cas que si aparegui posat el port=3306 només hi haurà que cambiar-lo

![Port3](https://github.com/JoelSola/Base-de-Dades/blob/main/Activitat%201/Imatges/port%202.png)


### 7

**Ensenya al professor que us podeu connectar al SGBD.**






