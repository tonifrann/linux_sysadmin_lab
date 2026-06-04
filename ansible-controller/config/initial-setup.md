# Configuración inicial del entorno

Este documento muestra los pasos previos necesarios para que un servidor Linux pueda ser gestionado con Ansible


## 1. 1. Usuario inicial del sistema

Durante la instalación del sistema operativo se crea un usuario inicial (por ejemplo: toni)

Este usuario se utilizará únicamente para el acceso SSH inicial y para ejecutar el bootstrap de Ansible.

El usuario administrador definitivo (admin) se creará automáticamente mediante un rol de Ansible.

<img width="1021" height="130" alt="image" src="https://github.com/user-attachments/assets/3fb11ae3-ea75-4c16-9825-24833f917135" />


## 2. SSH

Para que Ansible funcione correctamente, SHH debe estar en funcionamiento. Si no fuera asi habria que instalar el servicio ```openssh-server``` y permitir el servicio SSH en el firewall.

  
-  Sino esta ins
Se verifica que SSH está instalado y activo:
<img width="1023" height="66" alt="image" src="https://github.com/user-attachments/assets/10ec1162-0f49-4bdd-93a1-1d4250baeea9" />

Se verifica que SSH está permitido en el firewall:
<img width="1024" height="33" alt="image" src="https://github.com/user-attachments/assets/c29fe7df-0e9a-4bb1-865b-9b354c36ca3e" />


## 3. Clave SSH del controlador

En el controlador de Ansible se genera una clave SSH sin contraseña:
<img width="1022" height="384" alt="image" src="https://github.com/user-attachments/assets/4b22b82b-ef65-4da4-a5f5-30dcbb0319b9" />

La clave pública se copia en cada servidor:
<img width="1024" height="233" alt="image" src="https://github.com/user-attachments/assets/be6c8580-2cd8-4b1e-b08d-163a21ad4bee" />
