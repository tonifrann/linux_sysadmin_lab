# Incidencia: Servicio SSH caído (sshd)

Tras realizar cambios en la configuración de SSH, el servicio deja de arrancar correctamente, impidiendo el acceso remoto al servidor.


## 1. Problema

No es posible conectarse al servidor por SSH después de hacer cambios en la configuración.

La conexión es rechazada desde el cliente de Windows:

<img width="836" height="55" alt="image" src="https://github.com/user-attachments/assets/29c083b1-9805-4c17-8665-8c7404026619" />


## 2. Síntomas

- No se puede establecer conexión SSH
- No hay acceso remoto al servidor


## 3. Diagnóstico

Se comprueba el estado del servicio:

<img width="997" height="162" alt="image" src="https://github.com/user-attachments/assets/4470aa2f-619f-4017-a46c-f512fee20f38" />
