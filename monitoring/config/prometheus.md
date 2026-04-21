# Prometheus

Prometheus es el servicio encargado de recolectar y almacenar métricas del laboratorio.  
En este servidor se ejecuta como servicio principal del stack de monitorización.


## 1. Estado del servicio

Se comprueba que Prometheus está instalado, activo y escuchando en el puerto correspondiente:

<img width="1021" height="432" alt="image" src="https://github.com/user-attachments/assets/c12f7fa1-f37a-4d55-acd9-596e7ad07877" />


## 2. Configuración principal 
   
Se configuran los targets ```core-linux``` y ```docker-host```:

<img width="995" height="20" alt="image" src="https://github.com/user-attachments/assets/dca2ae9d-7270-4dc3-a5f7-d21ce3ec6df1" />

<img width="990" height="87" alt="image" src="https://github.com/user-attachments/assets/2c217103-a341-407c-b41e-1b1f15936817" />

Se valida que el archivo de configuración funcione correctamente:

<img width="994" height="55" alt="image" src="https://github.com/user-attachments/assets/e6dd40eb-a9eb-4ea1-8eb4-b42fdf1f5708" />


## 3. Node Exporter

Para que los targets aparezcan en estado UP, es necesario instalar [node_exporter(../node-exporter.md)


## 4. Comprobación de targets
Se revisa el estado de los targets desde la interfaz web:
http://<IP>:9090/targets

## 5. Métricas disponibles

Se validan métricas desde la interfaz:


## 6. Logs del servicio

Se revisan logs para detectar errores o fallos de configuración:
journalctl -u prometheus -xe
