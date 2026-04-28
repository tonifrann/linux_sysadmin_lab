# Configuración de Samba

Se instala y configura Samba para compartir recursos en red y permitir el acceso entre sistemas Linux y Windows.


## 1. Instalación

Para instalar Samba se ejecuta ```sudo dnf install samba samba-common samba-client -y```

<img width="1018" height="101" alt="image" src="https://github.com/user-attachments/assets/084a973b-5696-49e5-8de2-47c4d387892b" />


## 2. Configuración del servicio

Se habilitan y arrancan los servicios:

<img width="991" height="79" alt="image" src="https://github.com/user-attachments/assets/cf1356a9-f37f-4d03-a933-18a67e5642e1" />

Se comprueba el estado:

<img width="986" height="269" alt="image" src="https://github.com/user-attachments/assets/9a9e692a-7218-418e-b09f-2e47f4fca12c" />


## 3. Creación del recurso compartido

Se crea la carpeta y se le asignan los permisos necesarios. Se le da permisos de setgid para que los archivos que se creen hereden los permisos de la carpeta.

<img width="992" height="67" alt="image" src="https://github.com/user-attachments/assets/efd7c64f-d337-4cde-85d0-221d0ca90864" />


## 4. Configuración del grupo y del usuario

Se crea un grupo `smbgroup` y se añade al usuario `juan` para que tenga acceso al recurso compartido.

<img width="990" height="80" alt="image" src="https://github.com/user-attachments/assets/a6862830-2f15-4ea1-ad0e-abb53c02ce8d" />


## 5. Configuración de Samba

Se edita el archivo de configuración de samba ```nano /etc/samba/smb.conf``` y se añade al final:

<img width="988" height="127" alt="image" src="https://github.com/user-attachments/assets/170d204d-8cd3-4d0b-af6f-3286a59fbfbf" />


## 6. Crear el usuario de Samba

<img width="997" height="112" alt="image" src="https://github.com/user-attachments/assets/edc13e0e-4456-4737-bc0f-d7699dedaea0" />

## 7. Firewall

Se permite el trafico de samba con [firewalld](firewalld.md) 

<img width="988" height="86" alt="image" src="https://github.com/user-attachments/assets/23383db7-b768-430d-bba7-8be137d2d144" />

## 8. SELinux

Se revisa el contexto de [SELinux](selinux.md) del directorio compartido:

<img width="992" height="33" alt="image" src="https://github.com/user-attachments/assets/f46ec3b7-68df-4bd7-9e04-4bafaac7e6b1" />

No aparece ningun contexto, ya que está vacio. Se configura manualmente para que Samba pueda acceder correctamente:

<img width="991" height="50" alt="image" src="https://github.com/user-attachments/assets/d1062728-da49-4e83-bba6-d1ef3a55ebec" />

Se comprueba que se ha aplicado correctamente:

<img width="988" height="53" alt="image" src="https://github.com/user-attachments/assets/cab52128-f1c8-4929-af8b-8c6541b5c69a" />

## 9. Reinicio del servicio

<img width="989" height="35" alt="image" src="https://github.com/user-attachments/assets/62814699-5510-4615-813a-012b2374ef8a" />


## 10. Prueba de funcionamiento

Comprobación desde el servidor:

<img width="985" height="176" alt="image" src="https://github.com/user-attachments/assets/17b8652b-5e47-4ea1-9d8f-a1eeba0099af" />

Comprobación desde un cliente windows:

<img width="1634" height="199" alt="image" src="https://github.com/user-attachments/assets/ee6fff70-1d07-4b02-be97-83bc11a2b7f9" />


## 11. Logs

Se revisan los logs de Samba para verificar que no hay ningun problema:

<img width="979" height="128" alt="image" src="https://github.com/user-attachments/assets/7c32b093-fb3a-4412-9294-809d3ae61751" />
