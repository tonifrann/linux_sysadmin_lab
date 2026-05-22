# Instalación y configuración de Ansible Core

Ansible-controller (Rocky Linux 9) es el servidor encargado de centralizar la automatización con Ansible Core.


## 1. Instalación de Ansible Core

Se instala Ansible Core desde el repositorio oficial de Rocky Linux.
<img width="1022" height="21" alt="image" src="https://github.com/user-attachments/assets/3441f565-8be0-4e34-932c-9b42f3f35427" />

Se valida la instalación y la versión:
<img width="1022" height="160" alt="image" src="https://github.com/user-attachments/assets/fd1b32da-8643-44bd-bf3b-306b6d553299" />


## 2. Estructura del entorno

La estructura desoues de la instalación es:
<img width="1020" height="86" alt="image" src="https://github.com/user-attachments/assets/2e7c94c3-e6c7-4c9c-b825-2ffc1b58915f" />

- ansible.cfg → configuración general

- hosts → inventario del laboratorio

- roles/ → roles reutilizables


## 3. Configuración

Se configura el archivo ```/etc/ansible/ansible.cfg``` para utilizar el inventario y los roles del sistema:
<img width="1024" height="309" alt="image" src="https://github.com/user-attachments/assets/a85e6d48-f800-4d41-9e3b-ca40d8654258" />

