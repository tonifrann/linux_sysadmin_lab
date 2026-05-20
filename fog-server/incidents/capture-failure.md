# Incidencia: Error de captura por cifrado de BitLocker 


## 1. Problema

Al intentar capturar una imagen de Windows 11, FOG detiene el proceso indicando que la partición está cifrada con BitLocker, aunque Windows muestra que el cifrado está desactivado.

<img width="1010" height="357" alt="image" src="https://github.com/user-attachments/assets/ac339d8e-b720-49b5-b6d5-f678df927dc9" />


## 2. Síntomas

La captura arranca correctamente por PXE.

- Partclone detecta las particiones.

- El proceso se interrumpe antes de iniciar la copia.

- El equipo se reinicia automáticamente.

En Windows, BitLocker aparece como “desactivado”, pero muestra “Cifrado de espacio usado”.


