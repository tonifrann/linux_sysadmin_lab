# Configuración de SELinux

Este servidor utiliza SELinux en modo *enforcing* por defecto. 

---

## 1. Estado actual

Se comprueba el modo en el que está SELinux:

<img width="999" height="194" alt="image" src="https://github.com/user-attachments/assets/fee9c65d-ae7e-4a37-b3f5-587f077bfdba" />


## 2. Alertas de SELinux

- Se revisan posibles bloqueos:

<img width="1003" height="35" alt="image" src="https://github.com/user-attachments/assets/b6d3be4b-63d7-4cf4-90c3-6f3e2785d376" />


-También se revisa el log general ```sudo cat /var/log/audit/audit.log``` auqnue no se encuentra ningun error relacionado con SElinux.

- Actualmente no aparece ningun bloqueo, ya que estamos en la configuración inicial. Cuando se configuren servicios como Samba o Nginx, si SELinux bloquea algo se documentará en [Bloqueos de SELinux](linux_sysadmin-lab/core-linux/incidents/selinux-block.md)



## 


