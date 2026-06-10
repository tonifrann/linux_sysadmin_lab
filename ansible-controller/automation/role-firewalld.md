# Rol: firewalld

Este rol configura el firewall del sistema utilizando firewalld, permitiendo los permisos necesarios para que el que el servidor quede protegido.

Se aplica únicamente a sistemas Rocky/RHEL, ya que Ubuntu utiliza ufw o iptables.


## 1. Funciones del rol

El rol realiza automáticamente:

- Instalación de firewalld (Ubuntu y Rocky)

- Activación y habilitación del servicio

- Configuración de la zona por defecto

- Permitir servicios (SSH)

- Apertura de puertos (Node Exporter, etc.)

- Abre los puertos específicos

- Recargar la configuración del firewall


## 2. Tareas del rol

El rol se encarga de que la configuración del firewall sea homogénea y segura en todos los servidores que utilizan firewalld.

<img width="1023" height="18" alt="image" src="https://github.com/user-attachments/assets/40970144-139c-4350-9266-73187d0bf2bc" />

<img width="1023" height="728" alt="image" src="https://github.com/user-attachments/assets/56f4fb9f-54d2-45d3-9e4d-fbbccbf0361f" />


## 3. Ejecución del rol

Una vez ejecutamos el playbook:

<img width="1024" height="19" alt="image" src="https://github.com/user-attachments/assets/02627e1f-6809-47be-b550-02324cdd196a" />

- firewalld está instalado

- El servicio está activo y habilitado

- La zona por defecto es public

- SSH está permitido

- El puerto 9100/tcp está abierto

- La configuración es permanente

- El firewall se recarga correctamente
