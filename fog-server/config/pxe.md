# Arranque PXE en FOG Project

El arranque por PXE permite iniciar equipos desde la red para desplegar imágenes, capturar sistemas o ejecutar herramientas.
El proceso depende de la integración entre DHCP externo, TFTP, iPXE y el propio servidor FOG.


## 1. Flujo de arranque PXE

El proceso completo es:

1.- El cliente arranca desde red (PXE).

2.- Solicita la configuración de red al servidor DHCP externo (core-linux - 192.168.100.10).

3.- El servidor DHCP entrega:

    - IP del cliente

    - Gateway

    - Servidor TFTP (Fog server - 192.168.100.13)

    - Archivo de arranque → undionly.kpxe (BIOS) o ipxe.efi (UEFI)

4.-El cliente descarga el bootloader desde TFTP.

5.- El iPXE se ejecuta y se conecta via HTTP:

```http://192.168.100.13/fog/service/ipxe/boot.php```

6.- FOG revisa si el host tiene tareas pendientes.

    - Si el host tiene una tarea asignada → se ejecuta automáticamente

    - Si no hay tareas → se muestra el menú de FOG


## 2. Archivos de arranque PXE

Los archivos principales se encuentran en el servidor FOG:

```/tftpboot/```

- undionly.kpxe → BIOS Legacy

- ipxe.efi → UEFI

- default.ipxe →Script de arranque iPXE
  
<img width="1025" height="66" alt="image" src="https://github.com/user-attachments/assets/06b53ac3-c996-4ada-aad0-b3da43b458a7" />


## 3. Configuración DHCP (core-linux)

La configuración del arranque PXE se realiza en el servidor DHCP del sistema principal (core-linux), donde se define la opcion de boot para UEFI.

La configuración completa está documentada en ../core-linux/config/dhcp.md

## 4. Validación del arranque PXE

Para comprobar que el sistema funciona correctamente:

- Cliente arranca en modo PXE
- Se obtiene una IP por DHCP
- Carga de iPXE
- Acceso al menú de FOG

<img width="1022" height="430" alt="image" src="https://github.com/user-attachments/assets/3659dd6d-5d23-4191-9c55-2a452787bee1" />




<img width="798" height="595" alt="image" src="https://github.com/user-attachments/assets/e7da5450-7730-4d4a-9261-c6d49c92be39" />

