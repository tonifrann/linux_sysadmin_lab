# Incidencia: Error en la configuración de Prometheus

Prometheus muestra un error al validar el archivo `prometheus.yml`, haciendo que el servicio no funcione correctamente.

## 1. Problema

El servicio de Prometheus no arranca por culpa de un error en el archivo de configuración.

## 2. Síntomas

- El servicio aparece como *failed* al intentar iniciarlo.
- `systemctl status prometheus` muestra errores relacionados con la configuración.
- El comando de validación devuelve un error de sintaxis.
- La interfaz web no carga.

## 3. Diagnóstico

Se valida la configuración manualmente:

```bash
promtool check config /etc/prometheus/prometheus.yml

