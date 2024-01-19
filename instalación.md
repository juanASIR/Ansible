# Requisitos previos

* Tener acceso a internet (Para descargar paquetes)
* Necesitaremos 3 ordenadores (o MV) ***Linux***
* En nuestro caso, utilizaremos ***una*** MV ***Ubuntu 22.04*** como anfitrión (Donde instalaremos Ansible), y **dos** MV ***Debian 12*** (Donde nos conectaremos remotamente).
* Cada dispositivo tiene que estar actualizado y con ***SSH*** y ***Python*** instalado.
* ***Ansible*** ¡¡ SOLO SE INSTALARÁ EN EL ANFITRIÓN !!
* Las ***claves públicas y privadas*** se generarán en el *** Anfitrión***.
* En VirtualBox, red en ***modo puente*** y el modo promiscuo permitiendo todo, y en este trabajo ***IP DINÁMICA***.

# Instalación

Una vez tenemos las MV instaladas procedemos a su instalación-

### Preparación del Anfitrión

***1. Comprobamos si tenemos instalado SSH y Phtyon***

```
sudo apt update
sudo apt upgrade
sudo apt policy python3
sudo apt install python3
sudo apt policy ssh
sudo apt install openssh-server

```
![1](/Imagenes/1.PNG)

***2. Instalación Ansible***

Accedemos como superusuario.

```
apt install software-properties-common
add-apt-repository --yes --update ppa:ansible/ansible
apt install ansible
apt policy ansible
ansible --version

```

El ***primer comando*** de ese software nos proporciona una abstracción de los repositorios usados. Le permite gestionar fácilmente su distribución e independiente Fuentes de software de proveedores de software.

![2](/Imagenes/2.PNG)

Con el ***segundo comando*** incluimos el PPA (archivo de paquetes personal) oficial del proyecto en la lista de fuentes de su sistema.

![3](/Imagenes/3.PNG)

Con el ***tercer comando*** instalamos ansible.

![4](/Imagenes/4.PNG)

Y por último, los dos últimos comandos nos demuestran que lo tenemos instalado.

![5](/Imagenes/5.PNG)
![6](/Imagenes/6.PNG)

***3. Preparación de los terminales remotos***

Los siguientes pasos se tienen que hacer en cada MV con sus correspondientes datos.

```
nano /etc/hostname
cd /etc/ssh
nano sshd_config
systemctl restart ssh
passwd

```
En primer lugar cambiaremos el nombre del equipo, para que no haya confusiones, para ello utilizamos el siguiente comando. Es necesario reiniciar el equipo para guardar los cambios.

![7](/Imagenes/7.PNG)

Tras esto, nos vamos al archivo de configuración de ssh y permitimos el login del root.

![8](/Imagenes/8.PNG)

![9](/Imagenes/9.PNG)

Reiniciamos ssh, y si queremos para evitar confusiones podemos cambiar la contraseña con el último comando.

![11](/Imagenes/11.PNG)

***4. Creación claves para conexión ssh***

Creamos una clave pública para poder conectarnos con los equipos remotos sin tener que poner las contraseñas cada vez que queramos conectarnos.

```
ssh-keygen
cd .ssh
ssh-copy-id -i id_rsa.pub root@Ip_EquipoRemoto
ssh root@1Ip_EquipoRemoto

```

Generamos una claves pública y una privada, esta clave pública la utilizaremos para poder acceder a equipos remotos sin tener que poner la contraseña cada vez que querramos conectarnos. También hay que tener cuidado, pues un mal uso, permite acceso directo al servidor.

![12](/Imagenes/12.PNG)

Una vez generadas las claves, la copiamos en el equipo remoto via ssh. Las claves se encuentran en .ssh

![13](/Imagenes/13.PNG)

Y por último comprobamos que podemos acceder al equipo remoto sin necesidad de poner la contraseña.

![14](/Imagenes/14.PNG)
