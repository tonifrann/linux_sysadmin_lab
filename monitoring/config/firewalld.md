# Firewalld

Configuración del firewall en el servidor monitoring.


## Aplicar reglas

Se instala firewalld desde apt y se abren unicamente los puertos para los servicios instalados:

- Prometheus --> 9090/tcp
- Node Exporter --> 9100/tcp
- Grafana --> 3000/tcp

<img width="1021" height="388" alt="image" src="https://github.com/user-attachments/assets/215854a7-7bf3-405c-8f44-23db822564b6" />
