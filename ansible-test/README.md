# ansible-test (Ubuntu 22.04)

Este servidor se utiliza exclusivamente para probar los roles y playbooks de Ansible antes de aplicarlos en servidores nuevos.

Permite validar configuraciones, detectar errores y asegurar que los roles funcionan correctamente en un entorno controlado.


## Estado inicial del servidor

- Ubuntu Server 22.04 recién instalado

- Usuario admin con acceso SSH con la clave pública del servidor ansible-controller

- Sin Node Exporter

- Sin reglas de firewall

- Sin configuraciones adicionales


## Pruebas realizadas con Ansible

Aqui se edocumentan las pruebas que se han ejecutado desde ansible-controller sobre este servidor.


## 1. Prueba del rol usuarios

Se ejecuta el playbook ```usuarios```

<img width="1024" height="245" alt="image" src="https://github.com/user-attachments/assets/bee475d7-d770-4e8b-b6bc-c2212f02f442" />

### Comprobaciones

Se comprueba que las configuraciones se han realizado correctamente:

<img width="1023" height="210" alt="image" src="https://github.com/user-attachments/assets/4cafc49a-1b65-4dab-850f-dd0f42ed7cd5" />


## 2. Prueba del rol node-exporter

Se ejecuta el playbook ```node-exporter```

<img width="1022" height="589" alt="image" src="https://github.com/user-attachments/assets/ef1cdb97-e679-4d80-a517-409ed120989e" />

### Comprobaciones

El servicio esta activo:
<img width="1022" height="164" alt="image" src="https://github.com/user-attachments/assets/03f1d4cc-5429-43c0-9ce4-f4d4a42fbdaa" />

El puerto 9100 esta abierto y en escucha:
<img width="1024" height="30" alt="image" src="https://github.com/user-attachments/assets/f534dd21-3046-4bd4-a934-1c6f9281dd18" />

Las metricas se estan enviando correctamente:

<img width="1024" height="15" alt="image" src="https://github.com/user-attachments/assets/29fa9181-322e-492c-9f70-d5b4cf22501b" />

<img width="1022" height="462" alt="image" src="https://github.com/user-attachments/assets/dbb78444-1e10-4c36-a3df-629f45767350" />


## 3. Prueba del rol paquetes-base

Se ejecuta el playbook ```paquetes-base```
<img width="1024" height="257" alt="image" src="https://github.com/user-attachments/assets/43b69e56-8cdb-44d5-8a24-98f3118b8bb9" />

### Comprobaciones

Se comprueba que todos los paquetes están correctamente instalados:

<img width="1021" height="691" alt="image" src="https://github.com/user-attachments/assets/b27870b9-c360-42c4-bf82-fb43211afcd6" />
