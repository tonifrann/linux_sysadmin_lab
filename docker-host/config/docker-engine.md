# Docker Engine

Instalación y configuración de Docker Engine en el servidor docker-host.

---

## 1. Instalación del repositorio oficial

Se añade el repositorio de Docker para poder descargar las versiones estables y actualizadas:

<img width="1020" height="17" alt="image" src="https://github.com/user-attachments/assets/dbfac7ba-a72c-4405-9cab-fe9b16716252" />



<img width="1021" height="18" alt="image" src="https://github.com/user-attachments/assets/3e461544-a5d9-48ae-9675-1669cde04ec2" />



<img width="1020" height="97" alt="image" src="https://github.com/user-attachments/assets/2b22ba57-e090-45c7-9353-cbbf7d77cc89" />



sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/nullsudo inta
