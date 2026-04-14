# Backups (rsync, tar, dd)

En este documento se muestran distintas formas de realizar copias de seguridad en Linux, utilizando herramientas habituales según el tipo de backup: incremental, comprimido o a bajo nivel.

## 1. Introducción

No todos los backups son iguales. Dependiendo del caso, interesa:

Copiar solo cambios → rsync
Generar un archivo comprimido → tar
Clonar discos completos → dd


## 2. Backup incremental con rsync

Se realiza una copiade seguridad del lvm montado en /mnt/data al directorio /backup utilizando rsync.

<img width="993" height="113" alt="image" src="https://github.com/user-attachments/assets/25730961-5a6f-491c-8efb-51b1bd142d51" />

Se comprueba que los archivos se han copiado correctamente:

<img width="992" height="65" alt="image" src="https://github.com/user-attachments/assets/272345f8-a85e-436e-92c1-cb3a40eebcc2" />

> NOTA: Se utiliza rsync por su eficiencia al copiar únicamente los cambios.


## 3. Backup comprimido con tar

Se genera un archivo comprimido del directorio /srv/web:

<img width="994" height="82" alt="image" src="https://github.com/user-attachments/assets/037902e4-e754-432e-a1f9-37c9b79ab9f3" />

Verificamos que se ha creado correctamente:

<img width="991" height="84" alt="image" src="https://github.com/user-attachments/assets/3f22f7b6-8c74-455f-890d-19fc1bcb39c0" />

<img width="1000" height="68" alt="image" src="https://github.com/user-attachments/assets/0914878b-45c8-486f-848f-893a504b3169" />

> NOTA: $(date +%F) genera automáticamente la fecha, indicando cuándo se creó cada backup.


## 4. Backup de bajo nivel con dd

Se realiza una copia a bajo nivel de un disco a un archivo de imagen.

<img width="995" height="97" alt="image" src="https://github.com/user-attachments/assets/658c41f4-2614-40df-8a9a-1158af1fa4de" />

Se comprueba el tamaño del archivo generado:

<img width="990" height="97" alt="image" src="https://github.com/user-attachments/assets/19d1d55d-47e0-4333-af59-3ca330979893" />

> NOTA: Herramienta potente pero peligrosa: un error en if o of puede sobrescribir datos.


## 4. Restauración 

Se realizan pruebas de restauración para verificar que los backups han funcionado.

- rsync:

<img width="991" height="131" alt="image" src="https://github.com/user-attachments/assets/9cff1fa2-e02a-4dc4-af39-652827c1ef8f" />


- tar

<img width="994" height="66" alt="image" src="https://github.com/user-attachments/assets/97b04644-f852-46b1-8a7a-c9281b5b5248" />


- dd

<img width="987" height="69" alt="image" src="https://github.com/user-attachments/assets/c7000996-e3d2-4352-b648-538de2c99bba" />


## 5. Automatización de backups

Accedor como root para crear un crontab del sistema para hacer backups incrementales diarios por la noche.

<img width="988" height="49" alt="image" src="https://github.com/user-attachments/assets/7684ebe9-f41b-42d5-83a3-f0bbd504c0c3" />



