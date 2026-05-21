# Incidencia: Error en el depoly por falta de espacio den disco

# 1. Problema

Al intentar desplegar una imagen de  Windows 11 desde FOG, el proceso falla durante la restauración de la tabla de particiones GPT.

El cliente muestra un error indicando que las particiones de la imagen no caben en el disco destino.

<img width="1023" height="593" alt="image" src="https://github.com/user-attachments/assets/78108209-1536-41a2-8676-87625d737226" />


# 2. Síntomas

- El arranque por PXE funciona correctamente

- La imagen se descarga desde /images.

- El error aparece al restaurar la tabla GPT.

- El despliegue se aborta automáticamente.

- El log muestra los mensajes:

   - Partition 3/4 is too big for the disk

   - Aborting write operation!


## 3. Diagnóstico

La imagen fue capturada desde un disco más grande que el del equipo destino.

Aunque el sistema operativo no ocupaba todo el espacio disponible, la estructura GPT original tenia particiones más grandes que la capacidad del nuevo disco.

FOG solo puede restaurar imágenes en discos más pequeños en el caso de:

- La imagen sea de tipo Resizable

- Las particiones permitan redimensionamiento


## 4. Causa
   
La imagen win11_image se capturo desde un disco más grande que el disco destino.

- Disco de origen de 80 GB

- Disco de destino de 60 GB

La tabla GPT original no podía crearse completamente en el disco menor.


## 5. Solución

Se aumenta el tamaño del disco de destino para que sea igual que el que se utilizo en la captura de la imagen. 

Como alternativa, también se podria haber creado la imagen en un disco base más pequeño.


## 6. Verificación

Despues de ampliar el disco:

- La tabla GPT se restaura sin errores.

- Partclone continúa el despliegue sin errores.

- El equipo inicia Windows sin problemas.

<img width="1359" height="405" alt="image" src="https://github.com/user-attachments/assets/cb33f756-66cd-45f3-861e-f2bf5ceeb033" />



## 7. Prevención

- Crear la imagen base en un disco lo más pequeño posible.

- Verificar el tamaño del disco antes del despliegue de la imagen.

- Utilizar imágenes ```Resizable``` cuando sea posible

