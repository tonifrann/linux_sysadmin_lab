# Roles de Ansible

Los roles son configuraciones reutilizables que se pueden aplicar en los servidores del que se vayan introduciondo en el inventario.

Se crean dos roles básicos para validar el funcionamiento del controlador.


## 2. Roles implementados

- node-exporter: 
- firewalld: Aplica reglas de firewall dependiendo del servidor

<img width="1023" height="83" alt="image" src="https://github.com/user-attachments/assets/729a3d50-f78d-4f38-87a5-51abb4d2261c" />


## 3. Estructura de los roles

Se revisa la escructura que Ansible ha generado:
<img width="1021" height="606" alt="image" src="https://github.com/user-attachments/assets/3ac4b06b-9a47-4c25-b340-33693f0c4c87" />



## 4. Función de los roles

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
