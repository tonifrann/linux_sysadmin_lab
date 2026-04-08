# Linux Sysadmin Lab

Laboratorio práctico de administración de sistemas Linux que simula una infraestructura real de empresa.

Diseñado para demostrar despliegue, seguridad, monitorización, automatización y resolución de incidencias en múltiples servidores.

---

## Tecnologías y áreas trabajadas

- Administración Linux (Rocky / Ubuntu)
- Seguridad: SELinux, firewalls, hardening
- Redes y servicios
- Contenedores (Docker)
- Monitorización (Prometheus, Grafana)
- Backups y recuperación
- Automatización (Ansible, scripts)
- Troubleshooting real
- Integración Windows/Linux

---

## Arquitectura del laboratorio

| Servidor | Distro | Rol |
|----------|--------|-----|
| core-linux | Rocky Linux 9 | Servicios base, seguridad, almacenamiento |
| docker-host | Ubuntu 22.04 | Contenedores y microservicios |
| monitoring | Ubuntu 22.04 | Monitorización y logs |
| win-client | Windows Server 2022 | Cliente de pruebas |
| fog-server | Ubuntu 22.04 | PXE y despliegues |
| ansible-controller | Rocky Linux 9 | Automatización |

Diagramas en [`architecture/`](architecture/diagram-explained.png)

---

## Servidores del laboratorio

### core-linux
Servidor central: seguridad, servicios y almacenamiento  
[Ver documentación](core-linux/README.md)

### docker-host
Entorno de contenedores y aplicaciones  
[Ver documentación](docker-host/README.md)

### monitoring
Monitorización, métricas y logs  
[Ver documentación](monitoring/README.md)

### win-client
Cliente Windows para integración  
[Ver documentación](win-client/README.md)

### fog-server
Despliegue de sistemas por red (PXE)  
[Ver documentación](fog-server/README.md)

### ansible-controller
Automatización y configuración centralizada  
[Ver documentación](ansible-controller/README.md)

---

## Enfoque del laboratorio

Cada servidor incluye incidencias reales simuladas para practicar:

- Diagnóstico
- Análisis de logs
- Resolución de problemas
- Prevención

---

## Estado

Proyecto completo, funcional y documentado.
