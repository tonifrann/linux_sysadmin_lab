Error Bitlocker 
<img width="1026" height="722" alt="image" src="https://github.com/user-attachments/assets/e04cde43-fc27-484e-99f7-1bbe88f03f84" />

# Error de captura por firma de BitLocker 

1. Problema
Durante la captura de una imagen Windows 11, FOG aborta el proceso al detectar una firma BitLocker en la partición del sistema, aunque Windows muestra que el cifrado está desactivado.

El proceso se detiene con el mensaje:

Código
Found bitlocker signature in partition /dev/sda3 header.
Please disable BITLOCKER before capturing an image.
2. Síntomas
La tarea de captura arranca correctamente por PXE.

Partclone inicia el análisis de particiones.

El proceso se interrumpe antes de comenzar la copia.

El equipo se reinicia automáticamente tras el error.

En Windows, el estado de BitLocker aparece como:

“Desactivado”

“Cifrado de dispositivo: Desactivado”

Pero muestra “Cifrado de espacio usado”

3. Causa
Windows 10/11 puede aplicar cifrado automático parcial (BitLocker “cifrado rápido” o “cifrado de espacio usado”) incluso cuando el usuario nunca ha activado BitLocker manualmente.

Aunque el cifrado esté desactivado, la partición conserva:

la firma FVE

metadata residual de BitLocker

un encabezado NTFS marcado como previamente cifrado

FOG detecta esta firma en el sector inicial de la partición y considera que la unidad sigue cifrada, por lo que bloquea la captura.

4. Diagnóstico
El log de FOG confirma:

La red y NFS funcionan correctamente.

El almacenamiento tiene espacio suficiente.

La tabla de particiones se lee sin errores.

La partición afectada es /dev/sda3.

El único error es la detección de la firma BitLocker.

Windows confirma:

BitLocker desactivado

Cifrado de espacio usado aplicado previamente

La partición conserva la firma FVE

5. Resolución
Para eliminar la firma residual de BitLocker:

Forzar descifrado completo desde Windows:

Desactivar BitLocker aunque aparezca como “desactivado”.

Esperar al 100% del proceso.

Si la firma persiste, realizar una operación que fuerce a Windows a reescribir el encabezado NTFS:

Reducir la partición unos MB y volver a ampliarla.

O recrear la partición moviendo los datos.

Tras eliminar la firma, la captura se completa correctamente.

6. Validación
Una vez eliminada la firma:

La captura monta /images/dev sin errores.

Partclone inicia la copia de la partición.

La imagen se genera y se mueve a /images/<imagen>.

El proceso finaliza sin intervención manual.

7. Impacto
La captura no puede realizarse mientras exista metadata BitLocker.

Afecta a equipos Windows 10/11 con cifrado automático OEM o de Microsoft.

Puede reproducirse en cualquier equipo donde Windows haya aplicado “cifrado rápido”.
