# Node Exporter

Node Exporter se utiliza para exponer métricas del sistema (CPU, RAM, disco, red)  para Prometheus.

Se instala en los servidores:

- **core-linux** (192.168.100.10)  
- **monitoring** (192.168.100.11)  
- **docker-host** (192.168.100.12)
  

## 1. Instalación desde el binario oficial

Se elimina el paquete `prometheus-node-exporter` que venía instalado automáticamente como dependencia:

<img width="1018" height="337" alt="image" src="https://github.com/user-attachments/assets/edf6406b-b69a-4af2-9eb0-78f88c54eaac" />


Descarga y se descomprime el binario oficial:

<img width="1021" height="99" alt="image" src="https://github.com/user-attachments/assets/27bd2793-23f6-4deb-94fd-3b96d79a507f" />

<img width="1024" height="205" alt="image" src="https://github.com/user-attachments/assets/29cd17dd-bc9c-4a6e-a5b4-498de977b4e4" />


## 2. Creación de un usuario dedicado

Se crea un usuario sin shell para ejecutar node exporter:

<img width="1020" height="48" alt="image" src="https://github.com/user-attachments/assets/4b8bf689-2c36-4aad-a01f-592a57399725" />



## 3. Creación del servicio

Se crea el archivo del servicio:

<img width="1021" height="15" alt="image" src="https://github.com/user-attachments/assets/56e4a3d9-e453-41fc-96d4-da2dffe79199" />

Se configura:

<img width="1022" height="197" alt="image" src="https://github.com/user-attachments/assets/68747e15-3d4d-487c-b61b-91b1cf5a2be3" />

Se recarga systemd, se habilita y se arranca el servicio:

<img width="1021" height="382" alt="image" src="https://github.com/user-attachments/assets/7c00aa33-6b97-4518-959c-96c5b6276586" />


## 4.  Instalación en los tres servidores

Node Exporter se instala de la misma forma en:

- **core-linux**
- **monitoring**
- **docker-host**

Cada servidor debe tener:

- el binario en `/opt/node_exporter`
- el usuario `node_exporter`
- el servicio systemd activo
- el puerto **9100/tcp** accesible

## 5. Validación

Se valida desde el navegador:

<img width="1549" height="323" alt="image" src="https://github.com/user-attachments/assets/8a2213d9-1c9a-4941-a9ab-acf91aff4ca8" />

Se valida desde el terminal:

<img width="1022" height="15" alt="image" src="https://github.com/user-attachments/assets/aa55dc2c-cae4-4895-a8c6-029e8c1db14e" />

<img width="1023" height="257" alt="image" src="https://github.com/user-attachments/assets/66191314-1e7c-4043-964a-35672d3864c7" />


---


La integración con Prometheus se documenta en detalle en [prometheus.md](./prometheus.md).
