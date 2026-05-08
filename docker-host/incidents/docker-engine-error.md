# Incidencia: Error en Docker Engine

## 1. Problema

El servicio Docker Engine no está disponible y no permite gestionar ningún contenedor.


## 2. Síntomas

Se intenta ejecutar un comando de Docker:


Se comprueba el estado del servicio:

<img width="1022" height="252" alt="image" src="https://github.com/user-attachments/assets/9317ea60-cfea-41fa-8d8d-c13698ed3808" />


## 3. Diagnóstico

Se revisan los logs del servicio:

<img width="1022" height="15" alt="image" src="https://github.com/user-attachments/assets/fd67f1d3-ffb8-4ca7-8926-de905be61e33" />

<img width="1023" height="111" alt="image" src="https://github.com/user-attachments/assets/40ecba63-27e0-41a7-8b31-5add213fac7f" />



## 4. Causa

El servicio Docker da errores en el arranque del daemon que apuntan a un error en un carácter del archivo /etc/docker/daemon.json.


## 5. Solución

Se revisa el archivo /etc/docker/daemon.json e nbusca de errores y se reinicia el servicio Docker:

<img width="1022" height="14" alt="image" src="https://github.com/user-attachments/assets/6fe43a5f-91f9-47e2-b21f-2f6259c0ac59" />

<img width="1022" height="20" alt="image" src="https://github.com/user-attachments/assets/b3866575-d0c2-4ea0-9f8f-6e31fb0404f8" />




## 6. Verificación

Se comprueba que el servicio está activo:



Se valida el funcionamiento de Docker:



## 7. Prevención

Monitorizar el estado del servicio Docker.
Revisar logs en caso de fallo en el arranque.
