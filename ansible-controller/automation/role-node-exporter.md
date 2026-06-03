# Rol: node exporter

Este rol automatiza la instalación y configuración de Node Exporter en los servidores con Linux. De esta forma, cualquier host que se añada al inventario estará listo para ser monitorizado con Prometheus.


## 1. Funciones del rol

El rol realiza automáticamente:

- Eliminación del paquete prometheus-node-exporter si existe

- Descarga del binario oficial desde GitHub

- Descompresión del archivo

- Instalación en /opt/node_exporter

- Creación del usuario node_exporter sin shell

- Asignación de permisos correctos

- Creación del servicio systemd

- Habilitación y arranque del servicio


## 2. Tareas del rol

Se crea y modifica el archivo de configuración del rol:
<img width="1022" height="17" alt="image" src="https://github.com/user-attachments/assets/9a8a8c9a-e089-4061-b00b-a7f1c285b6ea" />

<img width="1023" height="643" alt="image" src="https://github.com/user-attachments/assets/458d5f74-e2c2-4a6d-82c5-ac9f5e2a209a" />
<img width="1023" height="243" alt="image" src="https://github.com/user-attachments/assets/b78c1ebf-6c23-4c3e-bd09-7f34ea422d08" />


