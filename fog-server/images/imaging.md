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
