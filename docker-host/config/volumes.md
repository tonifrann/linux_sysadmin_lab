# Docker Volumes

Configuración de volúmenes en Docker para que haya persistencia de datos si hay reinicios en los contenedores.


## 1. Creación de un volumen

Se crea un volumen para guardar datos persistentes:

<img width="1022" height="32" alt="image" src="https://github.com/user-attachments/assets/e34403f5-f4bc-426a-b203-319074462320" />


Se verifica que se ha creado correctamente:

<img width="1023" height="49" alt="image" src="https://github.com/user-attachments/assets/a1b19ac6-d507-4de3-aee7-8ac86de72fde" />


Se comprueba la información del volumen:

<img width="1023" height="192" alt="image" src="https://github.com/user-attachments/assets/b26165f2-9c4c-4a41-8fca-d8e265246eff" />


## 2. Despliegue del volumen en un contenedor

Se lanza un contenedor (Nginx que se descarga automáticamente) y se monta el volumen creado en el directorio de datos:

<img width="1021" height="46" alt="image" src="https://github.com/user-attachments/assets/2452acbe-3894-4460-8daa-d285d4159b5a" />



Se accede al contenedor para verificar de que se ha montado correctamente:

<img width="1023" height="48" alt="image" src="https://github.com/user-attachments/assets/b8182ba2-76ec-452a-a872-5c29da22906c" />


## 3. Persistencia de datos

Se accede al contenedor y se crean datos de prueba dentro del volumen:

<img width="1019" height="33" alt="image" src="https://github.com/user-attachments/assets/d0d60325-a4de-445d-823b-16403a16601e" />

Se detiene y se elimina el contenedor:

<img width="1022" height="79" alt="image" src="https://github.com/user-attachments/assets/c85aefc0-d7e5-442c-8d0f-0430fb055d05" />

Se crea un nuevo contenedor usando el mismo volumen:

<img width="1023" height="128" alt="image" src="https://github.com/user-attachments/assets/171eae18-5b63-4c3e-a917-4deb8576f5c9" />


Se comprueba que los datos siguen disponibles, validando la persistencia:

<img width="1023" height="64" alt="image" src="https://github.com/user-attachments/assets/54fe273e-e7c2-4623-ae56-3c0ea5bfbead" />


## Resultado

Se confirma que los datos persisten correctamente entre contenedores gracias al uso de volúmenes Docker.
