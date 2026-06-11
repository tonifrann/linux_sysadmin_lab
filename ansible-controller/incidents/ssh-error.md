# Incidencia: Host UNREACHABLE por error SSH

## 1. Problema
Al ejecutar un playbook, Ansible no puede conectar con el servidor de pruebas ansible-test.
El proceso se detiene y el host aparece como UNREACHABLE.


## 2. Síntomas

- El playbook falla al iniciar la conexión SSH.

- El host aparece como UNREACHABLE.

- El mensaje de error indica un problema de autenticación SSH.

<img width="1061" height="165" alt="image" src="https://github.com/user-attachments/assets/829f8fca-58cd-4078-a6bd-a40148683d8b" />


# 3. Diagnóstico

Se comprueba la conectividad:

<img width="1022" height="106" alt="image" src="https://github.com/user-attachments/assets/14f563d8-3dbe-4ad1-bb08-898a8801005e" />


# 4. Causa

La clave pública del controlador Ansible no esta autorizada en el servidor ansible-test.

El usuario configurado en el inventario no tenía acceso SSH mediante clave.


# 5. Solución

Se vuelve a autorizar la clave pública:

<img width="1010" height="159" alt="image" src="https://github.com/user-attachments/assets/2bfe833d-b9cf-4ec0-a5ee-4a02785d874f" />


# 6. Verificación

 Se comprueba la conectividad de nuevo:

 <img width="1024" height="130" alt="image" src="https://github.com/user-attachments/assets/2ed7a47c-a7bb-4aed-ac53-f8e08171b201" />
