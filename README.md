# Linux Sysadmin Lab

Laboratorio práctico de administración de sistemas Linux que simula una infraestructura real de empresa.

Incluye despliegue de servicios, seguridad, automatización, monitorización y resolución de incidencias reales.

---

## Tecnologías y áreas trabajadas

- Administración Linux (Rocky / Ubuntu)
- Seguridad: SELinux, hardening, firewalls (firewalld, ufw, iptables)
- Redes y servicios
- Contenedores (Docker)
- Monitorización (Prometheus, Grafana)
- Backups y recuperación
- Automatización (Ansible, scripts)
- Troubleshooting
- Integración Windows/Linux

---

## Arquitectura del laboratorio

| Servidor | IP | Distro | Rol |
|----------|----|--------|-----|
| core-linux | 192.168.100.10 | Rocky Linux 9 | Servicios base, seguridad, almacenamiento |
| monitoring | 192.168.100.11 | Ubuntu 22.04 | Monitorización y logs |
| docker-host | 192.168.100.12 | Ubuntu 22.04 | Contenedores y microservicios |
| fog-server | 192.168.100.13 | Ubuntu 22.04 | PXE y despliegues |
| ansible-controller | 192.168.100.14 | Rocky Linux 9 | Automatización |
| win-client | 192.168.100.50 | Windows 11 | Cliente de pruebas |

Diagrama en [`architecture/`](architecture/diagram-explained.png)

---

## Servidores del laboratorio

### core-linux
Servidor principal: seguridad, servicios y almacenamiento  
[Ver documentación](core-linux/README.md)

### monitoring
Monitorización, métricas y logs  
[Ver documentación](monitoring/README.md)

### docker-host
Entorno de contenedores y aplicaciones  
[Ver documentación](docker-host/README.md)

### fog-server
Despliegue de sistemas por red (PXE)  
[Ver documentación](fog-server/README.md)

### ansible-controller
Automatización y configuración centralizada  
[Ver documentación](ansible-controller/README.md)

### win-client
Cliente Windows utilizado únicamente para pruebas de acceso (Samba, SSH, Nginx). 

---

## Enfoque del laboratorio

Cada servidor incluye incidencias:

- Diagnóstico y Resolución de problemas
- Análisis de logs
- Medidas preventivas
