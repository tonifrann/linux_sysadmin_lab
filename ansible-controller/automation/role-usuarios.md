# Rol: usuarios

Este rol garantiza que el usuario administrativo ```admin``` está correctamente configurado en todos los servidores gestionados por Ansible.


## 1. Funciones del rol

El rol realiza automáticamente:

- Verifica que el usuario admin existe

- Establece /bin/bash como shell

- Añade sudo sin contraseña mediante /etc/sudoers.d/admin


## 2. Tareas del rol

El rol se asegura de que el usuario ```admin``` este configurado de forma homogenea.

<img width="1022" height="214" alt="image" src="https://github.com/user-attachments/assets/ec318e6d-db17-4f19-9780-df1f90e8dc50" />
