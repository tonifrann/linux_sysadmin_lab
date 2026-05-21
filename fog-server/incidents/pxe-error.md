# Incidencia: Error PXE al arrancar

## 1. Problema

Un equipo configurado para arrancar por red por PXE da error y no se puede realizar el despliegue.

<img width="640" height="154" alt="image" src="https://github.com/user-attachments/assets/3ae56be0-fd4e-4105-bed0-613cedd7f623" />


## 2. Síntomas

- El cliente recibe una IP correctamente por DHCP.

- Se muestran correctamente los parámetros de red

- El error aparece justo después de recibir el bootfile.

- iPXE no se llega a cargar.


## 3. Diagnóstico

El error PXE‑E79 indica que el cliente está en modo BIOS/Legacy, pero el servidor DHCP le está enviando un NBP UEFI (ipxe.efi).


## 4. Causa

El servidor DHCP está configurado para entregar ```ipxe.efi```, sin embargo los clientes BIOS necesitan ```undionly.kpxe```


## 5. Solución

Se modifica la configuración DHCP del servidor DHCP (core-linux) para que utilice el bootfile correcto.

<img width="1020" height="319" alt="image" src="https://github.com/user-attachments/assets/49a2497a-ffd6-4247-a0ab-762391f3242f" />


## 6. Verificación

Después de applicar el cambio:

- El cliente arranca por PXE correctamente.

- iPXE se carga sin errores.

- Aparece el menú de FOG.

<img width="638" height="327" alt="image" src="https://github.com/user-attachments/assets/32c8b442-a66b-467a-8976-d82b96a585e0" />


## 7. Prevención

- Verificar siempre si el cliente utiliza BIOS o UEFI.

- Usar siempre undionly.kpxe para BIOS.

- Usar ipxe.efi solo para UEFI.



snponly.efi

o cualquier NBP UEFI
