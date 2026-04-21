# Node Exporter

Node Exporter se utiliza para exponer métricas del sistema (CPU, RAM, disco, red)  para Prometheus.


## 1. Instalación desde el binario oficial

Se desinstala el node explorer que se habia instalado automaticamente como dependencia de prometheus desde apt:

<img width="1018" height="337" alt="image" src="https://github.com/user-attachments/assets/edf6406b-b69a-4af2-9eb0-78f88c54eaac" />


Descarga e intalación del binario oficial:

<img width="1021" height="99" alt="image" src="https://github.com/user-attachments/assets/27bd2793-23f6-4deb-94fd-3b96d79a507f" />

<img width="1024" height="205" alt="image" src="https://github.com/user-attachments/assets/29cd17dd-bc9c-4a6e-a5b4-498de977b4e4" />


## 2. Creación de un usuario dedicado

Se ccrea un usuario sin shell para el funcionamiento de node exporter:

<img width="1020" height="48" alt="image" src="https://github.com/user-attachments/assets/4b8bf689-2c36-4aad-a01f-592a57399725" />



## 2. Creación del servicio

Se crea el servicio y se añade la configuración:

<img width="1023" height="12" alt="image" src="https://github.com/user-attachments/assets/5a0b2628-2305-4238-8643-1e3ab300e148" />


<img width="1020" height="183" alt="image" src="https://github.com/user-attachments/assets/723b4f05-e646-40aa-89d0-368508ffe862" />


Se habilita y se arranca el servicio:


INCIDENCIAS:
Imagen de ssystemctl status. El error es pq el usuario y grupo de node_exporter no tienen permisos en la carpeta /opt/node_exporter
<img width="1024" height="301" alt="image" src="https://github.com/user-attachments/assets/c6cea5f2-135c-4fd8-b28e-bc37919f3f18" />

permisos: 
<img width="1017" height="98" alt="image" src="https://github.com/user-attachments/assets/2c741ffa-b068-4b4d-a52a-a245b300e7d9" />
