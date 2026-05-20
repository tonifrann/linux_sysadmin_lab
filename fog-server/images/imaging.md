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

Durante una captura:

El cliente arranca por PXE
iPXE carga el entorno FOS Linux
El disco es analizado automáticamente
Partclone captura únicamente los bloques utilizados
La imagen se comprime y se envía al almacenamiento NFS

Las imágenes se almacenan en:


<img width="497" height="353" alt="image" src="https://github.com/user-attachments/assets/c8c7737b-d7ac-45e1-a946-e5da01cb99d5" />


<img width="1363" height="404" alt="image" src="https://github.com/user-attachments/assets/49e09102-92f8-4f66-a285-4341a91f1031" />


<img width="1302" height="200" alt="image" src="https://github.com/user-attachments/assets/c283446f-5849-4479-8919-9d9827d0884f" />
