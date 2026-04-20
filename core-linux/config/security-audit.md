# Auditoría y seguridad

Este documento se implementan  algunas herramientas para auditar el sistema, controlar logs y detectar posibles problemas de seguridad.


## 1. auditd

Se utiliza auditd para registrar actividad del sistema como inicios de sesión, comandos ejecutados, accesos a archivos, con el objetivo de de tectar comportamientos anómalos.

Se revisa el estado del servicio:

<img width="998" height="261" alt="image" src="https://github.com/user-attachments/assets/394ea6fa-179b-4add-8d11-98b2fcab0630" />

Se revisan las autenticaciones registradas:

<img width="1001" height="289" alt="image" src="https://github.com/user-attachments/assets/0df2846f-4dc3-4187-a4e2-0851b379cc78" />



## logrotate

Se revisa la configuración de rotación de logs en servicios como Samba y Nginx para evitar crecimiento descontrolado.

<img width="997" height="390" alt="image" src="https://github.com/user-attachments/assets/e81c73df-519a-4b8b-bbc3-5f6f579073ae" />

Se comprueba la configuración de logrotate en Samba: 

<img width="994" height="177" alt="image" src="https://github.com/user-attachments/assets/01edea81-dafa-4da9-b218-4b0e7bc7642c" />

Se comprueba la configuración de logrotate en Nginx: 

<img width="994" height="228" alt="image" src="https://github.com/user-attachments/assets/37218b10-d68f-467a-87af-64614daa17d8" />

Se fuerza una rotación manual: 

<img width="994" height="178" alt="image" src="https://github.com/user-attachments/assets/f4160823-f6f9-47bf-b3e5-cc42b1af6f3d" />

> NOTA: algunos archivos no se ahn rotado porque ya existen rotaciones creadas automáticamente por el sistema. Esto confirma que logrotate está funcionando correctamente.
