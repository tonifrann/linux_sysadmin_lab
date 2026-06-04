# Inventario de Ansible

En el inventario se definen los hosts linux que se gestionan con Ansible. 


## 1. Inventario 

Se modifica el archivo ```/etc/ansible/hosts``` y se añade el servidor ```ansible-test``` que se gestiona con SSH. Aqui se deben ir añadiendo los nuevos servidores que se quieran gestionar con ansible enun futuro.
<img width="1023" height="51" alt="image" src="https://github.com/user-attachments/assets/97b79ad1-5480-44eb-ad0f-02d402161418" />


## 2. Verificación de la conectividad

Se verifica que el host responde correctamente con el modulo ```ping```:
<img width="1020" height="354" alt="image" src="https://github.com/user-attachments/assets/92840ae9-e1dc-42da-9e33-eb5fec396ebc" />


