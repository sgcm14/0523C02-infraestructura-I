Creación de bucket S3
=========

**Objetivo**

Creación de un Bucket S3 y configurado para hostear un sitio web estáti

Creación del bucket S3

Ingresamos en el buscador S3, y luego haremos clic en el Servicio S3 Almacenamiento
escalable en la nube

Luego buscaremos el botón Crear bucket.

Deberemos darle un nombre a nuestro Bucket, el mismo será global en toda la red de
AWS y no podrá haber 2 buckets con el mismo nombre

En Configuración de bloqueo de acceso público para este bucket deberemos
destildar Bloquear todo el acceso público.

Luego hacer clic en Crear bucket.
Luego seleccionaremos nuestro bucket de la lista de buckets creados, ingresamos y
cargamos los siguientes archivos

Cargar las carpetas una por una, luego hacer clic en el botón Cargar.
Luego iremos a la pestaña Propiedades, al fondo de la pantalla, donde dice
Alojamiento de sitios web estáticos y haremos clic en Editar.
Vamos a habilitar el alojamiento de sitios web estáticos y agregaremos index.html en
Documento de índice

Luego haremos clic en Guardar cambios.
Y copiaremos la dirección asignada.

Si ingresamos la dirección en nuestro navegador, NO podremos ingresar; para hacerlo,
deberemos definir unas políticas en nuestro bucket.

Para lograr nuestro objetivo, iremos a la pestaña Permisos y haremos clic en Editar
Política de bucket

A continuación, abriremos el Generador de políticas, copiándonos previamente el arn
del bucket.

En el Generador de políticas, deberemos dejarlo de esta manera:
Step 1: seleccionar S3 Bucket Policy.
Step 2:
- Principal: *
- Actions: GetObject
- Amazon Resource Name (ARN): arn:aws:s3:::websitebucketdh

Luego, hacer clic en Add Statement >

Esto generará una nueva política de acceso en formato JSON, la cual deberemos
copiar y pegar en la pantalla anterior agregando /* al Resource.

Luego, clic en Guardar cambios.
Como último paso, podemos ingresar nuevamente a la dirección del bucket
previamente copiada y veremos que ahora el sitio está accesible.


**Realizado por :** Sammy Gigi Cantoral Montejo (sgcm14)

<img src ="https://raw.githubusercontent.com/sgcm14/sgcm14/main/sammy.jpg" width="200">