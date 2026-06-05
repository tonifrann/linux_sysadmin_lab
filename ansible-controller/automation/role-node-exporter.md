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

El rol automatiza todo el proceso de instalación y configuración de Node Exporter:
<img width="1022" height="17" alt="image" src="https://github.com/user-attachments/assets/9a8a8c9a-e089-4061-b00b-a7f1c285b6ea" />

<img width="1023" height="643" alt="image" src="https://github.com/user-attachments/assets/458d5f74-e2c2-4a6d-82c5-ac9f5e2a209a" />
<img width="1023" height="243" alt="image" src="https://github.com/user-attachments/assets/b78c1ebf-6c23-4c3e-bd09-7f34ea422d08" />


## 3. Plantilla del servicio systemd

Se crea una plantilla del servicio de systemd:
<img width="1022" height="18" alt="image" src="https://github.com/user-attachments/assets/d7e56e69-716f-4235-b7d7-d99b98d5d2ff" />
<img width="1022" height="195" alt="image" src="https://github.com/user-attachments/assets/a6ba6a19-5848-42d0-83bc-6cef6361f3b5" />


## 4. Ejecución del rol

<img width="1023" height="17" alt="image" src="https://github.com/user-attachments/assets/18d906f1-cc18-4b62-8cad-cccb5b81943e" />

Después de ejecutar el playbook: 

- El servicio node_exporter queda instalado y activo.

- El puerto 9100/tcp tiene que abrirse utilizando el rol firewalld.

- Las métricas quedan disponibles para Prometheus.
