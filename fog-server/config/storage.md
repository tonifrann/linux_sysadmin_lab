# Almacenamiento de imágenes en FOG (NFS)

FOG utiliza NFS (Network File System) como sistema de almacenamiento para capturar, desplegar imágenes y automátizar tareas.

El servidor principal funciona como nodo de almacenamiento y comparte el directorio ```/images``` para que los clientes iPXE puedan leer y escribir en él.


## 1. Estructura del almacenamiento

El almacenamiento es donde FOG:

- Guarda las imágenes de lossistemas operativos
  
- Expone los datos a los clientes mientras se realiza el despliegue
  
- Gestiona la información durante las capturas
  
- Da soporte a tareas automatizadas (snapins y scripts)


## 2. Estructura lógica

FOG organiza el almacenamiento en el directorio ```/images```. Esta estructura es gestionada automáticamente por FOG.

De forma interna, se divide en:

   - dev/ → área temporal durante capturas

   - <nombre_de_la_imagen>/ → imágen final ya procesada

<img width="1023" height="117" alt="image" src="https://github.com/user-attachments/assets/17d4ddef-3210-44e2-8ddc-182f604fe7b0" />


## 3. Uso durante el flujo FOG

El almacenamiento interviene en diferentes momentos:

- Captura: se recibe la imagen desde el cliente y se almacena temporalmente

- Despliegue: el cliente accede a la imagen para restaurarla en l disco

- Snapins: distribución de scripts o software en equipos registrados


## 4. Servicios relacionados

El almacenamiento depende de que los siguientes servicios esten en funcionamiento:

- NFS → compartición de imágenes
- TFTP → arranque PXE
- HTTP → comunicación con la interfaz web
- MariaDB → gestión de tareas y hosts
