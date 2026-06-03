# Rol: node exporter

Este rol automatiza la instalación y configuración de Node Exporter en los servidores con Linux. De esta forma, cualquier host que se añada al inventario estará listo para ser monitorizado con Prometheus.


## 1. Funciones del rol

El rol realiza automáticamente:

- Descarga del binario oficial de Node Exporter

- Creación del usuario de servicio node_exporter

- Instalación del binario en /opt/node_exporter

- Generación de la unidad systemd mediante plantilla

- Habilitación y arranque del servicio

- Apertura del puerto 9100/tcp mediante el rol firewalld (si aplica)
