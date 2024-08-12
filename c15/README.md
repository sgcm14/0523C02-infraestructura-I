AWS + Load Balancer
=========

**Objetivos**
Balancear la carga de 2 web servers.


**Instrucciones**

Crear una instancia en EC2

Modificamos el número de Instancias a 2:

Elegimos Ubuntu Server

Seleccionamos el modelo de máquina Family T2.micro (apto para la capa
gratuita).

Vamos a dejar todas las opciones por defecto, pero modificaremos el
security group, agregando Permitir el tráfico HTTP desde internet.
En la opción Par de claves tendremos que hacer clic en Crear un nuevo par
de claves o utilizar alguna que hayamos creado en algún ejercicio anterior
y tengamos guardada en nuestro equipo.

Corroboramos la configuración de la instancia y hacemos clic en Lanzar
Instancia

Instanciamos un contenedor de Docker
En este apartado vamos a necesitar una consola o terminal BASH para
comunicarnos vía SSH. En la actualidad, hay muchos productos disponibles
y depende del sistema operativo que estemos utilizando. Por el momento,
dejamos a nuestro criterio cuál nos parece más cómodo y agradable a la
vista. En este ejemplo, utilizamos Windows 10 con CMDER. En caso de no
tenerlo, se puede descargar de https://cmder.net —recomendamos bajar
la versión full que es totalmente portable—.

Una vez instalado, instanciamos el contenedor yeasy/simple-web: sudo
docker run -d -p 80:80 yeasy/simple-web:latest

Comprobamos que el servicio esté andando. Ingresamos a un explorador y
colocamos la IP de nuestra instancia y nos debe contestar:
Ingresamos nuevamente a la instancia a través del navegador web
(repetimos este procedimiento para la segunda instancia en EC2).
Una vez que ya tenemos nuestros 2 servidores Web funcionando

Procedemos a crear nuestro balanceador de carga. En el menú de la
izquierda vamos a encontrar la opción

Ahora seleccionamos Balanceador de carga de aplicaciones

En Basic configuration deberemos dejar el balanceador abierto hacia
internet (internet-facing) y funcionando con IPv4

En Network mapping seleccionamos la vpc donde están nuestras
instancias y la zona de disponibilidad, en nuestro caso us-east-1a y
us-east-1b.

En Security groups haremos clic en Create a new security group.

Se nos abrirá una nueva ventana y deberemos crear el grupo de
seguridad del balanceador, agregando la regla de entrada que habilita la
escucha del puerto 80 (completar también la descripción)

Luego haremos clic en Crear grupo de seguridad.

Volvemos al menú anterior y asignamos el grupo de seguridad que
creamos al balanceador

En Listeners and routing deberemos agregar las instancias a las cuales
serán derivadas las peticiones realizadas hacia el Load Balancer, para lo
que tendremos que hacer clic en Create target group, que nos abrirá una
nueva ventana

En Create target group, deberemos asignar un nombre en Target group
name. El resto de las opciones las dejaremos por defecto y haremos clic
en Next.

En el paso siguiente deberemos asignar nuestras instancias al target
group y hacer clic en Include as pending below

Creamos el Target Group y volvemos a la creación del Load balancer.
Dentro de Listeners and routing buscamos nuestro target group recién
creado; será necesario primero refrescar con el ícono de la derecha.

Luego haremos clic en Create Load balancer:

Luego iremos a View Load balancer y en Descripción podremos ver el
Nombre de DNS asignado al Load balancer; en nuestro caso:
mibalanceador-1148250882.us-east-1.elb.amazonaws.com

Por ahora, podemos ingresar al balanceador con el nombre DNS anterior y
verlo en funcionamiento. Pero todavía se encuentra el acceso a cada
instancia por el puerto 80 desde anywhere y solamente el tráfico debe
dirigirlo al balanceador para que éste reparta.
Para eso, nos dirigimos a una de las instancias y en la pestaña Seguridad
haremos clic en el grupo de seguridad, y luego a Editar reglas de entrada.
Editamos el acceso HTTP solamente al grupo de seguridad del
balanceador. De esta manera, únicamente se puede ingresar al puerto 80
desde el balanceador. Para hacer esto será necesario borrar la regla de
HTTP creada y volver a crearla seleccionando en Origen el Security group
del balanceador

¡Felicitaciones, has logrado armar el ambiente de trabajo!

**Realizado por :** Sammy Gigi Cantoral Montejo (sgcm14)

<img src ="https://raw.githubusercontent.com/sgcm14/sgcm14/main/sammy.jpg" width="200">