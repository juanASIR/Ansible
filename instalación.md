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
![1](/Ansible/Imagenes/1.PNG)
