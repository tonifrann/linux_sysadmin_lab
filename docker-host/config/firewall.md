# Firewall

En este servidor se utiliza unicamente iptables.  
Docker gestiona automáticamente sus propias reglas (cadenas DOCKER, DOCKER-FORWARD, DOCKER-USER), asi que no es necesario instalar firewalld.  
Se aplica una política restrictiva en INPUT y se permiten únicamente los puertos necesarios.

## 1. Estado del firewall

Se comprueba el estado de las reglas de iptables:

<img width="1023" height="655" alt="image" src="https://github.com/user-attachments/assets/c6d139de-fb39-4c1b-b2cc-5848cb4a0470" />


## 2. Reglas necesarias para Docker

Docker gestiona automáticamente sus propias reglas de iptables.  
No es necesario abrir puertos manualmente para el funcionamiento interno.
