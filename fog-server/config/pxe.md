# Arranque PXE en FOG Project

El arranque por PXE permite iniciar equipos desde la red para desplegar imágenes, capturar sistemas o ejecutar herramientas.
El proceso depende de la integración entre DHCP externo, TFTP, iPXE y el propio servidor FOG.


## 1. 1. Flujo de arranque PXE

El proceso completo es:

El cliente arranca desde red (PXE).

Solicita la configuración de red al servidor DHCP externo (core-linux - 192.168.100.10).

El DHCP entrega:

IP del cliente

Gateway

Servidor TFTP (Fog server - 192.168.100.13)

Archivo de arranque → undionly.kpxe (BIOS) o ipxe.efi (UEFI)

El cliente descarga el bootloader desde TFTP.

El iPXE se ejecuta y se conecta via HTTP a ```http://192.168.100.13/fog/service/ipxe/boot.php```

FOG revisa si el host tiene tareas pendientes.

Si hubiese alguna tarea asignada, esta se ejecuta. Si no la hubiese se muestraría el menú PXE.

<img width="1021" height="348" alt="image" src="https://github.com/user-attachments/assets/77647bf7-ccdd-4de0-8566-265a5ef3f3d7" />
