# Prometheus

Prometheus es el servicio encargado de recolectar y almacenar métricas del laboratorio.  
En este servidor se ejecuta como servicio principal del stack de monitorización.


## 1. Estado del servicio

Se comprueba que Prometheus está instalado, activo y escuchando en el puerto correspondiente:

<img width="1021" height="432" alt="image" src="https://github.com/user-attachments/assets/c12f7fa1-f37a-4d55-acd9-596e7ad07877" />


## 2. Configuración principal 
   
Se configuran los targets ```core-linux```, ```monitoring``` y ```docker-host```:

<img width="1022" height="18" alt="image" src="https://github.com/user-attachments/assets/ae2796f2-cc8d-4e0e-a997-7f14186bdbaf" />

<img width="1021" height="82" alt="image" src="https://github.com/user-attachments/assets/9da12f53-2b73-4dd1-9104-956be7951a1d" />


Se valida que el archivo de configuración funcione correctamente:

<img width="994" height="55" alt="image" src="https://github.com/user-attachments/assets/e6dd40eb-a9eb-4ea1-8eb4-b42fdf1f5708" />


## 3. Node Exporter

Para que los targets aparezcan en estado UP, es necesario instalar [node_exporter](./node-exporter.md)


## 4. Comprobación de targets
Se revisa el estado de los targets desde la interfaz web:
http://<IP>:9090/targets

## 5. Métricas disponibles

Se validan métricas desde la interfaz:


## 6. Logs del servicio

Se revisan logs para detectar errores o fallos de configuración:
journalctl -u prometheus -xe


## 7. Integración
Prometheus se integra con:

Node Exporter → métricas de servidores

Grafana → visualización

Alertmanager → alertas (si está configurado)

📸 Captura: Prometheus como datasource en Grafana
