# Incidencia: Error en Docker Engine

## 1. Problema

El servicio Docker Engine no arranca y no se puede gestionar ningún contenedor.


## 2. Síntomas

Se intenta ejecutar un comando de Docker:

<img width="1022" height="45" alt="image" src="https://github.com/user-attachments/assets/1a54f84f-91e8-4a0d-9319-84d8f97dd382" />

Se comprueba el estado del servicio:

<img width="1022" height="252" alt="image" src="https://github.com/user-attachments/assets/9317ea60-cfea-41fa-8d8d-c13698ed3808" />


## 3. Diagnóstico

Se revisan los logs del servicio:

<img width="1022" height="15" alt="image" src="https://github.com/user-attachments/assets/fd67f1d3-ffb8-4ca7-8926-de905be61e33" />

<img width="1023" height="111" alt="image" src="https://github.com/user-attachments/assets/40ecba63-27e0-41a7-8b31-5add213fac7f" />



## 4. Causa

El daemon de Docker no se puede inicializar por culpa de un error de sintaxis en el archivo /etc/docker/daemon.json, haciendo que servicio falle al arrancar.


## 5. Solución

Se indentifica donde está el erroe en el archivo /etc/docker/daemon.json y se corrige. Después de reinicia el servicio de Docker para que se apliquen los cambios en la configuración:

<img width="1022" height="14" alt="image" src="https://github.com/user-attachments/assets/6fe43a5f-91f9-47e2-b21f-2f6259c0ac59" />

<img width="1022" height="20" alt="image" src="https://github.com/user-attachments/assets/b3866575-d0c2-4ea0-9f8f-6e31fb0404f8" />


## 6. Verificación

Se comprueba que el servicio está activo:
<img width="1018" height="205" alt="image" src="https://github.com/user-attachments/assets/0bc56880-7c40-46a5-94db-72b73d6b71f1" />

Se valida el funcionamiento de Docker:

<img width="1020" height="65" alt="image" src="https://github.com/user-attachments/assets/cb9a97af-f355-4bb9-8d23-017e32db1dc2" />



## 7. Prevención

Validar siempre la sintaxis de los archivos JSON antes de reiniciar un servicio

Revisar los logs de systemd siempre que haya un fallo en el arranque.
