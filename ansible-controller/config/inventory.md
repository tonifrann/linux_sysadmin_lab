# Inventario de Ansible

En el inventario se definen los hosts linux que se gestionan con Ansible. 


## 1. Inventario 

Se modifica el archivo ```/etc/ansible/hosts``` y se añade el servidor ```ansible-test``` que se gestiona con SSH. En este archivo se irán añadiendo los nuevos servidores que se quieran gestionar con Ansible.
<img width="1023" height="51" alt="image" src="https://github.com/user-attachments/assets/97b79ad1-5480-44eb-ad0f-02d402161418" />


## 2. Verificación de la conectividad

Se verifica que el host responde correctamente con el modulo ```ping```:
<img width="1021" height="133" alt="image" src="https://github.com/user-attachments/assets/646ce5b7-a817-478d-a910-a9095efa6b01" />

Se utiliza un inventario estático, manteniendo toda la definición de hosts en ```/etc/ansible/hosts```



