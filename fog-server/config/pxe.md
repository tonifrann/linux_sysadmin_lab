# Arranque PXE en FOG Project

El arranque PXE es el proceso inicial que permite a un equipo iniciar desde red y conectarse al servidor FOG para ver si debe ejecutar una tarea o mostrar el menú de arranque.


## 1. Flujo de arranque PXE

El proceso de rranque es el siguiente:

1.- El cliente arranca desde red (PXE).

2.-El servidor DHCP externo (core-linux - 192.168.100.10) proporciona la configuración de red y los parámetros de arranque.

3.- Se asignan los siguientes parámetros::

   - Servidor TFTP (Fog server - 192.168.100.13)

   - Bootloader 
            
      - undionly.kpxe (BIOS Legacy)
            
      - ipxe.efi (UEFI)

4.- El cliente descarga el iPXE via TFTP.

5.- Se ejecuta iPXE y se realiza una petición via HTTP al servidor FOG:

```http://192.168.100.13/fog/service/ipxe/boot.php```

6.- FOG revisa el estado del host:

- Si hay tareas asignadas, se ejecutan automáticamente.

- Sino hay tareas asignadas, se carga el menú de FOG.


## 2. Archivos de arranque PXE

Los archivos principales se encuentran en el servidor FOG:

```/tftpboot/```

- undionly.kpxe → BIOS Legacy

- ipxe.efi → UEFI

  
<img width="1025" height="66" alt="image" src="https://github.com/user-attachments/assets/06b53ac3-c996-4ada-aad0-b3da43b458a7" />


## 3. Configuración DHCP (core-linux)

La configuración del arranque PXE se realiza en el servidor DHCP del sistema principal (core-linux), donde se define la opcion de boot para UEFI.

Configuración completa:

[DHCP (ISC DHCP)](../core-linux/config/dhcp.md)


## 4. Validación del arranque PXE

Se valida el flujo completo del arranque desde el cliente hasta FOG:

- El equipo arranca en modo PXE

- Obtiene configuración IP vía DHCP

- Descarga iPXE mediante TFTP

- Conexión con FOG

<img width="1022" height="430" alt="image" src="https://github.com/user-attachments/assets/3659dd6d-5d23-4191-9c55-2a452787bee1" />

- Se carga el menú de FOG cuando no existen tareas asignadas

<img width="795" height="184" alt="image" src="https://github.com/user-attachments/assets/af7b881c-9b28-4881-8d8e-5382835fe22d" />

> Nota: Secure Boot debe estar desactivado para permitir la ejecución de iPXE (bootloader no firmado)
