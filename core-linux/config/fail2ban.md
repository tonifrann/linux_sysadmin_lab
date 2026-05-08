# Fail2ban

Fail2ban se utiliza para proteger el servidor de ataques de fuerza bruta.

Fail2ban resiva los logs del sistema y bloquea automáticamente las IP que intentan acceder varias veces con intentos fallidos.

En este servidor Fail2ban se utiliza para proteger:

- SSH (para evitar accesos no autorizados)

- Nginx (para detener peticiones maliciosas o que se repiten demasiadas veces)


## 1. Instalación
Instalar Fail2ban y el módulo de integración con firewalld:
