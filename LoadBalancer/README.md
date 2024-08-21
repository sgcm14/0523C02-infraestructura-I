AWS + Load Balancer
=========

**Objetivos:**

Balancear la carga de 2 web servers.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Example.PNG)
>  Modelo a construir


**Instrucciones:**

Primero creamos la VPC

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura1.PNG)
>  Pantalla de creación de VPC

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura2.PNG)
>  Pantalla de creación de VPC

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura3.PNG)
>  Pantalla de VPC 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura4.PNG)
>  Pantalla de creación de subred 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura5.PNG)
>  Pantalla de creación de subred 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura6.PNG)
>  Pantalla de creación de subred 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura7.PNG)
>  Pantalla de creación de subred 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura8.PNG)
>  Pantalla de VPC

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura9.PNG)
>  Pantalla de creación de gateway de internet

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura10.PNG)
>  Pantalla de creación de gateway de internet

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura11.PNG)
>  Pantalla de creación de gateway de internet

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura12.PNG)
>  Pantalla de creación de gateway de internet

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura13.PNG)
>  Pantalla de VPC

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura14.PNG)
>  Pantalla de tabla de enrutamiento 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura15.PNG)
>  Pantalla de tabla de enrutamiento 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura16.PNG)
>  Pantalla de VPC 

Crear las instancia en EC2:

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura17.PNG)
>  Pantalla de creación instancia 

Elegimos Ubuntu Server

Seleccionamos el modelo de máquina Family T2.micro (apto para la capa
gratuita).

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura18.PNG)
>  Pantalla de creación instancia  

Vamos a dejar todas las opciones por defecto, pero modificaremos el
security group, agregando Permitir el tráfico HTTP desde internet.
En la opción Par de claves tendremos que hacer clic en Crear un nuevo par
de claves o utilizar alguna que hayamos creado en algún ejercicio anterior
y tengamos guardada en nuestro equipo.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura19.PNG)
>  Pantalla de creación instancia 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura20.PNG)
>  Pantalla de creación instancia 

Corroboramos la configuración de la instancia y hacemos clic en Lanzar
Instancia

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura21.PNG)
>  Pantalla de creación instancia 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura22.PNG)
>  Pantalla de creación instancia  

**Instanciamos un contenedor de Docker:**
En este apartado vamos a necesitar una consola o terminal BASH para
comunicarnos vía SSH. En la actualidad, hay muchos productos disponibles
y depende del sistema operativo que estemos utilizando. Por el momento,
dejamos a nuestro criterio cuál nos parece más cómodo y agradable a la
vista. En este ejemplo, utilizamos Windows 10 con CMDER. En caso de no
tenerlo, se puede descargar de https://cmder.net —recomendamos bajar
la versión full que es totalmente portable—.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura23.PNG)
>  Pantalla de instancia 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura24.PNG)
>  Pantalla de instancia 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura25.PNG)
>  Pantalla de instancia 

Una vez instalado, instanciamos el contenedor yeasy/simple-web: 
        
        sudo docker run -d -p 80:80 yeasy/simple-web:latest


![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura26.PNG)
>  Pantalla de instancia 

Comprobamos que el servicio esté andando. Ingresamos a un explorador y
colocamos la IP de nuestra instancia y nos debe contestar:
Ingresamos nuevamente a la instancia a través del navegador web

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura27.PNG)
>  Pantalla de instancia 

**(repetimos este procedimiento para la segunda instancia en EC2).**

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura28.PNG)
>  Pantalla de creación de instancia 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura29.PNG)
>  Pantalla de creación de instancia 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura30.PNG)
>  Pantalla de creación de instancia 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura31.PNG)
>  Pantalla de creación de instancia 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura32.PNG)
>  Pantalla de instancia 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura33.PNG)
>  Pantalla de instancia 

Una vez que ya tenemos nuestros 2 servidores Web funcionando

Procedemos a crear nuestro balanceador de carga. En el menú de la
izquierda vamos a encontrar la opción

Ahora seleccionamos Balanceador de carga de aplicaciones

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura34.PNG)
>  Pantalla de creación de load balancer 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura35.PNG)
>  Pantalla de creación de load balancer 

En Basic configuration deberemos dejar el balanceador abierto hacia
internet (internet-facing) y funcionando con IPv4

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura36.PNG)
>  Pantalla de creación de load balancer 

En Network mapping seleccionamos la vpc donde están nuestras
instancias y la zona de disponibilidad, en nuestro caso us-east-1a y
us-east-1b.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura37.PNG)
>  Pantalla de creación de load balancer 

En Security groups haremos clic en Create a new security group.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura38.PNG)
>  Pantalla de creación de grupo de seguridad 

Se nos abrirá una nueva ventana y deberemos crear el grupo de
seguridad del balanceador, agregando la regla de entrada que habilita la
escucha del puerto 80 (completar también la descripción)

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura39.PNG)
>  Pantalla de creación de grupo de seguridad  

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura40.PNG)
>  Pantalla de creación de grupo de seguridad 

Luego haremos clic en Crear grupo de seguridad.

Volvemos al menú anterior y asignamos el grupo de seguridad que
creamos al balanceador

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura41.PNG)
>  Pantalla de creación de load balancer 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura42.PNG)
>  Pantalla de creación de grupo de destino

En Listeners and routing deberemos agregar las instancias a las cuales
serán derivadas las peticiones realizadas hacia el Load Balancer, para lo
que tendremos que hacer clic en Create target group, que nos abrirá una
nueva ventana

En Create target group, deberemos asignar un nombre en Target group
name. El resto de las opciones las dejaremos por defecto y haremos clic
en Next.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura43.PNG)
>  Pantalla de creación de grupo de destino

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura44.PNG)
>  Pantalla de creación de grupo de destino 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura45.PNG)
>  Pantalla de creación de grupo de destino

En el paso siguiente deberemos asignar nuestras instancias al target
group y hacer clic en Include as pending below

Creamos el Target Group y volvemos a la creación del Load balancer.
Dentro de Listeners and routing buscamos nuestro target group recién
creado; será necesario primero refrescar con el ícono de la derecha.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura46.PNG)
>  Pantalla de creación de load balancer

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura47.PNG)
>  Pantalla de creación de load balancer

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura48.PNG)
>  Pantalla de creación de load balancer

Luego haremos clic en Create Load balancer:

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura49.PNG)
>  Pantalla de creación de load balancer

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

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura50.PNG)
>  Pantalla de balanceador 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura51.PNG)
>  Pantalla de balanceador 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura52.PNG)
>  Pantalla de grupo de seguridad

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura53.PNG)
>  Pantalla de grupo de seguridad

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura54.PNG)
>  Pantalla de grupo de seguridad

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura55.PNG)
>  Pantalla de grupo de seguridad


¡Felicitaciones, has logrado armar el ambiente de trabajo!


![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura56.PNG)
>  Pantalla de instancia 1

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura57.PNG)
>  Pantalla de instancia 2

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/LoadBalancer/Captura58.PNG)
>  Pantalla de balanceador

**Realizado por :** Sammy Gigi Cantoral Montejo (sgcm14)

<img src ="https://raw.githubusercontent.com/sgcm14/sgcm14/main/sammy.jpg" width="200">