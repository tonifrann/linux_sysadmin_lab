# Incidencia: Error de captura por cifrado de BitLocker 


## 1. Problema

Al intentar capturar una imagen de Windows 11, FOG detiene el proceso indicando que la partición está cifrada con BitLocker, aunque Windows muestra que el cifrado está desactivado.

<img width="1026" height="722" alt="image" src="https://github.com/user-attachments/assets/e04cde43-fc27-484e-99f7-1bbe88f03f84" />


## 2. Causa

Windows tenía configurado el “cifrado de espacio usado”, lo que deja una firma de BitLocker residual en la partición aunque el cifrado esté desactivado.

FOG detecta esa firma y bloquea la captura.

3. Resolución
Se desactiva BitLocker completamente.

Se elimina la firma residual (descifrado completo / ajuste de partición).

Se repite la captura y funciona correctamente.

4. Resultado
La captura se completa sin errores tras eliminar la firma BitLocker.
