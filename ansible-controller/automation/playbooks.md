# Playbooks

Los playbooks permiten aplicar aplicar configuraciones de manera automática en los hosts definidos en el inventario.

En este entorno se utilizan para configurar los servidores Linux gestionados por Ansible aplicando los roles definidos previamente.


## 1. Playbook general

Con este playbook se aplican configuraciones comunes en los servidores del inventario.

<img width="1022" height="17" alt="image" src="https://github.com/user-attachments/assets/afb632cf-0fc7-4167-8955-5cca1e1c4065" />

<img width="1022" height="149" alt="image" src="https://github.com/user-attachments/assets/20f5e6c2-8c52-4c79-b230-3d471bb0915f" />


Este playbook hace que cualquier servidor nuevo:

- Se configure el usuario admin correctamente

- Se instale herramientas básicas 

- Se actualice el sistema

- Se active el firewall y se apliquen reglas base

- Se instale y configure Node Exporter para monitorizar


## 2. Playbook para usuarios

Playbook usitlizado para configurar correctamente el usuario ```admin```

<img width="1021" height="20" alt="image" src="https://github.com/user-attachments/assets/13b6d1cf-0434-4a70-a089-8d0a026d99ca" />

<img width="1024" height="86" alt="image" src="https://github.com/user-attachments/assets/6dc98ecb-f156-4511-a359-88ffad539f4b" />


## 3. Playbook para paquetes-base

Playbook utilizado para instalar herramientas basicas del sistema.

<img width="1023" height="20" alt="image" src="https://github.com/user-attachments/assets/8078ea53-9827-4859-895f-e14671f626cf" />

<img width="1024" height="90" alt="image" src="https://github.com/user-attachments/assets/cd95762e-90a6-440c-8318-27988fe71ad8" />


## 4. Playbook para update

Playbook utilizado para hacer el update del sistema.

<img width="1021" height="19" alt="image" src="https://github.com/user-attachments/assets/293b9ffe-d1d8-4dc4-8918-f2a72696972a" />

<img width="1021" height="82" alt="image" src="https://github.com/user-attachments/assets/ee2001b3-e166-4981-bc31-cd74b783154f" />


## 5. Playbook para firewalld

Playbook utilizado para aplicar reglas del firewall definidas en el rol.

<img width="1023" height="19" alt="image" src="https://github.com/user-attachments/assets/59fb0304-d3aa-4b46-8d99-1c1d82e816e2" />

<img width="1024" height="82" alt="image" src="https://github.com/user-attachments/assets/84ff9c42-296e-4651-89c6-30abe574e626" />

El funcionamiento del rol esta documentado en [rol firewalld](./role-firewalld.md)


## 6. Playbook para node-exporter

Playbook dedicado únicamente a la instalación y configuración de Node Exporter.

<img width="1023" height="20" alt="image" src="https://github.com/user-attachments/assets/89dfb606-49ad-4324-81ee-398ce9224a01" />

<img width="1024" height="87" alt="image" src="https://github.com/user-attachments/assets/8328e181-7344-49dd-a5f8-de4371b88f10" />

El funcionamiento del rol está documentado en [rol node exporter](./role-node-exporter.md)


## 7. Ejecución de los playbooks

Se comprueba que la sintaxis es correcta:
<img width="1022" height="49" alt="image" src="https://github.com/user-attachments/assets/e09d32b3-9383-48a6-82ae-d800627d3915" />

Se ejecuta el playbook:
<img width="1021" height="152" alt="image" src="https://github.com/user-attachments/assets/bc9a6422-0f92-4b69-8a1a-403f884c4353" />

Se revisa los hosts detectados:
<img width="1020" height="53" alt="image" src="https://github.com/user-attachments/assets/9761a1ba-050b-4ef2-8c5f-3d8c80b57ecc" />






