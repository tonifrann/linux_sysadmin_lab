# Incidencia: Disco lleno

El sistema se ha quedado sin espacio en disco, provocando fallos en servicios y comportamiento anormal.

## 1. Problema

El sistema empieza a mostrar errores debido a que la raíz se queda sin espacio.


## 2. Sintomas

- Errores al escribir en disco
- Servicios que no arrancan
- Mensajes de "no hay espacio en el disco"
- Sistema lento e inestable


## 3. Diagnostico

Se comprueba el uso disco y se ve que la raiz esta el 100% de uso:

<img width="989" height="65" alt="image" src="https://github.com/user-attachments/assets/f2f8105a-05ae-454f-b6c2-a32634fc464a" />

Una vez detectado que la raíz está llena, se identifican los directorios que ocupan más espacio:

<img width="993" height="367" alt="image" src="https://github.com/user-attachments/assets/ff80b15f-3ac6-4242-b730-ee92e20978d6" />

Se revisa el directorio ```/var/log``` con más detalle:

<img width="992" height="336" alt="image" src="https://github.com/user-attachments/assets/25f9678d-12b2-4b42-aa1d-bd5558922a4b" />


## 4. Causa

Se han ido acumulando logs en /var/log debido a que no está configurada la rotación, ni se han ido limpiando periodicamente, esto ha provocado que el disco se quede sin espacio.


## 5: Solución

Se eliminan los logs que ya no son necesarios para liberar espacio:

<img width="995" height="17" alt="image" src="https://github.com/user-attachments/assets/bc6ae155-541b-4219-b949-85ff353d5d79" />


## 6. Verificación 

Se comprueba que hay espacio en el disco:

<img width="992" height="61" alt="image" src="https://github.com/user-attachments/assets/37af820d-c301-415c-a742-fb5902a316d1" />


## 7. Prevención

- Configurar rotación de logs (logrotate)
- Monitorizar uso de disco
- Revisar periódicamente /var/log
- Limitar tamaño de logs de systemd (journald)
