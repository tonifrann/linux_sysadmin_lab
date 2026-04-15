# Incidencia: Error de firewall

Se simula un problema en la configuración del firewall que impide el acceso a servicios que deberían estar disponibles.

## 1. Problema

No es posible acceder al servidor web desde la red, aunque el servicio está funcionando correctamente.

> NOTA: El problema se ha provocado eliminando las reglas de HTTP/HTTPS en firewalld para simular un error de configuración.


## 2. Síntomas

- No se puede acceder a la web desde el navegador
- Timeout o conexión rechazada
- El servicio está activo en el servidor

Se comprueba que no funciona el acceso web desde un navegador:
<img width="466" height="196" alt="image" src="https://github.com/user-attachments/assets/a75df44f-1be7-47b4-b477-ea1030b420ab" />


## 3. Diágnostico

Se verifica que Nginx está funcionando:

<img width="991" height="288" alt="image" src="https://github.com/user-attachments/assets/a6fee1e2-2e40-4903-81a0-77ba3eb6e9c4" />

Se compueba que el puerto 80 está escuchando: 

<img width="994" height="63" alt="image" src="https://github.com/user-attachments/assets/6d7db062-6791-4953-8abe-46197ca54d86" />

Se revisa la configuración del firewall:

<img width="995" height="257" alt="image" src="https://github.com/user-attachments/assets/f1ae5a83-7aad-4718-9e14-3c04defe62a0" />


## 4. Causa

El firewall no está permitiendo el trafico HTTP/HTTPS, y bloquea el acceso aunque el servicio de nginx está activo.


## 5. Solución

Se añaden las reglas en el firewall:

<img width="996" height="109" alt="image" src="https://github.com/user-attachments/assets/61a1fd46-9552-487a-bf2e-5662c7df3f41" />


## 6. Verificación

Se comprueba el acceso desde el servidor:

<img width="994" height="48" alt="image" src="https://github.com/user-attachments/assets/fc954988-3885-4672-b807-72fd9e889c51" />

También desde el navegador:

<img width="374" height="124" alt="image" src="https://github.com/user-attachments/assets/982e28e2-32ce-4ebe-99b4-fb64f8147a74" />


## 7. Prevención

- Verificar reglas de firewall después de configurar servicios
- Comprobar conectividad desde cliente y servidor
- Documentar puertos necesarios por servicio
- Evitar cambios sin antes validar el funcionamiento
