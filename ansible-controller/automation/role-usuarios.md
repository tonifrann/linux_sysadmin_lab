# Rol: usuarios

Este rol garantiza que el usuario administrativo ```admin``` está correctamente configurado en todos los servidores gestionados por Ansible.


## 1. Funciones del rol

El rol realiza:

Verifica que el usuario admin existe

Establece /bin/bash como shell

Añade sudo sin contraseña mediante /etc/sudoers.d/admin
