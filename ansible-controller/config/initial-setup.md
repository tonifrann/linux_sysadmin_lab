# Configuración inicial del entorno

Se documentaran los pasos necesarios que hay que realizar en los servidores que se gestionaran con Ansible.

## 1. Usuario administrador
Se crea un usuario administrador ```admin``` con acceso SSH y privilegios de sudo sin necesidad de escribir la contraseña en cada uno de los servidores donde se ultilaza Ansible.

<img width="1023" height="160" alt="image" src="https://github.com/user-attachments/assets/3217564c-465f-48a9-85bc-f0746b31bad4" />

Los servidores son:
- Core-linux
- Monitoring
- Docker


## 2. SSH

Se resiva que SHH está activo y permitido en el firewall
