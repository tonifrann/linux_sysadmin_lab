# Incidencia: Error de captura por cifrado de BitLocker 


## 1. Problema

Al intentar capturar una imagen de Windows 11, FOG detiene el proceso indicando que la partición está cifrada con BitLocker, aunque Windows muestra que el cifrado está desactivado.

<img width="1010" height="357" alt="image" src="https://github.com/user-attachments/assets/ac339d8e-b720-49b5-b6d5-f678df927dc9" />


## 2. Síntomas

La captura arranca correctamente por PXE.

- Partclone detecta las particiones.

- El proceso se interrumpe antes de iniciar la copia.

- El equipo se reinicia automáticamente.


## 3. Diagnóstico

 - La red funciona correctamente.

- NFS se encuentra operativo.

- Los permisos en /images/dev son correctos.

- La tabla de particiones se lee sin errores.

- La partición afectada es /dev/sda3.

- En Windows, BitLocker aparece como “desactivado”, pero muestra “Cifrado de espacio usado”.

<img width="975" height="354" alt="image" src="https://github.com/user-attachments/assets/5e636020-2664-4130-91f0-79c3054ad19e" />


## 4. Causa

Windows 11 ha configurado el cifrado de espacio usado automáticamente, aunque el cifrado esté desactivado.

FOG detecta esa firma y bloquea la captura.


## 5. Solución

- Se desactiva BitLocker completamente (descifrado completo).

<img width="976" height="404" alt="image" src="https://github.com/user-attachments/assets/2e8d8e09-d2b3-4917-b656-3da314cfafe5" />


## 6. Verificación

- La captura se monta en /images/dev sin errores.

- Partclone inicia la copia de la partición.

- La imagen se crea correctamente.


## 7. Prevención
   
- Verificar el estado de BitLocker antes de capturar con ```manage-bde -status```

- Evitar que el equipo de la imagen base este cifrado.

- Asegurarse de que la partición está completamente descifrada antes de de volver a capturar.
