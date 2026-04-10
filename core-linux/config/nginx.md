# Configuración de Nginx

Se instala y configura Nginx para servir contenido web básico y preparar el entorno para futuras aplicaciones.

---

## 1. Instalación

```sudo dnf install nginx -y```

<img width="1072" height="583" alt="image" src="https://github.com/user-attachments/assets/acabd858-2c69-4f6c-afca-3def7082a6cf" />


## 2. Estado del servicio

Se habilita y arranca Nginx:

<img width="1001" height="383" alt="image" src="https://github.com/user-attachments/assets/e3aca520-8bbd-4227-bc14-83e2714b0725" />


## 3. Firewall

Se configura [firewalld](firewalld.md) para que se permita el trafico de HTTP/HTTPS

<img width="995" height="115" alt="image" src="https://github.com/user-attachments/assets/a44d0d48-63fa-4776-a5f5-77d5928bca48" />


## 4. Estructura de directorios

Se ha creado `/srv/web` como directorio de la aplicación web. Configuro el contexto para asegurarnos de que SElinux funcione correctamente y lo hago recursivo.

<img width="987" height="99" alt="image" src="https://github.com/user-attachments/assets/ee787166-0ec7-46b4-989c-9655b41cac7f" />


## 5. Configuración básica

En lugar de modificar el archivo principal nginx.conf, se crea un archivo de configuración para la web:

```sudo nano /etc/nginx/conf.d/web.conf```

<img width="986" height="117" alt="image" src="https://github.com/user-attachments/assets/8cb91a68-565e-4dfd-b8a5-850137b3800f" />


## 6. Prueba de funcionamiento

Se crea un archivo html simple y se recarga nginx.

<img width="993" height="68" alt="image" src="https://github.com/user-attachments/assets/971bd644-c193-4470-bbfa-b5b0292ee54c" />

Se comprueba en un navegador que funciona correctamente:

<img width="1335" height="128" alt="image" src="https://github.com/user-attachments/assets/5809d865-2c66-4892-95bd-a70ec505aeff" />


> NOTA:  En la primera prueba desde el navegador, Nginx no mostraba el contenido debido a un error de escritura en la ruta (`/svr/web` en lugar de `/srv/web`). Una vez corregido, el servicio funcionó correctamente.


## 7. SELinux

Se comprueba el contexto SELinux del directorio web:

<img width="990" height="46" alt="image" src="https://github.com/user-attachments/assets/2ffc785e-0d1c-4aa0-8aaf-ad4cbdfec0b1" />

El contexto es correcto (httpd_sys_content_t), por lo que Nginx puede acceder al contenido sin problemas.

No se ha detectado ningun bloqueo en SElinux relacionados con nginx:

<img width="990" height="45" alt="image" src="https://github.com/user-attachments/assets/527cceda-6311-4b7a-9a00-633ed8e83009" />


## 8. Logs

Se revisan los logs de acceso y error para verificar el funcionamiento del servicio:

- sudo tail -10 /var/log/nginx/access.log
- sudo tail -10 /var/log/nginx/error.log

No aparecen errores y las peticiones de http aparecen correctamente en el archivo access.log


## 9. Estado final

- Nginx instalado y funcionando correctamente
- Firewall configurado
- SELinux con el contexto correcto
- Logs sin errores
