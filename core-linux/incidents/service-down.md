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

Se revisan los logs en busca del fallo:

<img width="996" height="109" alt="image" src="https://github.com/user-attachments/assets/bbba8b3f-8d97-4cbc-8b9f-082a5f37cce6" />

<img width="997" height="16" alt="image" src="https://github.com/user-attachments/assets/57d50385-6ac4-4f45-be6a-06fff4b44a3b" />

<img width="990" height="386" alt="image" src="https://github.com/user-attachments/assets/a5833af5-0b48-4c0b-9dc1-362296e9e56e" />

Se revisa la configuración:

<img width="999" height="47" alt="image" src="https://github.com/user-attachments/assets/ec4c73ce-f5ab-48e2-8633-b36adce8583f" />


## 5. Solución

Se corrige el error en el archivo de configuración (puerto incorrecto):

<img width="991" height="17" alt="image" src="https://github.com/user-attachments/assets/2b3797aa-1b8e-4f50-86a5-84638ceede1b" />

<img width="996" height="146" alt="image" src="https://github.com/user-attachments/assets/1af555e1-222b-4796-8c9d-4a804db25ca0" />

