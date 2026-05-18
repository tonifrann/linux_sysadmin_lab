# DHCP en core-linux (ISC DHCP)

Se configura un servidor DHCP para poder gestionar direcciones IP para arrancar PXE en FOG.


## 1. Instalación del servidor DHCP

Se instala el paquete del dhcp-server:
<img width="1023" height="346" alt="image" src="https://github.com/user-attachments/assets/5c2aae63-eaa5-4578-9f8c-9502365993d9" />


## 2. Configuración del servicio

Se modifica el archivo de configuración de SHCP:
<img width="1022" height="22" alt="image" src="https://github.com/user-attachments/assets/33f7780b-3841-4526-937f-ab81c47dc7a8" />
<img width="1025" height="327" alt="image" src="https://github.com/user-attachments/assets/888ab91e-3d7a-421c-b17b-456f0e0859e9" />

Se valida la configuración:
<img width="1022" height="193" alt="image" src="https://github.com/user-attachments/assets/0465bffe-80e8-4157-bf22-eb99ca8b654d" />


## 3.Inicialización del servicio

Se habilita el servicio y se revisa su estado:
<img width="1023" height="402" alt="image" src="https://github.com/user-attachments/assets/119ac369-9b46-44f6-b3cd-8200855f223f" />


## 4. Comprobación desde un cliente

Se comprueba que el cliente recibe un IP del rango configurado:
<img width="973" height="510" alt="image" src="https://github.com/user-attachments/assets/27b694a7-15b0-4c02-983e-73f267b67fd4" />


