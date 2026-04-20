
# monitoring (Ubuntu 22.04)

Servidor de monitorización, orientado a la recogida de métricas, visualización y control del estado de los sistemas.

## Que se ha implementado en el servidor

- Monitorización centralizada con Prometheus
- Métricas del sistema con Node Exporter
- Visualización mediante Grafana
- Integración con core-linux y docker-host
- Comprobación del estado de servicios y recursos
- Resolución de incidencias durante la configuración

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

### 5. Incidencias simuladas
- [Target DOWN](incidents/target-down.md)
- [Error en prometheus.yml](incidents/prometheus-config-error.md)

---

## Estructura del repositorio
- `architecture/` → Diagramas y notas de diseño.
- `config/` → Configuración de servicios de monitorización.
- `integration/` → Integración con otros sistemas y dashboards.
- `incidents/` → Incidencias y resolución.

## Estado
Servidor operativo y monitorizando sistemas.
