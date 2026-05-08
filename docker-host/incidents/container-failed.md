# Incidencia: Contenedor finalizado con código 137 (SIGKILL)

## 1. Problema

El contenedor `alpine_tool` se detiene de forma inesperada mostrando estado `Exited (137)`.


## 2. Síntomas

Se revisan los contenedores:

<img width="1022" height="62" alt="image" src="https://github.com/user-attachments/assets/9adee627-2c71-441c-9695-76e18b686ef4" />

## 3. Diagnostico

Se comprueba que el proceso del contenedor no esta funcionando:

<img width="1023" height="33" alt="image" src="https://github.com/user-attachments/assets/8852523a-e3fa-47a4-b308-6b4619a90329" />

## 4. Causa

El contenedor fue finalizado por el sistema con código 137 (SIGKILL), normalmente asociado a falta de memoria (OOM) o detención forzada.

## 5. Solucion

El contenedor no estaba dañado, unicamente estaba detenido. Se vuelve a iniciar:

<img width="1021" height="34" alt="image" src="https://github.com/user-attachments/assets/1cacf66a-7d02-4167-9b9a-2ef3bf67872f" />

## 6. Varificación

Se comprueba que el contenedor este funcionando:

<img width="1020" height="49" alt="image" src="https://github.com/user-attachments/assets/a4e3c434-dab9-4403-a8b2-cf03d24d4889" />


## 7. Prevencion

Revisar el estado del proceso principal del contenedor.

Revisar los contenedores detenidos para detectar algun fallo.
