# ansible-test (Ubuntu 22.04)

Este servidor se utiliza únicamente para probar los roles y playbooks de Ansible para asegurar que funcionen correctamente, antes de aplicarlos en servidores nuevos.

Se pueden validar las configuraciones y detectar cualquier error. de esta manera, nos aseguramos que los roles funcionan correctamente en un entorno controlado.


## Estado inicial del servidor

- Ubuntu Server 22.04 recién instalado

- Usuario admin con acceso SSH con la clave pública del servidor ansible-controller

- Sin Node Exporter

- Sin reglas de firewall

- Sin configuraciones adicionales


## Pruebas realizadas con Ansible

Aqui se edocumentan las pruebas que se han ejecutado desde ansible-controller sobre este servidor.


## 1.- Prueba del rol usuarios

Se ejecuta el playbook ```usuarios```

<img width="1024" height="18" alt="image" src="https://github.com/user-attachments/assets/59f0989e-2b65-4970-87ac-d2a8f5549842" />
