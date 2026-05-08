# Incidencia: Contenedor finalizado inesperadamente con código 137 (SIGKILL)

## 1. Problema

El contenedor alpine_tool se detiene de forma inesperada durante su ejecución, pasando a estado Exited (137).


## 2. Síntomas

Se revisan los contenedores:

<img width="1022" height="62" alt="image" src="https://github.com/user-attachments/assets/9adee627-2c71-441c-9695-76e18b686ef4" />


## 3. Diagnostico

Se inspecciona el contenedor:
<img width="1023" height="13" alt="image" src="https://github.com/user-attachments/assets/b4eea43a-901f-4118-be8f-5ccc0492edcd" />

<img width="1021" height="160" alt="image" src="https://github.com/user-attachments/assets/83de3a82-b25c-4e65-8fce-6c9065fd5ece" />

Se revisan los logs, pero no se detalla ninguna información:

<img width="1020" height="27" alt="image" src="https://github.com/user-attachments/assets/487cfad7-259b-46f7-89f2-e63d4d36e8bc" />



## 4. Causa

El contenedor ha sido finalizado con código 137 (SIGKILL).
No se detecta OOM (OOMKilled=false) ni información en logs, por lo que no se puede demostrar la causa exacta. Probablemente ha sido una finalización externa o forzada.


## 5. Solución

Se reinicia el contenedor y se verifica que funciona correctamente:

<img width="1021" height="34" alt="image" src="https://github.com/user-attachments/assets/1cacf66a-7d02-4167-9b9a-2ef3bf67872f" />


## 6. Verificación

Se comprueba que el contenedor este funcionando:

<img width="1020" height="49" alt="image" src="https://github.com/user-attachments/assets/a4e3c434-dab9-4403-a8b2-cf03d24d4889" />


## 7. Prevención

Monitorizar los recursos del host para  detectar picos de consumo.
Revisar los eventos del sistema (dmesg / syslog) en caso de repetirse.
Definir algunos límites de recursos en contenedores (--memory, --cpus).
