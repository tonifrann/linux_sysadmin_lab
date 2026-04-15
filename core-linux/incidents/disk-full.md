# Incidencia: Disco lleno

Se simula una situación en la que el sistema se queda sin espacio en disco, provocando fallos en servicios y comportamiento anormal.

## 1. Problema

El sistema empieza a mostrar errores debido a que la raíz se queda sin espacio.

<img width="991" height="33" alt="image" src="https://github.com/user-attachments/assets/7ac128e9-0d4d-42df-bac9-0499161917f4" />

> NOTA: El problema se ha provocado llenando /var/log, una ubicación crítica donde se almacenan logs del sistema, lo que puede afectar directamente al funcionamiento de servicios.


## 2. Sintomas

Errores al guardar archivos
Servicios que no arrancan o fallan
Lentitud general del sistema
Mensajes de disco lleno


## 3. Diagnostico

Se comprueba el disco y se ve que la raiz esta el 100% de uso:

<img width="989" height="65" alt="image" src="https://github.com/user-attachments/assets/f2f8105a-05ae-454f-b6c2-a32634fc464a" />

Se localizan los directorios que ocupan más espacio:

<img width="993" height="367" alt="image" src="https://github.com/user-attachments/assets/ff80b15f-3ac6-4242-b730-ee92e20978d6" />

Se instacciona el directorio con más detalle:

<img width="992" height="336" alt="image" src="https://github.com/user-attachments/assets/25f9678d-12b2-4b42-aa1d-bd5558922a4b" />


## 4. Causa

El disco se ha llenado de logs en /va/log.


## 5: Solución

Se eliminan los logs que se han generado para la prueba:

<img width="995" height="17" alt="image" src="https://github.com/user-attachments/assets/bc6ae155-541b-4219-b949-85ff353d5d79" />


## 6. Verificación 

Se comprueba que hay espacio en el disco:

<img width="992" height="61" alt="image" src="https://github.com/user-attachments/assets/37af820d-c301-415c-a742-fb5902a316d1" />


## 7. Prevención

Para evitar que vuelva a ocurrir:

- Configurar rotación de logs con logrotate
- Revisar periódicamente el uso de /var/log
- Monitorizar el uso de disco
- Evitar acumulación de logs innecesarios
