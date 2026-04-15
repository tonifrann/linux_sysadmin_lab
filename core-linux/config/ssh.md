# Configuración de SSH (sshd_config)

Este documento describe la configuración básica y segura del servicio SSH en Rocky Linux 9.

---

## 1. Crear un usuario administrador

SSH no debe usarse con root. Primero creo un usuario normal y lo añado al grupo `admins` para permitir sudo.

<img width="996" height="178" alt="image" src="https://github.com/user-attachments/assets/dcddf278-62af-4bc4-96e4-cad2ad87f353" />

## 2. Dar permisos de sudo al grupo

- Entramos en ```visudo``` y se agregan las sigueintes lineas:

<img width="984" height="51" alt="image" src="https://github.com/user-attachments/assets/90c94f53-4cbd-443b-81b0-36322d454f5d" />


## 3. Configurar claves SSH

- Para crear la clave desde un PC Windows ejecuto:
  ```ssh-keygen -t ed25519```
  
- Para copiar la clave al Servidor:
  
<img width="1072" height="72" alt="image" src="https://github.com/user-attachments/assets/f609d47d-d148-488c-9bcf-1f65b81d68a6" />

- En el servidor (core-linux):

<img width="994" height="96" alt="image" src="https://github.com/user-attachments/assets/636e9339-77d1-4fc1-9be6-8f938a287648" />

> Nota: Si lo en vez de windows, se hubiera utilizado un cliente Linux, hubiera utilizado ```ssh-copy-id``` para copiar la clave al servidor, y no se hubiera tenido que crear las carpetas manualmente.


## 4. Configuración del servicio SSH

Ejecutamos ```sudo nano /etc/ssh/sshd_config``` y añadimos las siguientes lineas:

<img width="1009" height="502" alt="image" src="https://github.com/user-attachments/assets/024b4397-56f0-4346-9053-e4048a32b3db" />

Con esta configuración lograremos lo siguiente:
- Evitar que se acceda como root desde SSH.
- Que no se pueda acceder con contraseña, unicamente con claves SSH.
- Solo el usuario toni tiene acceso.
- El maximo numero de intentos fallidos es 3, asi reducimos la posibilidad de fuerza bruta.

## 5. Reiniciar SSH y verificar su status
<img width="999" height="304" alt="image" src="https://github.com/user-attachments/assets/c0681d62-ebbd-4fe1-9b08-ed6c009b9cee" />


## 6. Probar acceso
Verifico el acceso a la maquina Windows 11 con la clave y sin que pida contraseña.

<img width="1091" height="113" alt="image" src="https://github.com/user-attachments/assets/e18b7187-cabf-475c-8c14-fc7187ffae6d" />

Verifico que root no puede acceder.

<img width="1098" height="110" alt="image" src="https://github.com/user-attachments/assets/9ad9fac2-054d-4a38-a985-3a572ce21974" />
