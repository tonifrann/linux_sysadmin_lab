# Instalación y configuración de Ansible Core

Ansible-controller (Rocky Linux 9) es el servidor donde se instala Ansible Core, para realizar las configuracienes iniciales necesarias para gestionar hosts Linux y Windows.


## 1. Instalación de Ansible Core

Se instala Ansible Core desde el repositorios oficial de Rocky Linux.
<img width="1022" height="21" alt="image" src="https://github.com/user-attachments/assets/3441f565-8be0-4e34-932c-9b42f3f35427" />

Se veridica la instalación:
<img width="1022" height="160" alt="image" src="https://github.com/user-attachments/assets/fd1b32da-8643-44bd-bf3b-306b6d553299" />


## 2. Estructura del entorno

La estructura es:
<img width="1020" height="86" alt="image" src="https://github.com/user-attachments/assets/2e7c94c3-e6c7-4c9c-b825-2ffc1b58915f" />

- ansible.cfg → configuración general

- hosts → inventario del laboratorio

- roles/ → roles reutilizables
