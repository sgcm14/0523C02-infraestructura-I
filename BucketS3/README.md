Creación de bucket S3
=========

**Objetivo:**

Creación de un Bucket S3 y configurado para hostear un sitio web estático

Creación del bucket S3:

Ingresamos en el buscador S3, y luego haremos clic en el Servicio S3 Almacenamiento escalable en la nube

Luego buscaremos el botón Crear bucket.
![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura1.PNG)
> Pantalla de Crear bucket

Deberemos darle un nombre a nuestro Bucket, el mismo será global en toda la red de AWS y no podrá haber 2 buckets con el mismo nombre

En Configuración de bloqueo de acceso público para este bucket deberemos
destildar Bloquear todo el acceso público.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura2.PNG)
> Pantalla de Crear bucket


Luego hacer clic en Crear bucket.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura3.PNG)
> Pantalla de Crear bucket

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura4.PNG)
> Pantalla de Crear bucket

Luego seleccionaremos nuestro bucket de la lista de buckets creados, ingresamos y cargamos los siguientes archivos

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura5.PNG)
> Pantalla de Crear bucket - cargar

Cargar las carpetas una por una, luego hacer clic en el botón Cargar.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura6.PNG)
> Pantalla de Crear bucket - cargar

Luego iremos a la pestaña Propiedades, al fondo de la pantalla, donde dice
Alojamiento de sitios web estáticos y haremos clic en Editar.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura7.PNG)
> Pantalla de Crear bucket - bucket creado

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura8.PNG)
>  Pantalla de Crear bucket - bucket creado - propiedades

Vamos a habilitar el alojamiento de sitios web estáticos y agregaremos index.html en Documento de índice

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura9.PNG)
>  Pantalla de Crear bucket - bucket creado - propiedades

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura10.PNG)
>  Pantalla de Crear bucket - bucket creado - propiedades


Luego haremos clic en Guardar cambios.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura11.PNG)
>  Pantalla de Crear bucket - bucket creado - propiedades


Y copiaremos la dirección asignada.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura12.PNG)
>  Pantalla de Crear bucket - bucket creado - propiedades

Si ingresamos la dirección en nuestro navegador, NO podremos ingresar; para hacerlo, deberemos definir unas políticas en nuestro bucket.

Para lograr nuestro objetivo, iremos a la pestaña Permisos y haremos clic en Editar Política de bucket

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura13.PNG)
>  Pantalla de Crear bucket 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura14.PNG)
>  Pantalla de Crear bucket 


A continuación, abriremos el Generador de políticas, copiándonos previamente el arn del bucket.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura15.PNG)
>  Pantalla de Crear bucket 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura16.PNG)
>  Pantalla de Crear bucket 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura17.PNG)
>  Pantalla de Crear bucket 

En el Generador de políticas, deberemos dejarlo de esta manera:

Step 1: seleccionar S3 Bucket Policy.

Step 2:
- Principal: *
- Actions: GetObject
- Amazon Resource Name (ARN): arn:aws:s3:::websitebucketdh

Luego, hacer clic en Add Statement >

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura18.PNG)
>  Pantalla de Crear bucket 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura19.PNG)
>  Pantalla de Crear bucket 

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura20.PNG)
>  Pantalla de Crear bucket 

Esto generará una nueva política de acceso en formato JSON, la cual deberemos copiar y pegar en la pantalla anterior agregando /* al Resource.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura21.PNG)
>  Pantalla de Crear bucket 

Luego, clic en Guardar cambios.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura23.PNG)
>  Pantalla de Crear bucket 

Como último paso, podemos ingresar nuevamente a la dirección del bucket
previamente copiada y veremos que ahora el sitio está accesible.

![](https://raw.githubusercontent.com/sgcm14/0523C02-infraestructura-I/main/BucketS3/Captura24.PNG)
>  Pantalla de bucket desplegado


**Realizado por :** Sammy Gigi Cantoral Montejo (sgcm14)

<img src ="https://raw.githubusercontent.com/sgcm14/sgcm14/main/sammy.jpg" width="200">