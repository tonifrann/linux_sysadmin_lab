
# monitoring (Ubuntu 22.04)

El servidor de monitorización es el encargado de recopilar, almacenar y mostrar métricas del entorno Linux.

Este servidor permite supervisar el estado de los sistemas, detectar cualquier incidencia y analizar el rendimiento de la infraestructura.

---

## Caracteristicas del servidor

- Monitorización: Prometheus para recolección de métricas
  
- Exporters: Node Exporter en hosts Linux
  
- Visualización: Grafana para dashboards
  
- Supervisión: CPU, RAM, disco, red y estado UP/DOWN
  
- Integración: core-linux y docker-host como targets
  
- Firewall: control de acceso con firewalld

---

## Índice

### 1. Introducción
- [Descripción general](#descripción-general)

### 2. Servicios del servidor
- [Prometheus](config/prometheus.md)
- [Node Exporter](config/node-exporter.md)
- [Grafana](config/grafana.md)
- [Firewall (firewalld)](config/firewalld.md)

### 3. Integración
- [Targets monitorizados](integration/targets.md)
- [Dashboards](integration/dashboards.md)

### 4. Arquitectura del sistema
- [Diagrama](architecture/diagram.png)

### 5. Incidencias
- [Target DOWN](incidents/target-down.md)
- [Error en prometheus.yml](incidents/prometheus-config-error.md)

---

## Estructura del repositorio
- `architecture/` → Diagramas y notas de diseño.
- `config/` → Configuración de servicios de monitorización.
- `integration/` → Integración con otros sistemas y dashboards.
- `incidents/` → Incidencias y su resolución.

---

## Flujo de monitorización

- Los servidores (core-linux, docker-host) envian métricas a través de Node Exporter.
- Prometheus se encarga de recopilar esas métricas automáticamente
- Grafana utiliza estas métricas para mostrarlas en cuadros de mando.

La frecuencia con la que se recogen las métricas se configura en el archivo ```prometheus.yml```
