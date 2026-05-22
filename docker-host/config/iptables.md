# Configuración del Firewall (iptables)

En este servidor se utiliza únicamente iptables.  
Docker gestiona automáticamente sus propias reglas con iptables (cadenas DOCKER, DOCKER-FORWARD, DOCKER-USER), asi que no es necesario instalar firewalld.  
Se aplica una política restrictiva en INPUT y se permiten únicamente los puertos necesarios.

## 1. Estado del firewall

Se comprueba el estado de las reglas de iptables:

<img width="1023" height="655" alt="image" src="https://github.com/user-attachments/assets/c6d139de-fb39-4c1b-b2cc-5848cb4a0470" />


## 2. Configuración manual de reglas

Se permite el tráfico en la interfaz loopback (lo), necesario para la comunicación interna del sistema:
<img width="1022" height="32" alt="image" src="https://github.com/user-attachments/assets/bee20bcb-8877-4d45-b646-cbe591252e0d" />


Se permite el tráfico de las conexiones ya establecidas:
<img width="1024" height="30" alt="image" src="https://github.com/user-attachments/assets/5a4c9316-bd6c-4d05-83ad-1d1248d761ab" />


Se permite el acceso al servicio web del contenedor Nginx:
<img width="1022" height="28" alt="image" src="https://github.com/user-attachments/assets/a522a74f-24cd-4228-ac3f-9f7e491e7171" />

Se permite el acceso por SSH:
<img width="1020" height="32" alt="image" src="https://github.com/user-attachments/assets/d4f1b667-67c6-439e-8e0d-cdf8390681e4" />

Se configura una política restrictiva por defecto: 
<img width="1024" height="30" alt="image" src="https://github.com/user-attachments/assets/8c4313f5-ff3c-4eae-aeb5-74931e0e75d4" />

Se configura la cadena FORWARD para que este en ACCEPT, para que docker permita el trafico entre los contenedores y redes externas:

<img width="1021" height="29" alt="image" src="https://github.com/user-attachments/assets/18ce8189-0343-421d-8f12-1042a6f808a8" />



## 3. Persistencia de las reglas

Se utiliza netfilter-persistent para que se guarden y restauren automáticamente las reglas de iptables después de un reinicio del sistema.

<img width="1022" height="14" alt="image" src="https://github.com/user-attachments/assets/7598e631-850c-4805-abed-950efdebdb32" />

<img width="1022" height="418" alt="image" src="https://github.com/user-attachments/assets/83f701f3-722a-4c76-a065-2a793f545cb5" />
