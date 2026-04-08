# Configuración de SELinux

Este servidor utiliza SELinux en modo *enforcing* por defecto. 

---

## 1. Estado actual

Se comprueba el modo en el que está SELinux:

<img width="992" height="223" alt="image" src="https://github.com/user-attachments/assets/0ca78663-ee3e-4de1-878b-8a8730be69c2" />


## 2. Alertas de SELinux

- Se revisan posibles bloqueos:

<img width="998" height="52" alt="image" src="https://github.com/user-attachments/assets/fd32e35d-dc46-4e1f-a654-4126ceb37102" />


-También se revisa el log general:

```sudo cat /var/log/audit/audit.log``` 

Actualmente no aparece ningún bloqueo, ya que estamos en la configuración inicial.


## 3. Contexto de archivos

<img width="998" height="224" alt="image" src="https://github.com/user-attachments/assets/2b78e40a-47d9-43f9-baaa-bd9a7ca4fbba" />


## 4. Consideraciones

SELinux se mantiene en modo enforcing durante todo el laboratorio
No se desactiva, los problemas se solucionan ajustando contextos o políticas
Se documentarán los bloqueos reales en el apartado de incidencias


## 5. Notas

Al inicio SELinux no ha generado conflictos, pero al desplegar servicios (Samba, Nginx) empezaron a aparecer bloqueos que obligaron a revisar logs y ajustar configuraciones. [Bloqueos de SELinux](../incidents/selinux-block.md)

