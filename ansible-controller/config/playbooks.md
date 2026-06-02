# Playbooks

Los playbooks se utilizan para aplicar configuraciones de de manera automática en los servidores que se vayan definicendo en el inventario.

En este entorno se utilizan los roles node-exporter y firewalld. 


## 1. Playbook general

Este playbook aplica los roles comunes para cualquier servidor nuevo que se añada al inventario. En el laboratorio, todos los servidores ya se configuraron manualmente. 

<img width="1022" height="17" alt="image" src="https://github.com/user-attachments/assets/afb632cf-0fc7-4167-8955-5cca1e1c4065" />

<img width="1024" height="96" alt="image" src="https://github.com/user-attachments/assets/5edb95c1-9c9e-4507-8576-d7ec3ecb61a5" />

- Instala y configura Node Exporter

- Activa firewalld y abre los puertos definidos en host_vars

- Garantiza que cualquier servidor nuevo queda monitorizado y con unas reglas básicas de firewall 


## 2. Playbook para node-exporter

Este playbook solo configura el rol de Node Exporter. Se usa cuando se quiere añadir un servidor nuevo a la monitorización.

<img width="1023" height="20" alt="image" src="https://github.com/user-attachments/assets/89dfb606-49ad-4324-81ee-398ce9224a01" />

<img width="1024" height="87" alt="image" src="https://github.com/user-attachments/assets/8328e181-7344-49dd-a5f8-de4371b88f10" />





