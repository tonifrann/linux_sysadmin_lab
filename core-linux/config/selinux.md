# Configuración de SELinux

Este servidor tiene configurado SELinux en modo *enforcing* por defecto. 

---

## 1. Estado actual

Se comprueba el modo en el que está SELinux:

<img width="992" height="223" alt="image" src="https://github.com/user-attachments/assets/0ca78663-ee3e-4de1-878b-8a8730be69c2" />

No hay alertas en este punto:

<img width="998" height="52" alt="image" src="https://github.com/user-attachments/assets/fd32e35d-dc46-4e1f-a654-4126ceb37102" />


También se revisa el log general:

```sudo cat /var/log/audit/audit.log``` 

Actualmente no aparece ningún bloqueo, ya que se esta empezando a configurar todo.


## 2. Consideraciones

-  SELinux siempre está activado en modo enforcing y no se desactivará en ningun momento durante el laboratorio.
- Cualquier bloqueo que haya se documentarán en el apartado de [incidencias](../incidents/selinux-block.md)


## 3. SELinux en los servicios Samba y Nginx

Después de instalar los servicios, hay que configurar SELinux para que permita el acceso a estos servicios.

La configuración se explica en cada uno de los servicios:

- [Configuración de Samba](samba.md)
- [Configuración de Nginx](nginx.md)
