# ansible-controller (Rocky Linux 9)

Este servidor se utiliza para automatizar y gestionar la configuración de manera centralizada con Ansible.

Permite ejecutar playbooks en sistemas Linux y Windows para mantener configuraciones consistentes, desplegar cambios y automatizar tareas administrativas.

---

## Caracteristicas del servidor

- Automatización centralizada con Ansible Core
- Gestión remota de sistemas Linux con SSH
- Gestión remota de sistemas Windows con WinRM
- Uso de playbooks y roles reutilizables
- Inventario centralizado de hosts
- Automatización de configuraciones comunes
- Ejecución de tareas idempotentes
- Resolución de incidencias

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
- [Error WinRM](incidents/winrm-error.md)
- [Error en playbook](incidents/playbook-error.md)

---

## Estructura del repositorio

- `architecture/` → Diagramas y notas de diseño.
- `config/` → Configuración de Ansible e inventarios.
- `automation/` → Playbooks y automatización.
- `incidents/` → Incidencias y troubleshooting.

---

## Flujo de automatización

- El servidor Ansible se conecta a los hosts Linux mediante SSH.
- Los sistemas Windows se gestionan mediante WinRM.
- Los playbooks aplican configuraciones y automatizaciones de forma centralizada.
- Los roles permiten reutilizar configuraciones comunes entre distintos sistemas.
