# ansible-controller (Rocky Linux 9)

Este servidor se utiliza para automatizar y gestionar la configuración de manera centralizada con Ansible.

Permite ejecutar playbooks en sistemas Linux y Windows para mantener configuraciones consistentes, desplegar cambios y automatizar tareas administrativas.

---

## Caracteristicas del servidor

- Automatización con Ansible Core
- Gestión de hosts Linux con SSH
- Gestión de hosts Windows con WinRM
- Uso de playbooks y roles reutilizables
- Inventario centralizado de los equipos
- Ejecución de tareas de configuración
- Aplicación de cambios de forma controlada

---

## Índice

### 1. Introducción
- [Descripción general](#descripción-general)

### 2. Servicios del servidor
- [Ansible Core](config/ansible.md)
- [Inventario](config/inventory.md)
- [Roles](config/roles.md)
- [Firewall (firewalld)](config/firewalld.md)

### 3. Automatización
- [Playbooks Linux](automation/linux-playbooks.md)
- [Playbooks Windows](automation/windows-playbooks.md)
- [Ejecución remota](automation/remote-execution.md)

### 4. Arquitectura del sistema
- [Diagrama](architecture/diagram.png)

### 5. Incidencias
- [Error de conexión SSH](incidents/ssh-error.md)
- [Error de conexión WinRM](incidents/winrm-error.md)
- [Error en playbook](incidents/playbook-error.md)

---

## Estructura del repositorio

- `architecture/` → Diagrama del sistema
- `config/` → Instalación de Ansible, inventario, roles y firewall
- `automation/` → Playbooks y roles utilizados
- `incidents/` → Incidencias y su resolución.
