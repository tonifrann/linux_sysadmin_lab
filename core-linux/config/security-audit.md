# Auditoría y seguridad

Este documento se implementan  algunas herramientas para auditar el sistema, controlar logs y detectar posibles problemas de seguridad.


## 1. auditd

Se utiliza auditd para registrar eventos relevantes del sistema.

Se revisa el estado del servicio:

<img width="998" height="261" alt="image" src="https://github.com/user-attachments/assets/394ea6fa-179b-4add-8d11-98b2fcab0630" />

Se añaden algunas reglas para auditar cambios sensibles en el suistema.

<img width="992" height="19" alt="image" src="https://github.com/user-attachments/assets/dc5e6569-a03e-4b31-b1e4-718fc9bd66ac" />

<img width="1009" height="315" alt="image" src="https://github.com/user-attachments/assets/1cedf6d1-281b-4b12-904a-1c72bdf41c94" />



## logrotate

Se ha configurado una rotación para los Backups

<img width="1006" height="131" alt="image" src="https://github.com/user-attachments/assets/a2999ab4-8614-4629-ad67-7f03f06161be" />
