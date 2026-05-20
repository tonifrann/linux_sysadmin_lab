# Gestión de imágenes en FOG

FOG utiliza un sistema de captura y despliegue basado en Partclone para clonar sistemas operativos a través de la red.

Las imágenes se almacenan en el servidor FOG, y se transfieren utilizando NFS durante la captura y el despliegue de imágenes.


## 1. Componentes implicados

El proceso de creación de imagenes implica varios servicios:

* PXE/iPXE, que se encarga del arranque de red del cliente.

* HTTP, que se utiliza para cargar menús y scripts de arranque.

* NFS, que permite la transferencia de imágenes.

* Partclone, que se encarga de capturar y restaurar particiones.

* FOG Scheduler, que gestiona las tareas.


## 2. Flujo de captura

Este es el proceso que sigue la captura de una imagen :

- El cliente arranca por PXE

- iPXE carga el entorno FOS Linux

- El disco es analizado automáticamente

- Partclone captura únicamente los bloques utilizados

- La imagen se comprime y se envía al almacenamiento NFS

<img width="497" height="353" alt="image" src="https://github.com/user-attachments/assets/c8c7737b-d7ac-45e1-a946-e5da01cb99d5" />


## 3. Almacenamiento de las imágenes

Las imágenes se almacenan en el servidor FOG dentro del directorio ```/ìmages```. 

La Estructura tipica es:

- dev/ esárea temporal durante capturas
  
- <nombre_imagen>/ es la imagen final generada, en este caso ```win11_image```

- postdownloadscripts/ donde se guardan los scripts asociados a despliegues
  
<img width="1023" height="336" alt="image" src="https://github.com/user-attachments/assets/332d53f8-2099-4537-b059-48e3e208af44" />


## 4. Flujo de despliegue

El despliegue es el proceso de bolcado de la imagen:

- El cliente arranca por PXE
  
- Se asigna una tarea desde el FOG

- iPXE carga el entorno FOS Linux

- Se descarga la imagen desde NFS
  
- Partclone restaura los bloques en el disco destino

<img width="1359" height="402" alt="image" src="https://github.com/user-attachments/assets/850d4108-6a55-4930-93c2-e3b488d238f8" />




