# Rol: firewalld

Este rol configura el firewall del sistema utilizando firewalld, permitiendo los permisos necesarios para que el que el servidor quede protegido.

Se aplica únicamente a sistemas Rocky/RHEL, ya que Ubuntu utiliza ufw o iptables.

1. Funciones del rol
El rol realiza:

Habilitar y asegurar que el servicio firewalld está activo

Establecer la zona por defecto

Permitir servicios esenciales (SSH, Node Exporter, etc.)

Abrir puertos específicos según necesidades del laboratorio

Recargar la configuración del firewall
