# Incidencia: Error en la configuración de Prometheus


## 1. Problema

El servicio de Prometheus no arranca por culpa de un error en el archivo de configuración.


## 2. Síntomas

- El servicio aparece como *failed* al intentar iniciarlo.
- `systemctl status prometheus` muestra errores relacionados con la configuración.
- El comando de validación devuelve un error de sintaxis.
- La interfaz web no carga.


## 3. Diagnóstico

Se revisa el estado del servicio:

<img width="1019" height="253" alt="image" src="https://github.com/user-attachments/assets/6f843e57-19d2-4728-a16f-e5252521b66a" />

Se valida la configuración manualmente:

<img width="1021" height="55" alt="image" src="https://github.com/user-attachments/assets/279259c0-383f-4faa-b1c4-e96c3a83c36f" />


## 4. Causa

La línea `- job_name: prometheus` tenía dos espacios menos de los necesarios, provocando un error en el bloque `scrape_configs`.

<img width="1022" height="58" alt="image" src="https://github.com/user-attachments/assets/9c410b57-a07d-4dc3-a516-66ab7970010e" />


## 5. Solución

Se corrige el archivo prometheus.yml:

<img width="1022" height="52" alt="image" src="https://github.com/user-attachments/assets/e35c440a-ce6b-4be3-83f1-f626c3b1d339" />

Se valida:

<img width="1022" height="52" alt="image" src="https://github.com/user-attachments/assets/611a942a-6e99-48cb-92ae-9e4d8f24ebd5" />


## 6. Verificación

Se reinicia el servicio y se revisa su funcionamiento:

<img width="1020" height="259" alt="image" src="https://github.com/user-attachments/assets/a145e76c-fccc-4d89-bee1-d0bb6a1e53d9" />


## 7. Prevención

- Validar siempre el archivo antes de reiniciar el servicio.

- Mantener una correcta sintaxis en los archivos de configuración YAML.
