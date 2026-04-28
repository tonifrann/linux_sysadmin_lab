# Incidencia: Disco lleno

El sistema se ha quedado sin espacio en disco, lo que está provocando fallos en los servicios.

## 1. Problema

El sistema empieza a mostrar errores ya que la raíz del sistema se queda sin espacio.


## 2. Sintomas

- Aparecen errores al escribir en disco
- Algunos servicios que no pueden arrancar
- Aparecen mensajes indicando que no hay espacio disponible en el disco
- El sistema se relentiza y se vuelve inestable


## 3. Diagnostico

Se comprueba el uso del disco y se ve que la raiz está al 100% de uso:

<img width="989" height="65" alt="image" src="https://github.com/user-attachments/assets/f2f8105a-05ae-454f-b6c2-a32634fc464a" />

Una vez se detecta que la raíz está llena, se identifican los directorios que ocupan más espacio:

<img width="993" height="367" alt="image" src="https://github.com/user-attachments/assets/ff80b15f-3ac6-4242-b730-ee92e20978d6" />

Se revisa el directorio ```/var/log``` con más detalle:

<img width="992" height="336" alt="image" src="https://github.com/user-attachments/assets/25f9678d-12b2-4b42-aa1d-bd5558922a4b" />


## 4. Causa

Se han ido acumulando logs en /var/log debido a que no está configurada la rotación, ni se han ido limpiando periodicamente, esto ha hecho que el disco se quede sin espacio.


## 5: Solución

Se eliminan los logs que ya no son necesarios para liberar espacio:

<img width="995" height="17" alt="image" src="https://github.com/user-attachments/assets/bc6ae155-541b-4219-b949-85ff353d5d79" />


## 6. Verificación 

Se comprueba que hay espacio en el disco:

<img width="992" height="61" alt="image" src="https://github.com/user-attachments/assets/37af820d-c301-415c-a742-fb5902a316d1" />


## 7. Prevención

- Configurar rotación de logs (logrotate)
- Monitorizar uso de disco 
- Revisar periódicamente la carpeta /var/log
- Limitar tamaño de los logs de systemd (journald)
