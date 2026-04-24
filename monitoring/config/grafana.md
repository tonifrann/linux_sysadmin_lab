# Grafana

Grafana es el servicio encargado de visualizar métricas.  
Se utiliza para representar gráficamente las métricas recogidas por Prometheus.


## 1. Instalación

Se descarga y descomprime el binario oficial de Grafana:

<img width="1022" height="232" alt="image" src="https://github.com/user-attachments/assets/ea9e7d89-88ca-4d32-ba84-187d27d4bad0" />


Se crea el usuario dedicado:

<img width="1021" height="65" alt="image" src="https://github.com/user-attachments/assets/344bed2b-90d9-4c8d-a6ac-fad23bc46e57" />


Se configura el servicio systemd:

<img width="1022" height="23" alt="image" src="https://github.com/user-attachments/assets/79a3bcf0-aa91-423f-81ee-6d32fc5547cd" />

<img width="1023" height="278" alt="image" src="https://github.com/user-attachments/assets/30fb8a1f-3924-430e-8e71-85a3bf2f153f" />


Se habilita y arranca el servicio:

📸 *Captura: enable + start*

---

## 2. Acceso web

Grafana queda accesible en:
http://<IP>:3000


Usuario por defecto: `admin`  
Se solicita cambio de contraseña en el primer acceso.

📸 *Captura: login inicial*

---

## 3. Añadir Prometheus como datasource

Se añade Prometheus como datasource principal:

- URL: `http://localhost:9090`
- Access: Server
- Save & Test → OK

📸 *Captura: configuración del datasource*

---

## 4. Importar dashboard Node Exporter (ID 1860)

Se importa el dashboard oficial para visualizar métricas de los servidores:

- Dashboard ID: **1860**
- Datasource: Prometheus

📸 *Captura: dashboard funcionando*

---

## 5. Organización

Se crea una carpeta `Monitoring` para agrupar dashboards relacionados.

📸 *Captura opcional*

---
