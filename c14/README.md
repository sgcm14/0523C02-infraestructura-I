Crear una máquina virtual con el servicio Amazon EC2 + WebServer
=========

**Objetivos:**
En el siguiente ejercicio vamos a crear una instancia de tipo Linux en AWS
y luego instalaremos un WebServer - Apache para poder acceder a él.
Nuestra infraestructura tiene que contener los siguientes recursos:
1. VPC x1
2. EC2 x2

Ingresamos en el buscador EC2, y luego haremos clic en el Servicio “EC2
Servidores virtuales en la nube”.

Deberemos darle un nombre a nuestro Servidor

Luego, seleccionamos la imagen “Ubuntu Server 20.04 LTS”.

Dejaremos todo por defecto, salvo la opción Par de claves, en la cual
tendremos que hacer clic en Crear un nuevo par de claves:

Y se nos va a abrir una nueva ventana

Se descargará el par de claves asociadas a la instancia en el formato PEM
en nuestro equipo. Luego haremos clic en "Lanzar instancia”.

A continuación, hacemos clic en el botón “Ver todas las instancias”:

Una vez ejecutada la instancia, debemos ubicar nuestro archivo .pem en
nuestra computadora y abrir el menú contextual con clic derecho en Git
Bash Here

Una vez logueados a nuestra instancia deberemos instalar el servidor
apache. Para eso tendremos que ejecutar los siguientes comandos:

    -sudo apt-get update

    -sudo apt-get install apache2

Para verificar que nuestro servidor está siendo ejecutado tendremos que
hacer: systemctl status apache2. Luego, deberíamos ver la siguiente
devolución:


**Realizado por :** Sammy Gigi Cantoral Montejo (sgcm14)

<img src ="https://raw.githubusercontent.com/sgcm14/sgcm14/main/sammy.jpg" width="200">