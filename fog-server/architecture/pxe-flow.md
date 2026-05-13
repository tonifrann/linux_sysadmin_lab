# Flujo de arranque PXE

## 1. Inicio del cliente PXE

El equipo cliente arranca desde la red usandoPXE (Preboot Execution Environment) desde BIOS o UEFI.

La tarjeta de red pide la configuración de la red automáticamente mediante DHCP.


## 2. Solicitud DHCP

El cliente PXE envía una petición DHCP para obtener:

- Dirección IP
- Máscara de red
- Gateway
- Servidor de arranque PXE
- Archivo de arranque iPXE


## 3. Descarga de iPXE

El cliente conecta al servicio TFTP del servidor FOG y descarga el bootloader iPXE.

Archivos habituales:

undionly.kpxe → BIOS Legacy
ipxe.efi → UEFI


## 4. Conexión con FOG

Una vez que se ha cargado iPXE, el cliente se conecta con el servidor FOG mediante HTTP.

FOG comprueba automáticamente si el host tiene tareas pendientes asignadas.


## 5. Flujo de ejecución

```Sin tareas asignadas```

FOG muestra el menú de arranque PXE mostrando estas opciones:

- Boot from disk
- Memtest
- Registro del host en el inventario
- Deploy Image
- Multicasting
- Hardware compatibility test


```Con tareas asignadas```

FOG omite el menú PXE y ejecuta automáticamente la unas de las siguientes tareas programadas:

- Deploy Image
- Capture Image


## 6. Carga del entorno Linux FOS

FOG descarga el entorno Linux FOS (FOG Operating System), un entorno temporal que permite:

- Acceder al disco del cliente
- Capturar imágenes
- Desplegar imágenes
- Ejecutar automatizaciones


## 7. Montaje del almacenamiento NFS

El cliente monta el recurso NFS exportado por el servidor FOG, normalmente en la ruta ```/images```


## 8. Operación de imagen

- Capture

Se genera una imagen del sistema cliente y se almacena en el servidor FOG.

- Deploy

Se despliega una imagen existente sobre el equipo cliente.


## 9. Automatización post-despliegue

Al finalizar el despliegue, FOG puede ejecutar:

- Snapins de PowerShell y Batch
- Instalación de software
- Configuración del sistema (nombre del equipo, red, dominio, etc)
- Scripts SYSTEM ejecutados sin sesión iniciada


FOG permite automatizar tareas tanto durante como después del despliegue en cualquier host registrado.


## 10. Finalización

El equipo cliente se reinicia automáticamente tras completar la operación.

El sistema operativo queda operativo con la imagen desplegada y las automatizaciones aplicadas.
