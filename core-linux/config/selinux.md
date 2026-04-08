# Configuración de SELinux

Este servidor utiliza SELinux en modo *enforcing* por defecto. 

---

## 1. Estado actual

Se comprueba el modo en el que está SELinux:

<img width="992" height="223" alt="image" src="https://github.com/user-attachments/assets/0ca78663-ee3e-4de1-878b-8a8730be69c2" />

No hay alertas en este punto:

<img width="998" height="52" alt="image" src="https://github.com/user-attachments/assets/fd32e35d-dc46-4e1f-a654-4126ceb37102" />


-También se revisa el log general:

```sudo cat /var/log/audit/audit.log``` 

Actualmente no aparece ningún bloqueo, ya que estamos en la configuración inicial.


## 2. Consideraciones

- SELinux se mantiene en modo enforcing durante todo el laboratorio, no se desactiva.
- Los bloqueos reales se documentarán en el apartado de [incidencias](../incidents/selinux-block.md)


---

 
## Configuración después de instalar los servicios

Una vez desplegados servicios como Samba y Nginx, SELinux puede bloquear accesos si los contextos no están bien definidos.

Aquí se revisarán las rutas de los servicios para asegurar que SELinux está correctamente configurado.


## 3. Ajustes en Samba

Nota para más tarde: “Aquí debo configurar semanage fcontext, restorecon, etc. Sin incidencias por ahora, ya que se documentarán en /incidents”.

📸 Captura recomendada después de aplicar cambios: contexto de /srv/share con ls -Z.

## 6. Ajustes en Nginx

``` Se revisan los contextos de los directorios web y logs:

ls -Z /srv/app
ls -Z /var/log/nginx

📸 Captura recomendada: contextos de /srv/app y /var/log/nginx.

Si fuera necesario, se aplicarían comandos como:

restorecon -Rv /srv/app
semanage fcontext -a -t httpd_sys_content_t "/srv/app(/.*)?"

📸 Captura recomendada: salida de restorecon mostrando cambios aplicados. ```

