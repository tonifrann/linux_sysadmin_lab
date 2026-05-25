# Configuración de Firewall (firewalld)

La configuración del firewall en el servidor de ansible-controller se realiza con firewalld. 

Se permite solamente el acceso necesario para la administración remota con SHH y la gestión de hosts Windows con WinRM.


## 1. Estado del servicio
Se comprueba que firewalld está activo y habilitado:
<img width="1023" height="258" alt="image" src="https://github.com/user-attachments/assets/ba2a7b9b-6e8e-4be5-887f-fd9c7594ae43" />


## 2. Reglas aplicadas

Se añaden las reglas necesarias para permitir SSH y WinRM:
