# Configuración de Firewall (firewalld)

Este entorno está configurado ```firewalld```, aunque en otros servidores del laboratorio se configuraran con ```ufw```, ```iptables``` y ```nftables``` para trabajar distintos tipos de configuración en firewalls.

## 1. Estado del servicio

Se comprueba que firewalld está activo y habilitado:

<img width="1011" height="243" alt="image" src="https://github.com/user-attachments/assets/668f2461-6bcb-4e63-b514-5baed8c11bc5" />


## 2. Zona activa

Se identifica la zona activa de red:

<img width="1000" height="70" alt="image" src="https://github.com/user-attachments/assets/a60bd2e9-e907-4bc1-9682-05562b2b652c" />


## 3. Configuración inicial

Se revisan las reglas que hay configuradas.

<img width="997" height="274" alt="image" src="https://github.com/user-attachments/assets/ff8f600e-c3b7-46b0-a468-997e25d146eb" />


## 4. Permitir servicios necesarios

Se añaden los servicios que queremos permitir.

<img width="996" height="163" alt="image" src="https://github.com/user-attachments/assets/7047c98d-22c4-4db8-904f-9672566f3bd5" />


Una vez configurado Samba, se permite también su servicio en el firewall.

<img width="988" height="86" alt="image" src="https://github.com/user-attachments/assets/f83013fb-6edb-4ba2-b5cf-3e7cee99b207" />


## 5. Verificación de las reglas

Se comprueba que los servicios estan correctamente configurados.

<img width="1004" height="257" alt="image" src="https://github.com/user-attachments/assets/767f2801-45b8-45e4-adaa-a30e920c2d2a" />


## 6. Consideraciones de seguridad

- Solo se permiten los servicios necesarios.
- Se evita abrir puertos si existe el servicio.
