# Firewall

En este servidor se utiliza unicamente iptables.  
Docker gestiona automáticamente sus propias reglas (cadenas DOCKER, DOCKER-FORWARD, DOCKER-USER), asi que no es necesario instalar firewalld.  
Se aplica una política restrictiva en INPUT y se permiten únicamente los puertos necesarios.

## 1. Estado del firewall

Se comprueba el estado de las reglas de iptables:

<img width="1023" height="655" alt="image" src="https://github.com/user-attachments/assets/c6d139de-fb39-4c1b-b2cc-5848cb4a0470" />


## 2. Configuracion de reglas

Se permite el acceso al servicio Nginx:
<img width="1022" height="28" alt="image" src="https://github.com/user-attachments/assets/a522a74f-24cd-4228-ac3f-9f7e491e7171" />

Se permite el acceso por SSH:
<img width="1020" height="32" alt="image" src="https://github.com/user-attachments/assets/d4f1b667-67c6-439e-8e0d-cdf8390681e4" />

Se configura para que sean permanentes despues de un reinicio:

<img width="1023" height="18" alt="image" src="https://github.com/user-attachments/assets/8f159d67-f291-4245-81ac-a75614197a85" />

