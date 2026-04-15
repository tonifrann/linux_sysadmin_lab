# Configuración de red (nmcli)

La configuración se realiza manualmente con `nmcli`.

## 1. Comprobar el estado inicial de la interfaz
<img width="995" height="178" alt="image" src="https://github.com/user-attachments/assets/9db5d60d-48c0-4fe6-80a1-32fb0231bf76" />

## 2. Configuración de IP estatica
Asigno la IP 192.168.100.10/24, gateway y el DNS

<img width="998" height="116" alt="image" src="https://github.com/user-attachments/assets/9e6c233a-180f-4afb-a2b8-cd64973c5c81" />

## 3. Verificación de la configuración

### Verificar la IP
<img width="998" height="226" alt="image" src="https://github.com/user-attachments/assets/ee60e5e2-e9e7-4ae4-abad-a9950b452ed5" />

### Verificar el gateway
<img width="997" height="75" alt="image" src="https://github.com/user-attachments/assets/b26baee9-ff57-4dbf-8e90-8ce28786c03c" />

### Verificar el DNS y la conectividad
<img width="997" height="304" alt="image" src="https://github.com/user-attachments/assets/8fd9a9d0-e4f8-4636-868a-212f6be48608" />

## 4. Configuración persistente
Todo ha quedado guardado en el archivo /etc/NetworkManager/system-connections/eth0.nmconnection


> Nota: El servidor ya tiene acceso a Internet y ya se puede actualizar el sistema con:

> ```dnf update -y```
