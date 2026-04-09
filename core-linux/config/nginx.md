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

Se ha creado `/srv/web` como directorio de la aplicación web. Configuro el contexto para segurarnos de que SElinux funcione correctamente y lo hago recursivo.

<img width="987" height="99" alt="image" src="https://github.com/user-attachments/assets/ee787166-0ec7-46b4-989c-9655b41cac7f" />


## 5. Configuración básica

Se edita el archivo de configuración de nginx para que encuentr la ruta que hemos creado con ```nano /etc/nginx/nginx.conf```

<img width="990" height="97" alt="image" src="https://github.com/user-attachments/assets/4e87cc5e-12e4-40ff-b5df-8f1338f7169e" />


## 6. Prueba de funcionamiento

Se crea un archivo html simple y se recarga nginx.

<img width="993" height="68" alt="image" src="https://github.com/user-attachments/assets/971bd644-c193-4470-bbfa-b5b0292ee54c" />






