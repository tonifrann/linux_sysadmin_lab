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

Se revisa la configuración del recurso compartido:

<img width="987" height="141" alt="image" src="https://github.com/user-attachments/assets/0a89d4db-544e-4b81-9164-a1cd773c4c20" />

<img width="987" height="98" alt="image" src="https://github.com/user-attachments/assets/e3cfa49e-2c3c-4a01-be1d-9a5c622c43f4" />

Se detecta que el recurso compartido no tiene correctamente configurado el grupo:

<img width="989" height="64" alt="image" src="https://github.com/user-attachments/assets/a879f3d7-3d06-4946-b72e-cd11b629601d" />

