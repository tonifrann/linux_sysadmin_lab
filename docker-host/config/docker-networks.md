# Docker Networks

Configuración de redes en Docker para la comunicación entre contenedores.


## 1. Creación de red personalizada 

Se crea una red tipo bridge para aislar y gestionar la comunicación entre los contenedores:

<img width="1022" height="32" alt="image" src="https://github.com/user-attachments/assets/4a88d63c-b746-46ce-be95-48dd2462ead5" />

Se comprueba que la red ha sido creada correctamente:

<img width="1023" height="96" alt="image" src="https://github.com/user-attachments/assets/d0a84e09-003f-464a-b4d0-493658ae4393" />


## 3. Conexión de contenedor a la red

Se lanza un contenedor y se conecta a la red que hemos creado:

<img width="1024" height="50" alt="image" src="https://github.com/user-attachments/assets/9578d5b0-a598-46bc-8b00-71090291817b" />



## 4. Revisión de la red

Se revisa la configuración de la red y los contenedores asociados:

<img width="1022" height="14" alt="image" src="https://github.com/user-attachments/assets/147b8e10-b26b-48cd-bd70-3f33e28ed462" />
<img width="1021" height="754" alt="image" src="https://github.com/user-attachments/assets/ecda637d-458d-448e-918c-9d1aa8adfa9c" />

---

El contenedor aparece asociado a la red y tiene conectividad dentro del entorno.
