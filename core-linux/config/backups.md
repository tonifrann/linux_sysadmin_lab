# Backups (rsync, tar, dd)

En este documento se muestran distintas formas de realizar copias de seguridad en Linux, utilizando herramientas habituales según el tipo de backup: incremental, comprimido o a bajo nivel.

## 1. Introducción

No todos los backups son iguales. Dependiendo del caso, interesa:

Copiar solo cambios → rsync
Generar un archivo comprimido → tar
Clonar discos completos → dd


## 2. Backup incremental con rsync

Se utiliza rsync para copiar directorios de forma eficiente, copiando solo los cambios. Ideal para backups periódicos, ya que reduce tiempo y consumo de espacio.

<img width="993" height="113" alt="image" src="https://github.com/user-attachments/assets/25730961-5a6f-491c-8efb-51b1bd142d51" />

Se verifica:

<img width="992" height="65" alt="image" src="https://github.com/user-attachments/assets/272345f8-a85e-436e-92c1-cb3a40eebcc2" />


## 3. Backup comprimido con tar

Se utiliza tar para generar un archivo comprimido con el contenido de un directorio.

<img width="994" height="82" alt="image" src="https://github.com/user-attachments/assets/037902e4-e754-432e-a1f9-37c9b79ab9f3" />

Nota: $(date +%F) genera automáticamente la fecha en formato YYYY-MM-DD, lo que facilita identificar cuándo se creó cada backup.
