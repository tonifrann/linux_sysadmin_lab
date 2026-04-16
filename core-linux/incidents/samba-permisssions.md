# Incidencia: Permisos en Samba

Se simula un problema de acceso a un recurso compartido en Samba debido a una mala configuración de permisos.


## 1. Problema

Un usuario no puede acceder a un recurso compartido de Samba, aunque el servicio está funcionando correctamente.

<img width="515" height="209" alt="image" src="https://github.com/user-attachments/assets/fcd57441-60ad-485c-b48d-a22345889f66" />


> NOTA: El problema se ha provocado modificando permisos en el directorio compartido para simular un fallo real.


## 2. Síntomas

- Windows muestra acceso denegado
- Desde Linux tampoco se puede escribir en el directorio



## 3. Diagnóstico

Se comprueba que el servicio de Samba está activo:

<img width="988" height="274" alt="image" src="https://github.com/user-attachments/assets/a65d9fd0-dd17-49ab-8a7b-bcbd16bfab46" />

<img width="991" height="200" alt="image" src="https://github.com/user-attachments/assets/xxx" />
