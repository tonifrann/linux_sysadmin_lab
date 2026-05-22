# docker-host (Ubuntu 22.04)

Es un servidor dedicado a la ejecución de contenedores Docker. Se podrá desplegar servicios aislados, hacer pruebas con Docker Engine y gestionar aplicaciones con Docker Compose.

---

## Caracteristicas del servidor

- Instalación de Docker Engine
- Instalación de Docker Compose
- Redes internas con Docker Networks
- Persistencia mediante volúmenes Docker
- Node Exporter para Prometheus
- Configuración del firewall
- Integración con el servidor de monitorización
- Resolución de incidencias

---

## Índice

### 1. Introducción
- [Descripción general](#descripción-general)

### 2. Servicios del servidor
- [Docker Engine](config/docker-engine.md)
- [Docker Compose](config/docker-compose.md)
- [Docker Networks](config/docker-networks.md)
- [Volúmenes y persistencia](config/volumes.md)
- [Firewall (iptables)](config/iptables.md)

### 3. Contenedores
- [Servicios desplegados](containers/containers.md)

### 4. Arquitectura del sistema
- [Diagrama](architecture/diagram.png)

### 5. Incidencias
- [Error en Docker Engine](incidents/docker-engine-error.md)
- [Contenedor no arranca](incidents/container-failed.md)

---

## Estructura del repositorio
- `architecture/` → Diagramas y notas de diseño.
- `config/` → Configuración de Docker Engine, Compose y Node Exporter.
- `containers/` → Contenedores desplegados en el servidor.
- `incidents/` → Incidencias y su resolución.
