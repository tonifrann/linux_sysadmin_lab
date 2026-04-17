# Incidencia: Bloqueo de SELinux en Samba

Después de crear un nuevo recurso compartido en Samba, los usuarios no pueden escribir en él, aunque los permisos parecen correctos.


## 1. Problema

Se crea un nuevo recurso compartido en `/srv/sistemas` y se asignan permisos a nivel de sistema.

El recurso existe, pero no se puede acceder:

<img width="807" height="678" alt="image" src="https://github.com/user-attachments/assets/3a9d32a8-ae1d-41d0-9ff6-18d4d0521b95" />


## 2. Síntomas

- Desde Windows se ve la carpeta pero no se puede acceder
- Desde Linux los permisos y la configuración de ```/etc/samba/smb.conf``` parece correcta.




<img width="988" height="67" alt="image" src="https://github.com/user-attachments/assets/523620d4-830c-40f9-803d-c75ed91f94dc" />
