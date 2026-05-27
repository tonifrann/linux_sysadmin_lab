# ansible-controller (Rocky Linux 9)

Este servidor se utiliza para automatizar y gestionar la configuración de manera centralizada con Ansible.

Permite ejecutar playbooks en sistemas Linux para mantener configuraciones consistentes, desplegar cambios y automatizar tareas administrativas.

---

## Caracteristicas del servidor

- Automatización: Ansible Core (playbooks, roles, inventario)

- Gestión remota: SSH para la administración de hosts Linux

- Ejecución centralizada: despliegue y aplicación de configuraciones en los nodos

- Firewall: control de acceso con firewalld

---

## Índice

### 1. Introducción
- [Descripción general](#descripción-general)

### 2. Servicios del servidor
- [Configuración inicial](config/initial-setup.md)
- [Ansible Core](config/ansible.md)
- [Inventario](config/inventory.md)
- [Roles](config/roles.md)
- [Firewall (firewalld)](config/firewalld.md)

### 3. Automatización
- [Playbooks Linux](automation/linux-playbooks.md)
- [Ejecución remota](automation/remote-execution.md)

### 4. Arquitectura del sistema
- [Diagrama](architecture/diagram.png)

### 5. Incidencias
- [Error de conexión SSH](incidents/ssh-error.md)
- [Error en playbook](incidents/playbook-error.md)

---

## Estructura del repositorio

- `architecture/` → Diagrama del sistema
- `config/` → Instalación de Ansible, inventario, roles y firewall
- `automation/` → Playbooks y roles utilizados
- `incidents/` → Incidencias y su resolución.
