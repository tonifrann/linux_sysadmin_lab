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

   - Partition X is too big for the disk

   - Aborting write operation!


## 3. Diagnóstico

El error indica que:

- La imagen fue capturada desde un disco más grande.

- El disco del equipo destino es más pequeño.

- FOG intenta restaurar la tabla GPT original, pero las particiones no caben.

FOG solo puede restaurar una imagen en un disco igual o mayor que el original, a no ser que la imagen este configurada como ```resizable``` y las particiones lo permitan.


## 4. Causa
   
La imagen win11_image fue capturada desde un disco más grande que el disco donde se intenta hacer el deploy.

- Imagen capturada desde un disco de 80 GB

- Intento de desplegar en un disco de 60 GB

Aunque la partición de Windows no ocupe todo el espacio, la tabla GPT sí contiene particiones que superan el tamaño del disco de destino.


## 5. Solución

Se aumentar el tamaño del disco de destino para que sea igual que el original. Aunque también se podria haber optado por volver a crear la imagen en un disco más pequeño.


## 6. Verificación

Despues de crear un disco mayor en el equipo destino:

- El despliegue restaura la tabla GPT sin errores.

- No aparecen mensajes de particiones demasiado grandes.

- El proceso continúa con Partclone y finaliza correctamente.

- El equipo arranca Windows sin problemas.


## 7. Prevención

- Crear siempre la imagen base en un disco lo más pequeño posible.

- Verificar el tamaño del disco de destino antes de hacer el deploy de la imagen.


