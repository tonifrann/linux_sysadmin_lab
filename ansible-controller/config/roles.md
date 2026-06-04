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
<img width="1026" height="177" alt="image" src="https://github.com/user-attachments/assets/20a82213-743b-4f3b-9381-5e4b2bb61338" />


## 4. Estructura de los roles

Se revisa la escructura que Ansible ha generado:
<img width="1021" height="606" alt="image" src="https://github.com/user-attachments/assets/3ac4b06b-9a47-4c25-b340-33693f0c4c87" />



## 5. Función de los roles

### node-exporter
  
Este rol instala y configura el agente de Node Exporter, para expone las métricas del sistema para Prometheus.

- Descarga el binario oficial desde GitHub

- Crea el usuario de servicio node_exporter

- Copia el binario a /usr/local/bin/

- Crea el servicio systemd

- Activa y  habilita el servicio

- Permite el puerto 9100/tcp (si se usa firewalld) 


### firewalld

Este rol gestiona las reglas de firewall en los servidores:

- Activa  y habilita firewalld 

- Abre los puertos definidos en cada host

- Aplica las reglas permanentemente

- Recarga las reglas después de cambios en la configuración
