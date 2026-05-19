# Arranque PXE en FOG Project

El arranque por PXE permite iniciar equipos desde la red para desplegar imágenes, capturar sistemas o ejecutar herramientas.
El proceso depende de la integración entre DHCP externo, TFTP, iPXE y el propio servidor FOG.


## 1. Flujo de arranque PXE

El proceso completo es:

1.- El cliente arranca desde red (PXE).

2.- Solicita la configuración de red al servidor DHCP externo (core-linux - 192.168.100.10).

3.- l DHCP entrega:

  - IP del cliente

  - Gateway

  - Servidor TFTP (Fog server - 192.168.100.13)

  - Archivo de arranque → undionly.kpxe (BIOS) o ipxe.efi (UEFI)

El cliente descarga el bootloader desde TFTP.

El iPXE se ejecuta y se conecta via HTTP a ```http://192.168.100.13/fog/service/ipxe/boot.php```

FOG revisa si el host tiene tareas pendientes.

Si el host tiene una tarea asignada → se ejecuta automáticamente

Si no hay tareas → se muestra el menú de FOG

<img width="1021" height="348" alt="image" src="https://github.com/user-attachments/assets/77647bf7-ccdd-4de0-8566-265a5ef3f3d7" />


## 2. Archivos de arranque PXE

Los archivos principales se encuentran en ```/tftpboot/```

- undionly.kpxe → BIOS Legacy

- ipxe.efi → UEFI

- default.ipxe →
  
<img width="1025" height="66" alt="image" src="https://github.com/user-attachments/assets/06b53ac3-c996-4ada-aad0-b3da43b458a7" />


## 3. Configuración DHCP (core-linux)

Como FOG no actúa como DHCP, el servidor DHCP externo debe incluir:

-BIOS (Legacy)
next-server 192.168.100.13;
filename "undionly.kpxe";

- UEFI
next-server 192.168.100.13;
filename "ipxe.efi";


