# Prometheus

Prometheus es el servicio encargado de recolectar y almacenar métricas del laboratorio.  
En este servidor se ejecuta como servicio principal del stack de monitorización.


## 1. Estado del servicio

Se comprueba que Prometheus está instalado, activo y escuchando en el puerto correspondiente:

<img width="1021" height="432" alt="image" src="https://github.com/user-attachments/assets/c12f7fa1-f37a-4d55-acd9-596e7ad07877" />


## 2. Configuración principal 
   
Se configuran los targets ```core-linux``, ```monitoring``` y ```docker-host```:
<img width="1022" height="18" alt="image" src="https://github.com/user-attachments/assets/ae2796f2-cc8d-4e0e-a997-7f14186bdbaf" />

<img width="1020" height="85" alt="image" src="https://github.com/user-attachments/assets/73e85694-196e-40ee-af14-a02a98b44879" />

Se configuran los targets por nombre en lugar de por IP para facilitar la gestión desde Prometheus.  Los nombres añaden en `/etc/hosts` del servidor de monitorización.

<img width="1021" height="213" alt="image" src="https://github.com/user-attachments/assets/b5c3147e-71e7-4295-929b-23421c859255" />


Se valida que el archivo de configuración funcione correctamente:

<img width="1023" height="77" alt="image" src="https://github.com/user-attachments/assets/5f56a7be-6b21-4586-add4-165ac71f090a" />


## 3. Node Exporter

Para que los targets aparezcan en estado UP, es necesario instalar [node_exporter](./node-exporter.md)


## 4. Comprobación de targets
Se revisa el estado de los targets desde la interfaz web:

<img width="1419" height="777" alt="image" src="https://github.com/user-attachments/assets/d26ed25d-9682-4b93-a503-6ca7ddb5f51f" />


## 5. Métricas disponibles

Se consultan algunas métricas desde la interfaz web para validar su funcionamiento:

<img width="1911" height="728" alt="image" src="https://github.com/user-attachments/assets/d1f03b2d-ee28-481e-947c-6d0728153d70" />


## 6. Logs del servicio

Se revisan logs para detectar errores o fallos de configuración con el comando ```journalctl -u prometheus -xe``` pero no se muestra ningun error.


## 7. Validación del sistema

- Prometheus accesible en http://192.168.100.11:9090
- Targets en estado UP
- Métricas disponibles
- Sin errores en logs
