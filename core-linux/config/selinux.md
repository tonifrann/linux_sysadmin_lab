# Configuración de SELinux

Este servidor utiliza SELinux en modo *enforcing* por defecto. 

---

## 1. Estado actual

Se comprueba el modo en el que está SELinux:

<img width="992" height="223" alt="image" src="https://github.com/user-attachments/assets/0ca78663-ee3e-4de1-878b-8a8730be69c2" />

No hay alertas en este punto:

<img width="998" height="52" alt="image" src="https://github.com/user-attachments/assets/fd32e35d-dc46-4e1f-a654-4126ceb37102" />


También se revisa el log general:

```sudo cat /var/log/audit/audit.log``` 

Actualmente no aparece ningún bloqueo, ya que estamos en la configuración inicial.


## 2. Consideraciones

- SELinux se mantiene en modo enforcing durante todo el laboratorio, no se desactiva.
- Los bloqueos reales se documentarán en el apartado de [incidencias](../incidents/selinux-block.md)


---

 
## 3. SELinux en los servicios Samba y Nginx

Una vez se han instalado los servicios, se deben configurar los contextos SELinux para permitir el acceso.

La configuración se documenta en cada servicio:

- [Configuración de Samba](samba.md)
- [Configuración de Nginx](nginx.md)
