# Configuración de Samba

Se instala y configura Samba para compartir recursos en red y permitir el acceso entre sistemas Linux y Windows.


## 1. Instalación

Para instalar Samba ejecutamos ```sudo dnf install samba samba-common samba-client -y```

<img width="1018" height="101" alt="image" src="https://github.com/user-attachments/assets/084a973b-5696-49e5-8de2-47c4d387892b" />


## 2. Servicio y firewall

Se habilitan y arrancan los servicios:

<img width="989" height="47" alt="image" src="https://github.com/user-attachments/assets/2e8adf19-201f-4c4e-ac66-871fce4eb935" />

Se comprueba el estado:

<img width="986" height="269" alt="image" src="https://github.com/user-attachments/assets/9a9e692a-7218-418e-b09f-2e47f4fca12c" />


## 3. Creación del recurso compartido

Se crea la carpeta y se le dan los permisos necesarios. Se le ha permisos de setgid para que los archivos que se creen hereden los permisos del directorio.

<img width="992" height="67" alt="image" src="https://github.com/user-attachments/assets/efd7c64f-d337-4cde-85d0-221d0ca90864" />


## 4. 4. Configuración del grupo y del usuario

Se crea un grupo `smbgroup` y se añade al usuario `juan` para que tenga acceso al recurso compartido.

<img width="990" height="80" alt="image" src="https://github.com/user-attachments/assets/a6862830-2f15-4ea1-ad0e-abb53c02ce8d" />


## 5. Configuración de Samba

Se edita el archivo de configuración de samba ```nano /etc/samba/smb.conf``` y se añade al final:

<img width="988" height="127" alt="image" src="https://github.com/user-attachments/assets/170d204d-8cd3-4d0b-af6f-3286a59fbfbf" />


## 6. Crear el usuario de Samba

<img width="997" height="112" alt="image" src="https://github.com/user-attachments/assets/edc13e0e-4456-4737-bc0f-d7699dedaea0" />

## 8. Firewall

Se permite el trafico de samba con [firewalld](firewalld.md) 

<img width="988" height="86" alt="image" src="https://github.com/user-attachments/assets/23383db7-b768-430d-bba7-8be137d2d144" />






