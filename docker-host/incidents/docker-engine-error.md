# Incidencia: Error en Docker Engine

## 1. Problema

El servicio Docker Engine no está disponible y no permite gestionar ningún contenedor.


## 2. Síntomas

Se intenta ejecutar un comando de Docker:


Se comprueba el estado del servicio:

<img width="1022" height="252" alt="image" src="https://github.com/user-attachments/assets/9317ea60-cfea-41fa-8d8d-c13698ed3808" />


## 3. Diagnóstico

Se revisa el estado del servicio Docker:



Se revisan los logs del servicio:


## 4. Causa

El servicio Docker se encuentra detenido debido a un error en el arranque del daemon.


## 5. Solución

Se reinicia el servicio Docker:


## 6. Verificación

Se comprueba que el servicio está activo:



Se valida el funcionamiento de Docker:



## 7. Prevención

Monitorizar el estado del servicio Docker.
Revisar logs en caso de fallo en el arranque.
