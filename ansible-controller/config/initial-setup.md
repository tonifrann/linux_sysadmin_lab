# Configuración inicial del entorno

Se documentan los pasos necesarios que se deben realizar en cada uno de los servidores que estan gestionados con Ansible.

- Monitoring
- Docker
- Fog-server


## 1. Usuario administrador

Se crea un usuario administrador ```admin``` con acceso SSH y privilegios de sudoers para que no sea necesario escribir la contraseña cada vez.

Este usuario se utilizará unicamente para la automatización con Ansible.

<img width="1021" height="130" alt="image" src="https://github.com/user-attachments/assets/3fb11ae3-ea75-4c16-9825-24833f917135" />


## 2. SSH

Se verifica que SSH está instalado y activo:
<img width="1023" height="66" alt="image" src="https://github.com/user-attachments/assets/10ec1162-0f49-4bdd-93a1-1d4250baeea9" />

Se verifica que SSH está permitido en el firewall:
<img width="1024" height="33" alt="image" src="https://github.com/user-attachments/assets/c29fe7df-0e9a-4bb1-865b-9b354c36ca3e" />


## 3. Clave SSH del controlador

En el controlador de Ansible se genera una clave SSH sin contraseña:
<img width="1022" height="384" alt="image" src="https://github.com/user-attachments/assets/4b22b82b-ef65-4da4-a5f5-30dcbb0319b9" />

La clave pública se copia en cada servidor:
<img width="1024" height="233" alt="image" src="https://github.com/user-attachments/assets/be6c8580-2cd8-4b1e-b08d-163a21ad4bee" />

