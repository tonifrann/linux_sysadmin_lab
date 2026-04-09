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


## 4. Estructura de directorios

Se ha creado `/srv/web` como directorio de la aplicación web. Esto permite gestionar mejor los permisos, backups y contextos SELinux.

<img width="987" height="99" alt="image" src="https://github.com/user-attachments/assets/ee787166-0ec7-46b4-989c-9655b41cac7f" />

