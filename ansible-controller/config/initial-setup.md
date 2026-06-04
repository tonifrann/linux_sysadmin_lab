# Configuración inicial del entorno

Este documento muestra los pasos previos necesarios para que un servidor Linux pueda ser gestionado con Ansible


## 1. Usuario inicial del sistema

Durante la instalación del sistema operativo se crea un usuario inicial (por ejemplo: toni)

Este usuario se utilizará únicamente para el acceso SSH inicial y para ejecutar el bootstrap de Ansible.

El usuario administrador definitivo (admin) se creará automáticamente mediante un rol de Ansible.


## 2. SSH

Para que Ansible funcione correctamente, SSH debe estar instalado y activo. Si no fuera así, habría que instalar el servicio ```openssh-server``` y comprobar que se tiene acceso SSH.

<img width="1023" height="15" alt="image" src="https://github.com/user-attachments/assets/9eeddd56-fd3d-497d-a0eb-044aa09239ff" />
<img width="1022" height="14" alt="image" src="https://github.com/user-attachments/assets/186b5b5b-86b0-40da-b1e6-dcedc6b8680a" />


## 3. Clave SSH del controlador

En el controlador de Ansible se genera una clave SSH sin contraseña:
<img width="1022" height="384" alt="image" src="https://github.com/user-attachments/assets/4b22b82b-ef65-4da4-a5f5-30dcbb0319b9" />

La clave pública se copia en el usuario inicial del servidor:
<img width="1024" height="233" alt="image" src="https://github.com/user-attachments/assets/be6c8580-2cd8-4b1e-b08d-163a21ad4bee" />

Una vez hecho esto, el servidor ya puede recibir el playbook de bootstrap que creará el usuario admin y aplicará la configuración inicial.
