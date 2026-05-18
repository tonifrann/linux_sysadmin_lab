# DHCP en core-linux (ISC DHCP)

Se configura un servidor DHCP para poder gestionar direcciones IP para el arranque PXE de los clientes que utilizarán FOG.


## 1. Instalación del servidor DHCP

Se instala el paquete del servidor DHCP:
<img width="1023" height="346" alt="image" src="https://github.com/user-attachments/assets/5c2aae63-eaa5-4578-9f8c-9502365993d9" />


## 2. Configuración del servicio

Se edita el archivo de configuración:
<img width="1022" height="22" alt="image" src="https://github.com/user-attachments/assets/33f7780b-3841-4526-937f-ab81c47dc7a8" />
<img width="1025" height="327" alt="image" src="https://github.com/user-attachments/assets/888ab91e-3d7a-421c-b17b-456f0e0859e9" />

Se valida la sintaxis del archivo de configuración:
<img width="1022" height="193" alt="image" src="https://github.com/user-attachments/assets/0465bffe-80e8-4157-bf22-eb99ca8b654d" />


## 3.Inicialización del servicio

Se habilita el servicio y se revisa su estado:
<img width="1023" height="402" alt="image" src="https://github.com/user-attachments/assets/119ac369-9b46-44f6-b3cd-8200855f223f" />


## 4. Comprobación desde un cliente

Se comprueba que el cliente recibe una IP del rango configurado:
<img width="974" height="508" alt="image" src="https://github.com/user-attachments/assets/c63bcbe5-f8a9-41d9-9bbf-15d2fa56ace3" />++

Se revisan los logs del sistema:
<img width="1021" height="18" alt="image" src="https://github.com/user-attachments/assets/a4784f2b-7d8c-430d-bb9c-985d6156f606" />
<img width="1023" height="78" alt="image" src="https://github.com/user-attachments/assets/34a1d5f4-18b0-46a1-94e5-bef5a6e4a83c" />

Se revisa el archivo de concesiones DHCP: 
<img width="1023" height="20" alt="image" src="https://github.com/user-attachments/assets/bf9b6a32-cad3-4249-9171-d818ab54a623" />
<img width="1022" height="204" alt="image" src="https://github.com/user-attachments/assets/200df62d-1774-415e-b1b9-6a8e2ce25752" />
