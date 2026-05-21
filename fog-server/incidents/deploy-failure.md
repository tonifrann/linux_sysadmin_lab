# Incidencia: Error en el depoly por falta de espacio den disco

# 1. Problema

Al intentar desplegar una imagen de  Windows 11 desde FOG, el proceso falla durante la restauración de la tabla de particiones GPT.

El cliente muestra un error indicando que las particiones de la imagen no caben en el disco destino.

<img width="1023" height="593" alt="image" src="https://github.com/user-attachments/assets/78108209-1536-41a2-8676-87625d737226" />


# 2. Síntomas

- El despliegue arranca correctamente por PXE.

- La imagen se descarga correctamente desde /images.

- El error aparece justo al restaurar la tabla GPT.

- El proceso se aborta automáticamente y el equipo se reinicia.

- El log muestra los siguientes mensajes:

   - Current disk size doesn’t match that of the backup

   - Partition X is too big for the disk

   - Aborting write operation!
