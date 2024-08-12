Creación de nuestra primera máquina virtual utilizando el servicio de EC2
=========

**Instrucciones:**

Ingresamos en el buscador EC2, y luego haremos clic en el Servicio “EC2
Servidores virtuales en la nube”:


Luego buscaremos el Lanzador y haremos clic en Lanzar la Instancia.

Tendremos que darle un nombre a nuestro Servidor:

Seleccionamos la imagen “Microsoft Windows Server 2016 Base”:

Seleccionamos las opciones como se ve a continuación:


Dejaremos todo por defecto, salvo la opción "Par de claves", en la que
tendremos que hacer clic en Crear un nuevo par de claves

Se va abrir una nueva ventana y completamos los datos


Se descargará el par de claves asociadas a la instancia en el formato PEM
en nuestro equipo. Luego haremos clic en "Lanzar instancia".

A continuación, haremos clic en el botón “Ver todas las instancias”:

Seleccionamos la instancia, luego hacemos clic en “Actions> Security> Get
Windows password” o “Acciones> Seguridad> Obtener la contraseña de
Windows”:

Subimos nuestro par de claves creado previamente (miclave.pem) y
hacemos clic en Descifrar contraseña.


Esto nos generará un usuario y contraseña que usaremos para
conectarnos a nuestra VM instanciada en AWS. En este caso, el usuario es
administrador y la contraseña está generada automáticamente.

Pulsamos el botón Cerrar y volveremos al panel donde están las VMs. Allí,
haremos clic sobre la que nos queremos conectar y deberemos copiar la
siguiente dirección:




**Realizado por :** Sammy Gigi Cantoral Montejo (sgcm14)

<img src ="https://raw.githubusercontent.com/sgcm14/sgcm14/main/sammy.jpg" width="200">