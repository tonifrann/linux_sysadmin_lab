# Fail2ban

Fail2ban se utiliza para proteger el servidor de ataques de fuerza bruta.

Fail2ban resiva los logs del sistema y bloquea automáticamente las IP que intentan acceder varias veces con intentos fallidos.

En este servidor Fail2ban se utiliza para proteger:

- SSH (para evitar accesos no autorizados)

- Nginx (para detener peticiones maliciosas o que se repiten demasiadas veces)


## 1. Instalación

Se habilita el repositorio de ```epel-release``` para poder instalar Fail2ban:

<img width="1021" height="138" alt="image" src="https://github.com/user-attachments/assets/0b41d520-b6dc-476b-a79a-7200e1c9cffb" />

Se instala Fail2ban y se integra con firewalld:

<img width="1017" height="267" alt="image" src="https://github.com/user-attachments/assets/e6969626-8934-4a2a-9585-5bbf6abd9fde" />

Se habilita y se inicia el servicio:

<img width="1023" height="289" alt="image" src="https://github.com/user-attachments/assets/78d4559d-7092-4448-bcbd-b2cc915944ed" />


## 2. Configuración

Se crea el archivo de configuración:
<img width="1022" height="16" alt="image" src="https://github.com/user-attachments/assets/ec1d2e85-510c-4fb7-bc82-7cd4e67d2aef" />

Se modifica el archivo con los ajustes deseados, el tiempo de baneo de una IP, el tiempo en el que se cuentan los intentos, el numero máximo de intentos fallidos, etc:

<img width="1022" height="113" alt="image" src="https://github.com/user-attachments/assets/86283852-7c5b-483a-828d-03de2e133ec8" />


## 3. Protección de SSH

Se crea el archivo de configuración jail:

<img width="1023" height="17" alt="image" src="https://github.com/user-attachments/assets/9357fffa-cd3b-4791-a400-68840debe10b" />

Se configura el archivo de manera que se active la protección ssh y se bloqueen las IPs si realizan 3 fallos seguidos:

<img width="1023" height="112" alt="image" src="https://github.com/user-attachments/assets/15df3e81-8a25-4d37-8054-8e2576a7c1cd" />


## 4. Protección de Nginx (HTTPS)

Se crea el archivo de configuración para el jail:
<img width="1020" height="19" alt="image" src="https://github.com/user-attachments/assets/72b5ebd0-c821-4f57-bbb4-0d2244fa2068" />

Se configura:
<img width="1023" height="256" alt="image" src="https://github.com/user-attachments/assets/d121145b-16ef-4ab5-a5ae-cc435c1065d8" />


## 5. Configuración de los filtros

Se crea un nuevo filtro para detectar las autenticaciones fallidas:
<img width="1020" height="18" alt="image" src="https://github.com/user-attachments/assets/0b03020f-bb5d-4314-9e0c-2c130b00ecac" />
Se configura:


Se crea otro filtro para detectar peticiones maliciosas:

Se configura:

