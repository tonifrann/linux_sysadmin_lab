# core-linux (Rocky Linux 9)

Es el servidor principal del laboratorio. Está enfocado a la seguridad, los servicios basicos y al almacenamiento. Se utilizará para realizar pruebas de red, autenticación, backups y servicios web.


## Caracteristicas del servidor

- Automatización: Ansible Core (playbooks, roles, inventario)

- Gestión remota: SSH para administración de hosts Linux

- Control de acceso: firewalld para limitar conexiones al controlador

- Ejecución centralizada: despliegue y aplicación de configuraciones en los nodos

---

## Índice

### 1. Introducción
- [Descripción general](#descripción-general)

### 2. Instalación y configuración base
- [Instalación del sistema](config/instalation.md)
- [Configuración de red (nmcli)](config/networking.md)
- [Configuración de SSH](config/ssh.md)
- [Fail2ban (Protección SSH y servicios)](config/fail2ban.md)
- [Firewall (firewalld)](config/firewalld.md)
- [SELinux](config/selinux.md)
- [Auditoría y seguridad](config/security-audit.md)

### 3. Servicios del servidor
- [Samba con ACLs](config/samba.md)
- [Nginx con HTTPS](config/nginx.md)
- [LVM y almacenamiento](config/lvm.md)
- [Backups (rsync, tar, dd)](config/backups.md)
- [DHCP (ISC DHCP)](config/dhcp.md)

### 4. Arquitectura del laboratorio
- [Diagrama](architecture/diagram.png)

### 5. Automatización
- [Scripts del servidor](scripts/scripts.md)

### 6. Incidencias
- [Disco lleno](incidents/disk-full.md)
- [Error de firewall](incidents/firewall-misconfig.md)
- [Permisos Samba](incidents/samba-permissions.md)
- [Servicio caído](incidents/service-down.md)

---

## Estructura del repositorio
- `architecture/` → Diagramas y notas de diseño.
- `config/` → Configuraciones detalladas de cada servicio.
- `scripts/` → Scripts utilizados en el servidor.
- `incidents/` → Incidencias y su resolución.

