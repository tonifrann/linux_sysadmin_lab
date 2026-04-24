# Firewalld

Configuración del firewall en el servidor monitoring.


## Aplicar reglas

Se instala firewalld desde apt y se abren unicamente los puertos para los servicios instalados:

- Prometheus --> 9090/tcp
- Node Exporter --> 9100/tcp
- Grafana --> 3000/tcp

<img width="1022" height="160" alt="image" src="https://github.com/user-attachments/assets/d7f9086b-b5e0-4a9e-887d-ba58915ca0eb" />

