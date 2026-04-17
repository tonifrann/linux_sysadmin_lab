# Scripts del servidor

Scripts utilizados en el servidor para tareas de mantenimiento y soporte.

Se guardan en /usr/local/bin y se ejecutan con crontab automaticamente.


## 1. Backup del recurso Samba

Se copia el contenido del recurso compartido /srv/share en un directorio de backups:

<img width="1009" height="112" alt="image" src="https://github.com/user-attachments/assets/647116b0-1370-462e-bc5e-504d9c6d47cf" />

Se ejecuta:

<img width="1003" height="131" alt="image" src="https://github.com/user-attachments/assets/3301eeb4-1044-4f88-a526-ab3210e61292" />


## 2. Limpieza de logs antiguos

Elimina logs antiguos rotados que se van acumulando en /var/log:

<img width="1008" height="51" alt="image" src="https://github.com/user-attachments/assets/5549c858-280b-4676-bfb7-de0e120608b7" />


## 3. Comprobación de espacio en disco

Muestra el uso del disco y los directorios que más ocupan.

<img width="1005" height="117" alt="image" src="https://github.com/user-attachments/assets/6c6e6a7b-1a86-49cb-a717-42bfd127405c" />

Se ejecuta:

<img width="1003" height="177" alt="image" src="https://github.com/user-attachments/assets/0be7db10-f0e1-4228-9556-e6a13adf30dd" />
