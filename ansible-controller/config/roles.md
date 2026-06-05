# Roles de Ansible

Los roles permiten organizar la configuración en componentes reutilizables.

Cada rol implementa una función concreta del sistema y puede aplicarse a cualquier servidor definido en el inventario.


## 2. Roles implementados

Los roles que se utilizan en este entorno son:

- usuarios — Gestiona el usuario admin (SSH, sudoers, permisos).

- paquetes-base — Instala herramientas básicas del sistema.

- update — Instala actualizaciones del sistema.

- firewalld — Gestiona reglas de firewall por servidor.

- node-exporter — Instala y configura el agente de métricas para Prometheus.

Estos roles se aplicarán a todos los servidores definidos en el inventario.


## 3. Creación de roles

Los roles se crean con el comando de Ansible Galaxy:
<img width="1023" height="177" alt="image" src="https://github.com/user-attachments/assets/823083d1-7a33-4937-a331-212a258ec6f0" />


## 4. Estructura de los roles

En cada rol que se ha creado tiene esta misma estructura:
<img width="1008" height="575" alt="image" src="https://github.com/user-attachments/assets/648bb5bb-49e6-4428-811b-e8f95ed50987" />


## 5. Función de los roles

### usuarios

El rol asegura que el usuario admin queda correctamente configurado en todos los servidores:

- Verifica que el usuario admin existe

- Establece /bin/bash como shell

- Añade sudo sin contraseña mediante /etc/sudoers.d/admin


### paquetes-base

Instala herramientas basicas que tienen que estar en todos los servidores.

- Instala utilidades del sistema (htop, vim/nano, curl, wget…)

- Instala herramientas de red (net-tools, traceroute…)

- Instala herramientas de compresión (tar, unzip…)

- Garantiza un entorno homogéneo en todos los hosts


### update

Aplica actualizaciones del sistema de forma centralizada.

- Actualiza los repositorios

- Instala actualizaciones disponibles

- Limpia paquetes obsoletos

- Reinicia el servidor si es necesario (kernel nuevo)


### firewalld

Gestiona las reglas de firewall en los servidores:

- Activa  y habilita firewalld 

- Abre los puertos definidos en cada host

- Aplica las reglas permanentemente

- Recarga las reglas después de cambios en la configuración


### node-exporter
  
Instala y configura el agente de Node Exporter, para expone las métricas del sistema para Prometheus.

- Descarga el binario oficial desde GitHub

- Crea el usuario de servicio node_exporter

- Copia el binario a /usr/local/bin/

- Crea el servicio systemd

- Activa y  habilita el servicio

- Permite el puerto 9100/tcp (si se usa firewalld) 



