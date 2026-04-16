# Incidencia: Permisos en Samba

No se puede acceder a un recurso compartido en Samba debido a una mala configuración de permisos.


## 1. Problema

Un usuario no puede acceder a un recurso compartido de Samba. El recurso se monta correctamente, pero no permite acceder ni escribir (acceso denegado).

<img width="515" height="209" alt="image" src="https://github.com/user-attachments/assets/fcd57441-60ad-485c-b48d-a22345889f66" />


## 2. Síntomas

- Windows muestra acceso denegado
- Desde Linux tampoco se puede escribir en el directorio


## 3. Diagnóstico

Se comprueba que el servicio de Samba está activo:

<img width="988" height="274" alt="image" src="https://github.com/user-attachments/assets/a65d9fd0-dd17-49ab-8a7b-bcbd16bfab46" />

Se revisa la configuración del recurso compartido:

<img width="987" height="141" alt="image" src="https://github.com/user-attachments/assets/0a89d4db-544e-4b81-9164-a1cd773c4c20" />

<img width="987" height="98" alt="image" src="https://github.com/user-attachments/assets/e3cfa49e-2c3c-4a01-be1d-9a5c622c43f4" />

Se revisan los permisos del recurso compartido:

<img width="989" height="64" alt="image" src="https://github.com/user-attachments/assets/a879f3d7-3d06-4946-b72e-cd11b629601d" />

Ya que el servicio está activo y la configuración parece correcta, parece un problema de permisos.


## 4. Causa

El directorio compartido tiene permisos incorrectos a nivel de grupo, lo que impide la escritura aunque Samba esté correctamente configurado.


## 5. Solucion

Se corrigen los permisos de propietario del grupo:

<img width="991" height="80" alt="image" src="https://github.com/user-attachments/assets/2b21eca1-e635-469b-b746-eb419a4874a1" />


## 6. Verificación

Se vuelve a acceder desde Windows:

<img width="926" height="193" alt="image" src="https://github.com/user-attachments/assets/74f3aefb-2d0e-4499-9134-9ab0a77338ac" />

Se comprueba también desde Linux:

<img width="994" height="159" alt="image" src="https://github.com/user-attachments/assets/f125386b-bc5c-409e-abea-8b28260b8ccc" />


## 7. Prevención

- Definir correctamente usuarios y grupos en los directorios
- Validar acceso desde Linux y Windoes cuando se hagan cambios
- Mantener coherencia entre permisos Linux y configuración de Samba
- Utilizar ACLs cuando sea necesario
- Documentar que usuarios y grupos tienen acceso
