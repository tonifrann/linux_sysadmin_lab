# Roles de Ansible

Los roles son configuraciones reutilizables que se pueden aplicar en los servidores del que se vayan introduciondo en el inventario.

Se crean dos roles básicos para validar el funcionamiento del controlador.


## 2. Roles implementados

- usuarios: Crea un usuario administrador y copia la clave SSH
- firewalld: Aplica reglas de firewall dependiendo del servidor

<img width="1022" height="81" alt="image" src="https://github.com/user-attachments/assets/be042246-fb8f-4a28-857b-a5e28f23fb84" />


## 3. Estructura de los roles

Se revisa la escructura que Ansible ha generado:
<img width="1022" height="609" alt="image" src="https://github.com/user-attachments/assets/8ca97b71-fc21-43d2-a521-20fe79091d96" />


## 4. Función de los roles

### usuarios
  
Este rol prepara el acceso de administrador a los servidores que se vayan añadiendo en el inventario

- Creación del usuario admin

- Lo añade al grupo wheel

- Copia la clave pública SSH para poder acceder sin contraseña


### firewalld

Este rol gestiona las reglas de firewall según el servidor:

- Se activa  y habilita firewalld 

- Abre los puertos definidos en cada host

- Recarga las reglas después de cambios en la configuración
