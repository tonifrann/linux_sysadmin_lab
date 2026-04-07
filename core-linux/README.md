# core-linux (Rocky Linux 9)

Servidor principal del laboratorio, orientado a seguridad, servicios base y almacenamiento. Actúa como nodo central para pruebas de red, autenticación, backups y servicios web.

## 📌 Índice

### 1. Introducción
- [Descripción general](#descripción-general)

### 2. Instalación y configuración base
1. [Instalación del sistema](config/installation.md)
2. [Configuración de red (nmcli)](config/networking.md)
3. [Hardening SSH](config/ssh.md)
4. [Firewall (firewalld)](config/firewalld.md)
5. [SELinux](config/selinux.md)

### 3. Servicios del servidor
- [LVM y almacenamiento](config/lvm.md)
- [Samba con ACLs](config/samba.md)
- [Nginx con HTTPS](config/nginx.md)
- [Backups (rsync, tar, dd)](config/backups.md)
- [Hardening general](config/hardening.md)

### 4. Arquitectura del laboratorio
- [Diagramas](architecture/diagram.png)
- [Notas de diseño](architecture/design-notes.md)

### 5. Automatización
- [Scripts del servidor](scripts/)

### 6. Incidencias simuladas
- [Disco lleno](incidents/disk-full.md)
- [Bloqueo por SELinux](incidents/selinux-block.md)
- [Error de firewall](incidents/firewall-misconfig.md)
- [Permisos Samba](incidents/samba-permissions.md)
- [Servicio caído](incidents/service-down.md)

---

## 🔐 Funciones principales

### Seguridad
- SSH endurecido  
- SELinux enforcing  
- firewalld  
- Fail2ban  
- Hardening general  

### Servicios
- Samba con ACLs  
- Nginx con HTTPS y virtual hosts  

### Almacenamiento
- LVM (PV/VG/LV)  
- Snapshots  
- Ampliación de volúmenes  

### Backups
- rsync (incrementales)  
- tar (archivos y configuraciones)  
- dd (copias completas)  

### Auditoría
- auditd  
- logrotate  
- Análisis con Lynis  

### Automatización
- Tareas programadas con cron 

## Estructura del directorio
- `architecture/` → Diagramas y notas de diseño.
- `config/` → Configuraciones detalladas de cada servicio.
- `scripts/` → Scripts utilizados en el servidor.
- `incidents/` → Incidencias simuladas y su resolución.

## Estado
Este servidor está completamente documentado y sirve como referencia para el resto del laboratorio.

