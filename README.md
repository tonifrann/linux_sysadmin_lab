# Linux Sysadmin Lab
Linux SysAdmin Lab
Este repositorio contiene un laboratorio completo orientado a administración de sistemas Linux. Incluye servicios habituales en entornos de infraestructura, seguridad, contenedores, monitorización, automatización y resolución de incidencias.
El objetivo es practicar y documentar tareas reales de un administrador de sistemas.

Arquitectura general
El laboratorio está formado por varios servidores, cada uno con un rol específico:

Servidor	Distro	Rol
core-linux	Rocky Linux 9	Servicios base, seguridad, Samba, LVM, Nginx, backups
docker-host	Ubuntu 22.04	Docker, Docker Compose, microservicios, firewall
monitoring	Ubuntu 22.04	Prometheus, Grafana, centralización de logs
win-client	Windows Server 2022	Pruebas de Samba y PXE
fog-server	Ubuntu 22.04	FOG, PXE, TFTP, DHCP
ansible-controller (opcional)	Ubuntu o Rocky	Automatización con Ansible
Los diagramas de red y servicios están en la carpeta architecture/.

core-linux (Rocky Linux 9)
Servidor principal orientado a seguridad, servicios y almacenamiento.

Incluye:

Gestión de usuarios y sudoers

SSH endurecido

firewalld

SELinux en modo enforcing

Fail2ban

Samba con ACLs

Nginx con HTTPS (Let’s Encrypt)

Virtual hosts

LVM (PV, VG, LV, snapshots, ampliación de volúmenes)

Configuración de logrotate

Backups con rsync, tar y dd

Cron jobs

Hardening general

Auditoría con auditd

Análisis con Lynis

Incidencias documentadas:

Disco lleno

Bloqueos por SELinux

Reglas de firewall incorrectas

Servicio caído

Problemas de permisos en Samba

docker-host (Ubuntu 22.04)
Servidor dedicado a contenedores y servicios desplegados con Docker.

Incluye:

Docker Engine

Docker Compose

Contenedor Nginx

Contenedor de aplicación

Redes internas

Volúmenes persistentes

Healthchecks

iptables o nftables

Incidencias documentadas:

Contenedor detenido

Volumen corrupto

Puerto bloqueado

Imagen dañada

monitoring (Ubuntu 22.04)
Servidor de monitorización y observabilidad.

Incluye:

Prometheus

Node Exporter en todos los servidores

Grafana

Dashboards personalizados

Alertas básicas

Centralización de logs (rsyslog o Loki + Promtail)

Incidencias documentadas:

Exporter no disponible

Scrape fallido

Dashboard con errores

Logs no recibidos

win-client (Windows Server 2022)
Servidor Windows para pruebas de integración.

Incluye:

Pruebas de Samba

Acceso a servicios web

Cliente PXE para FOG

Scripts PowerShell básicos

fog-server (Ubuntu 22.04)
Servidor para despliegues masivos mediante FOG.

Incluye:

Instalación de FOG

TFTP

PXE boot

DHCP

Captura y despliegue de imágenes

Scripts post-instalación

Incidencias documentadas:

PXE no arranca

TFTP bloqueado

Problemas con DHCP

Imagen corrupta

ansible-controller (opcional)
Servidor para automatizar tareas en el laboratorio.

Incluye:

Inventario

Playbooks

Roles básicos (nginx, firewalld, docker, node_exporter, usuarios)
