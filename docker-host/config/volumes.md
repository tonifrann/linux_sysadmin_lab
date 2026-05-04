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

<img width="1021" height="46" alt="image" src="https://github.com/user-attachments/assets/ab3d7155-7ab9-40fd-95e6-b4f5334204c2" />



## 3. Persistencia de datos

Se accede al contenedor y se crean datos de prueba dentro del volumen:

<img width="1023" height="30" alt="image" src="https://github.com/user-attachments/assets/309213ef-d062-4066-9037-4a4e5d3f60b2" />


Se detiene y se elimina el contenedor:

<img width="1022" height="76" alt="image" src="https://github.com/user-attachments/assets/7d0bd578-73a2-4190-b13d-13357ab77761" />


Se crea un nuevo contenedor usando el mismo volumen y se comprueba que los datos siguen estando, validando así la persistencia:

<img width="1021" height="67" alt="image" src="https://github.com/user-attachments/assets/7bfb72f1-b18a-44cc-b911-12532754f132" />


## 4. Resultado

Los datos han persistido correctamente entre contenedores después de eliminarlos, gracias a que se han utilizado volúmenes Docker. 
