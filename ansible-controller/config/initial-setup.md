# Configuración inicial del entorno

Se documentan los pasos necesarios que hay que realizar en cada uno de los servidores que se gestionaran con Ansible.

- Core-linux
- Monitoring
- Docker

## 1. Usuario administrador

Se crea un usuario administrador ```admin``` con acceso SSH y privilegios de sudoers para que no sea necesario escribir la contraseña cada vez.
<img width="1023" height="160" alt="image" src="https://github.com/user-attachments/assets/3217564c-465f-48a9-85bc-f0746b31bad4" />


## 2. SSH

Se resiva que SHH está activo:
<img width="1025" height="68" alt="image" src="https://github.com/user-attachments/assets/242c5244-d3f3-453d-a278-439777a6ec5b" />

Se revisa que SHH esta permitido en el firewall:
<img width="1021" height="33" alt="image" src="https://github.com/user-attachments/assets/baccaa21-6fda-46fe-9d92-da7621aab029" />


## 3. Clave SSH del controlador

Se genera una clave SSH en el controlador de Ansible sin contraseña:
<img width="1022" height="384" alt="image" src="https://github.com/user-attachments/assets/4b22b82b-ef65-4da4-a5f5-30dcbb0319b9" />

Se copia la clave publica en cada servidor:
