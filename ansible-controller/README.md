ansible-controller (Rocky Linux 9)

Servidor dedicado a la automatización de configuración y orquestación mediante Ansible.
Centraliza la ejecución de playbooks, la gestión de inventarios y la aplicación de roles comunes sobre los equipos del laboratorio (Linux y Windows).

Permite estandarizar configuraciones, desplegar software, aplicar hardening básico y mantener los sistemas actualizados de forma reproducible.

Características del servidor

Instalación y configuración de Ansible Core

Gestión de inventarios estáticos y dinámicos
Ejecución de playbooks para Linux y Windows

Roles reutilizables para tareas comunes

Integración con SSH (Linux) y WinRM (Windows)

Configuración de firewall

Resolución de incidencias reales del entorno

Índice

Introducción

Descripción general

Servicios del servidor

Instalación de Ansible

Inventario del laboratorio

Roles y estructura de automatización

Firewall y seguridad

Automatización

Playbooks del laboratorio

Ejecución remota en Linux y Windows

Arquitectura del sistema

Diagrama del entorno

Flujo de ejecución de playbooks

Incidencias

Error en ejecución de playbooks

Error de conexión SSH

Error de conexión WinRM

Estructura del repositorio

architecture/  → Diagramas del sistema y flujos de ejecución
config/        → Instalación de Ansible, inventario, roles y firewall
automation/    → Playbooks y roles utilizados en el laboratorio
incidents/     → Incidencias reales y su resolución
