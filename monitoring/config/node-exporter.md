# Node Exporter

Node Exporter se utiliza para exponer métricas del sistema (CPU, RAM, disco, red) que Prometheus recoge posteriormente.  
En este laboratorio se instala en el servidor de monitorización (192.168.100.11).

---

## 1. Instalación

### Descarga y extracción del binario
```bash
cd /opt
sudo wget https://github.com/prometheus/node_exporter/releases/latest/download/node_exporter-*.linux-amd64.tar.gz
sudo tar -xvf node_exporter-*.linux-amd64.tar.gz
sudo mv node_exporter-*.linux-amd64 node_exporter
