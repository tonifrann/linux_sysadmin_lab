# Configuración de SSH (sshd_config)

Este documento describe la configuración básica y segura del servicio SSH en Rocky Linux 9.

---

## 1. Crear un usuario administrador

SSH no debe usarse con root. Primero creo un usuario normal y lo añado al grupo `admins` para permitir sudo.

<img width="996" height="178" alt="image" src="https://github.com/user-attachments/assets/dcddf278-62af-4bc4-96e4-cad2ad87f353" />

## 2. Dar permisos de sudo al grupo

- Entramos en ```visudo```
- Agregamos al guiguiente linea:
  ```%admins ALL=(ALL) ALL```

## 3. Configurar claves SSH

- Para crear la clave desde un PC Windows ejecuto:
  ```ssh-keygen -t ed25519```
  
- Para copiar la clave al Servidor:
  
<img width="1072" height="72" alt="image" src="https://github.com/user-attachments/assets/f609d47d-d148-488c-9bcf-1f65b81d68a6" />

- En el servidor (core-linux):

<img width="994" height="96" alt="image" src="https://github.com/user-attachments/assets/636e9339-77d1-4fc1-9be6-8f938a287648" />

Nota: Si lo en vez de windows, l ohubiera hehco en un cliente Linux, hubiera utilizado ```ssh-copy-id``` para copiar la clave al servidor, y no hubiera tenido que crear las carpetas manualmente.


## 4. Configuración del servicio SSH

Ejecutamos ```sudo nano /etc/ssh/sshd_config```

PermitRootLogin no
PasswordAuthentication no
PubkeyAuthentication yes
AllowUsers toni
AllowGroups admins
X11Forwarding no
MaxAuthTries 3
ClientAliveInterval 300

Con esta configuración lograremos lo siguiente:
- Evitar que se acceda como root desde SSH.
- Que no se pueda acceder con contraseña, unicamente con claves SSH.
- Solo el usuario toni tiene acceso.
- El maximo numero de intentos fallidos es 3, asi reducimos la posibilidad de fuerza bruta.

## 5. Reiniciar SSH
sudo systemctl restart sshd
sudo systemctl status sshd

## 6. Desde mi maquina
ssh toni@192.168.100.10

## 7. Estado final
SSH queda configurado de forma segura:

- Acceso solo con claves
- Root deshabilitado
- Usuario administrador con sudo
- Intentos limitados
