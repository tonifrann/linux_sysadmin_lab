# Docker Volumes

Configuración de volúmenes en Docker para asegurar la persistencia de datos entre reinicios de contenedores.


## 1. Creación de un volumen

Se crea un volumen para almacenar datos persistentes:


## 2. Despliegue de un contenedor con volumen

Se lanza un contenedor de prueba (Nginx) montando el volumen creado en el directorio de datos:

<img ... />

Se verifica que el contenedor está en ejecución:

<img ... />


## 3. Generación de datos

Se accede al contenedor y se crean datos de prueba dentro del volumen:

<img ... />


## 4. Persistencia de datos

Se detiene y elimina el contenedor:

<img ... />

Se vuelve a crear un nuevo contenedor utilizando el mismo volumen:

<img ... />

Se comprueba que los datos siguen disponibles, validando la persistencia:

<img ... />


## Resultado

Se confirma que los datos persisten correctamente entre contenedores gracias al uso de volúmenes Docker.
