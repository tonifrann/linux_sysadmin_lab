# Prometheus

Prometheus es el servicio encargado de recolectar y almacenar métricas del laboratorio.  
En este servidor se ejecuta como servicio principal del stack de monitorización.


## 1. Estado del servicio

Se comprueba que Prometheus está instalado, activo y escuchando en el puerto correspondiente:

systemctl status prometheus
ss -tulnp | grep 9090

## 2. Configuración principal 
   
Se configura:
/etc/prometheus/prometheus.yml

Se valida:

promtool check config /etc/prometheus/prometheus.yml

## 3. Comprobación de targets
Se revisa el estado de los targets desde la interfaz web:
http://<IP>:9090/targets

## 4. Métricas disponibles

Se validan métricas desde la interfaz:


## 5. Logs del servicio

Se revisan logs para detectar errores o fallos de configuración:
journalctl -u prometheus -xe
