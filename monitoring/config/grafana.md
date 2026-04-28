# Grafana

Grafana es el servicio que nos permite ver las métricas de manera gráfica.

Se utiliza para mostrar en gráficos las métricas que recoge Prometheus.


## 1. Instalación

Se descarga e instala Grafana desde un paquete .deb de su web oficial:

<img width="1022" height="232" alt="image" src="https://github.com/user-attachments/assets/ea9e7d89-88ca-4d32-ba84-187d27d4bad0" />


Se habilita, arranca el servicio y se revisa su status:

<img width="1021" height="431" alt="image" src="https://github.com/user-attachments/assets/72512908-bd7b-4eeb-8973-ceec5f647f4f" />


## 2. Acceso web

Se accede a Grafana via web: 
<img width="1178" height="769" alt="image" src="https://github.com/user-attachments/assets/531ee087-6de4-4721-b1dd-d6df203c3952" />


Usuario y contraseña por defecto: `admin`
Se solicita cambio de contraseña en el primer acceso.

<img width="1905" height="606" alt="image" src="https://github.com/user-attachments/assets/271a8b9d-7b7a-4148-b2be-c929d4f97cfa" />



## 3. Añadir Prometheus como datasource

Se añade Prometheus como datasource principal:

<img width="1884" height="780" alt="image" src="https://github.com/user-attachments/assets/a418d455-ecc4-431d-9074-ae5fbd339a17" />


## 4. Importar dashboard Node Exporter (ID 1860)

Se importa el dashboard oficial (ID 1860) para visualizar métricas de los servidores:

<img width="1178" height="1048" alt="image" src="https://github.com/user-attachments/assets/dcefa452-6eca-409c-b40a-4423b9fb973f" />


## 5. Validación del sistema

- La dirección para acceder a Grafana es http://192.168.100.11:3000
- El Datasource de Prometheus está conectado correctamente
- Los Dashboards están mostrando métricas en tiempo real

