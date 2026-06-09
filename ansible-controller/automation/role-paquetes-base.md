# Rol: paquetes-base
Este rol instala un conjunto de paquetes esenciales que deben estar presentes en todos los servidores del laboratorio.
Garantiza que cada máquina tenga las herramientas mínimas necesarias para administración, diagnóstico y funcionamiento general.

## 1. Funciones del rol

El rol instala automáticamente:

- Paquetes de administración del sistema

- Herramientas de red

- Utilidades de diagnóstico

- Paquetes necesarios para otros roles o servicios

Este conjunto de paquetes es común para todos los servidores Linux del laboratorio.


## 2. Lista de paquetes instalados

Los paquetes instalados dependen de la familia del sistema operativo:

- Ubuntu / Debian: curl, wget, vim, htop, net-tools, tree, git, unzip, tar, software-properties-common

- Rocky / RHEL: curl, wget, vim-enhanced, htop, net-tools, tree, git, unzip, tar, dnf-plugins-core


## 3. Tareas del rol

El rol instala los paquetes con apt o dnf según la distribución de linux:

<img width="1022" height="18" alt="image" src="https://github.com/user-attachments/assets/244798e9-f212-4689-ae26-b489661a8ee9" />

<img width="1022" height="563" alt="image" src="https://github.com/user-attachments/assets/0e0b8b0e-082f-4797-9b4a-fb222aa2824c" />


## 4. Ejecución del rol

Una vez ejecutamos el playbook:

<img width="1022" height="19" alt="image" src="https://github.com/user-attachments/assets/b4af882d-3260-4ef0-ae2e-f38daa1f280a" />

- Todos los servidores tienen las herramientas básicas de administración

- Los comandos esenciales están disponibles (curl, vim, htop, etc.)

- La base de todos los seridores queda homogénea

- Otros roles pueden ejecutarse sin dependencias faltantes
