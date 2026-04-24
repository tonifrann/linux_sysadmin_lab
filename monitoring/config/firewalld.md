# Firewalld

Configuración del firewall en el servidor monitoring. Se utiliza firewalld para mantener consistencia con el resto de servidores.


## Aplicar reglas

Se instala firewalld desde apt y se abren unicamente los puertos para los servicios instalados:

- Prometheus --> 9090/tcp
- Node Exporter --> 9100/tcp
- Grafana --> 3000/tcp

<img width="1020" height="129" alt="image" src="https://github.com/user-attachments/assets/2ea6f029-b336-45a8-a813-07472b056f32" />


Se verifica la configuración:

<img width="1020" height="50" alt="image" src="https://github.com/user-attachments/assets/203b00cc-af61-44eb-9d16-9473b166d403" />
