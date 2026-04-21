# Linux Sysadmin Lab

Laboratorio práctico de administración de sistemas Linux que simula una infraestructura real de empresa.

Incluye despliegue de servicios, seguridad, automatización, monitorización y resolución de incidencias reales.

---

## Tecnologías y áreas trabajadas

- Administración Linux (Rocky / Ubuntu)
- Seguridad: SELinux, firewalls, hardening
- Redes y servicios
- Contenedores (Docker)
- Monitorización (Prometheus, Grafana)
- Backups y recuperación
- Automatización (Ansible, scripts)
- Troubleshooting
- Integración Windows/Linux

---

## Arquitectura del laboratorio

| Servidor | Distro | Rol |
|----------|--------|-----|
| core-linux | Rocky Linux 9 | Servicios base, seguridad, almacenamiento |
| docker-host | Ubuntu 22.04 | Contenedores y microservicios |
| monitoring | Ubuntu 22.04 | Monitorización y logs |
| win-client | Windows 11 | Cliente de pruebas |
| fog-server | Ubuntu 22.04 | PXE y despliegues |
| ansible-controller | Rocky Linux 9 | Automatización |

Diagrama en [`architecture/`](architecture/diagram-explained.png)

---

## Red del laboratorio

| **Servidor** | **IP** |
| :--- | :--- |
| core-linux | 192.168.100.10 |
| monitoring | 192.168.100.11 |
| docker-host | 192.168.100.12 |
| fog-server | 192.168.100.13 |
| ansible-controller | 192.168.100.14 |

## Servidores del laboratorio

### core-linux
Servidor principal: seguridad, servicios y almacenamiento  
[Ver documentación](core-linux/README.md)

### docker-host
Entorno de contenedores y aplicaciones  
[Ver documentación](docker-host/README.md)

### monitoring
Monitorización, métricas y logs  
[Ver documentación](monitoring/README.md)

### win-client
Cliente Windows utilizado únicamente para pruebas de acceso (Samba, SSH, Nginx).  

### fog-server
Despliegue de sistemas por red (PXE)  
[Ver documentación](fog-server/README.md)

### ansible-controller
Automatización y configuración centralizada  
[Ver documentación](ansible-controller/README.md)

---

## Enfoque del laboratorio

Cada servidor incluye incidencias reales simuladas para practicar:

- Diagnóstico y Resolución de problemas
- Análisis de logs
- Medidas preventivas
