# Playbooks

Los playbooks permiten aplicar aplicar configuraciones de manera automática en los hosts definidos en el inventario.

En este entorno se utilizan para configurar los servidores Linux gestionados por Ansible aplicando los roles definidos previamente.


## 1. Playbook general

Con este playbook se aplican configuraciones comunes en los servidores del inventario.

<img width="1022" height="17" alt="image" src="https://github.com/user-attachments/assets/afb632cf-0fc7-4167-8955-5cca1e1c4065" />

<img width="1022" height="149" alt="image" src="https://github.com/user-attachments/assets/20f5e6c2-8c52-4c79-b230-3d471bb0915f" />


Este playbook garantiza que cualquier servidor nuevo queda:

- con el usuario admin correctamente configurado

- con herramientas básicas instaladas

- actualizado

- con firewall activo y con reglas aplicadas

- monitorizado con Node Exporter


## 2. Playbook para node-exporter

Playbook dedicado únicamente a la instalación y configuración de Node Exporter.

<img width="1023" height="20" alt="image" src="https://github.com/user-attachments/assets/89dfb606-49ad-4324-81ee-398ce9224a01" />

<img width="1024" height="87" alt="image" src="https://github.com/user-attachments/assets/8328e181-7344-49dd-a5f8-de4371b88f10" />

El funcionamiento del rol (tareas YAML, servicio systemd, etc.) está documentado en [rol node exporter](./role-node-exporter.md)

## 3. Playbook para firewalld

Playbook utilizado para aplicar reglas de firewall según el servidor.

<img width="1023" height="19" alt="image" src="https://github.com/user-attachments/assets/59fb0304-d3aa-4b46-8d99-1c1d82e816e2" />

<img width="1024" height="82" alt="image" src="https://github.com/user-attachments/assets/84ff9c42-296e-4651-89c6-30abe574e626" />

Los puertos se definen con variables en: ```/etc/ansible/host_vars/```.

- ```host_vars/monitoring.yml```
<img width="1025" height="81" alt="image" src="https://github.com/user-attachments/assets/096ef70d-92b9-48e6-9b40-bed30216310a" />

- ```host_vars/fog_server.yml```

<img width="1024" height="147" alt="image" src="https://github.com/user-attachments/assets/446e5a99-b7a8-42f4-9f7b-9e80547080d8" />

El funcionamiento del rol esta documentado en [rol firewalld](./role-firewalld.md)


## 4. Ejecución de los playbooks

Se comprueba que la sintaxis es correcta:
<img width="1022" height="49" alt="image" src="https://github.com/user-attachments/assets/e09d32b3-9383-48a6-82ae-d800627d3915" />

Se ejecuta el playbook:
<img width="1022" height="216" alt="image" src="https://github.com/user-attachments/assets/99ae3ba5-bdf2-4e16-ab56-9461a5c349c4" />

Se revisa los hosts detectados:
<img width="1025" height="83" alt="image" src="https://github.com/user-attachments/assets/2ab049eb-1119-4cc8-9174-1447dc50160e" />





