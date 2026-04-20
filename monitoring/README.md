
# monitoring (Ubuntu 22.04)

Servidor de monitorización central del laboratorio, encargado de la recolección, almacenamiento y visualización de métricas del entorno Linux.

Permite supervisar el estado de los sistemas, detectar incidencias y analizar el rendimiento de la infraestructura.


## Que se ha implementado en el servidor

- Monitorización centralizada con Prometheus
- Recolección de métricas del sistema con Node Exporter
- Visualización de datos mediante Grafana
- Supervisión de core-linux y docker-host
- Monitorización de CPU, RAM, disco y red
- Detección de servicios caídos (UP/DOWN)

## Índice

### 1. Introducción
- [Descripción general](#descripción-general)

### 2. Servicios del servidor
- [Prometheus](config/prometheus.md)
- [Node Exporter](config/node-exporter.md)
- [Grafana](config/grafana.md)

### 3. Integración
- [Targets monitorizados](integration/targets.md)
- [Dashboards](integration/dashboards.md)

### 4. Arquitectura del sistema
- [Diagrama](architecture/diagram.png)

### 5. Incidencias
- [Target DOWN](incidents/target-down.md)
- [Error en prometheus.yml](incidents/prometheus-config-error.md)


## Estructura del repositorio
- `architecture/` → Diagramas y notas de diseño.
- `config/` → Configuración de servicios de monitorización.
- `integration/` → Integración con otros sistemas y dashboards.
- `incidents/` → Incidencias y resolución.


## Flujo de monitorización

Los servidores (core-linux, docker-host) exponen métricas con Node Exporter
Prometheus recoge esas métricas automáticamente
Grafana las usa para mostrarlas en dashboards

La frecuencia de recogida se define en ```prometheus.yml```
