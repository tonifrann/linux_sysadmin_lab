# core-linux (Rocky Linux 9)

Servidor principal del laboratorio, orientado a seguridad, servicios base y almacenamiento. Actúa como nodo central para pruebas de red, autenticación, backups y servicios web.

## Funciones principales
- Seguridad: SSH endurecido, SELinux enforcing, firewalld, Fail2ban, hardening general.
- Servicios: Samba con ACLs, Nginx con HTTPS y virtual hosts.
- Almacenamiento: LVM (PV/VG/LV), snapshots, ampliación de volúmenes.
- Backups: rsync (incrementales), tar (archivos y configuraciones), dd (copias completas).
- Auditoría: auditd, logrotate, análisis con Lynis.
- Automatización: tareas programadas con cron.

## Estructura del directorio
- `architecture/` → Diagramas y notas de diseño.
- `config/` → Configuraciones detalladas de cada servicio.
- `scripts/` → Scripts utilizados en el servidor.
- `incidents/` → Incidencias simuladas y su resolución.

## Estado
Este servidor está completamente documentado y sirve como referencia para el resto del laboratorio.

