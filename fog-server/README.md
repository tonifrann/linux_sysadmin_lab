# fog-server (Rocky Linux 9)

Servidor dedicado al despliegue masivo de sistemas operativos mediante PXE (Preboot Execution Environment).

Permite la captura, almacenamiento y despliegue automatizado de imágenes de sistemas operativos en múltiples equipos dentro de la red, centralizando la gestión de estaciones de trabajo.

Además, incorpora automatización mediante scripts SYSTEM, snapins y tareas automatizadas, permitiendo dejar los equipos completamente configurados tras la instalación (software, red, hardening básico y ajustes del entorno).

---

## Características del servidor

- Instalación y configuración de FOG Project  
- Configuración de PXE / iPXE  
- Integración con DHCP externo  
- Servicio TFTP para arranque en red  
- Servicio NFS para almacenamiento de imágenes  
- Captura y despliegue de sistemas operativos  
- Gestión de hosts e inventario de equipos  
- Automatización post-despliegue (scripts SYSTEM)  
- Configuración de firewall  
- Resolución de incidencias reales del entorno  

---

## Índice

### 1. Introducción
- [Descripción general](#descripción-general)

### 2. Servicios del servidor
- [FOG Server](config/fog-installation.md)
- [PXE / iPXE](config/pxe.md)
- [NFS Storage](config/storage.md)
- [Firewall](config/firewall.md)

### 3. Automatización post-despliegue
- [Snapins y Scripts SYSTEM](config/automation.md)

### 4. Gestión de imágenes
- [Captura y despliegue de imágenes](images/imaging.md)

### 5. Arquitectura del sistema
- [Diagrama del entorno](architecture/diagram.png)
- [Flujo de arranque PXE](architecture/pxe-flow.md)

### 6. Incidencias
- [Error en arranque PXE](incidents/pxe-error.md)
- [Error en captura de imagen](incidents/capture-failure.md)
- [Error en despliegue](incidents/deploy-failure.md)

---

## Estructura del repositorio

- `architecture/` → Diagramas del sistema y flujos PXE  
- `config/` → Instalación y configuración de FOG, PXE, NFS, TFTP y firewall  
- `images/` → Documentación de captura y despliegue de sistemas  
- `incidents/` → Incidencias reales y su resolución  
- `automation/` → Scripts SYSTEM para post-despliegue  
