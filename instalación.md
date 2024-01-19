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

