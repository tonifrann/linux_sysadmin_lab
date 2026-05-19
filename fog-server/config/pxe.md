# Arranque PXE en FOG Project

El arranque PXE es el proceso inicial que permite a un equipo iniciar desde red y conectarse al servidor FOG para ver si debe ejecutar una tarea o mostrar el menú de arranque.


## 1. Flujo de arranque PXE

El proceso es el siguiente:

1.- El cliente arranca desde red (PXE).

2.-El servidor DHCP externo (core-linux - 192.168.100.10) realiza la configuración de red 

3.- Se entrega:

    - Servidor TFTP (Fog server - 192.168.100.13)

    - Bootloader (undionly.kpxe / ipxe.efi)

4.- El cliente descarga el iPXE via TFTP.

5.- El iPXE ejecuta una peticion HTTP a FOG:

```http://192.168.100.13/fog/service/ipxe/boot.php```

6.- FOG revisa las tareas:

    - Si hay tareas asignadas, se ejecutan automáticamente.

    - Sino hay tareas asignadas, se muestra el menú de FOG y el usuario selecciona una de las opciones manualmente.


## 2. Archivos de arranque PXE

Los archivos principales se encuentran en el servidor FOG:

```/tftpboot/```

- undionly.kpxe → BIOS Legacy

- ipxe.efi → UEFI
- 
  
<img width="1025" height="66" alt="image" src="https://github.com/user-attachments/assets/06b53ac3-c996-4ada-aad0-b3da43b458a7" />


## 3. Configuración DHCP (core-linux)

La configuración del arranque PXE se realiza en el servidor DHCP del sistema principal (core-linux), donde se define la opcion de boot para UEFI.

Configuración completa:

[DHCP (ISC DHCP)](../core-linux/config/dhcp.md)


## 4. Validación del arranque PXE

Para comprobar que el sistema funciona correctamente:

- Cliente arranca en modo PXE
- Se obtiene una IP por DHCP
- Carga de iPXE

<img width="1022" height="430" alt="image" src="https://github.com/user-attachments/assets/3659dd6d-5d23-4191-9c55-2a452787bee1" />


## 
