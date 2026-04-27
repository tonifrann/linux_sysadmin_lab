# Configuración de Firewall (firewalld)

Este entorno se ha configurado con ```firewalld```, aunque en otros servidores del laboratorio se configurarán con ```ufw``` e ```iptables``` para trabajar distintos tipos de configuración en firewalls.

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


## 5. Apertura del puerto 9100/tcp (Node Exporter)

Node Exporter expone métricas en el puerto 9100/tcp, por lo que es necesario permitirlo en firewalld:

<img width="996" height="78" alt="image" src="https://github.com/user-attachments/assets/969029a3-05c7-4abc-8233-1e6122e65e12" />


## 6. Verificación de las reglas

Se comprueba que los servicios estan correctamente configurados.

<img width="991" height="259" alt="image" src="https://github.com/user-attachments/assets/42e855c9-0f8c-468b-9495-b55fe31df694" />




