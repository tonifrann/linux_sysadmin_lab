# Incidencia: Target DOWN

## 1. Problema

Prometheus muestra el target `docker-host` como **DOWN**, impidiendo la recolección de métricas.

<img width="1913" height="809" alt="image" src="https://github.com/user-attachments/assets/bc778469-055f-4f6d-9844-e193befd0121" />


## 2. Síntomas

- El panel `/targets` indica fallo de conexión.
- No se reciben métricas del nodo.
- El resto de targets están en estado UP.
- En Grafana no se muestran datos del servidor.


## 3. Diagnóstico

Se revisa el estado del servicio en `docker-host`:

<img width="1021" height="222" alt="image" src="https://github.com/user-attachments/assets/14e186ea-fc84-44f9-b4cc-4683970af13b" />


## 4. Causa
node_exporter no está levantado en el servidor docker-host.


## 5. Solución

Se inicia el servicio:

<img width="1022" height="17" alt="image" src="https://github.com/user-attachments/assets/f7be02e0-1617-48b6-98f7-f8e0a70a26f9" />


## 6. Verificación

El target pasa a UP en el panel /targets.

<img width="1912" height="779" alt="image" src="https://github.com/user-attachments/assets/a79295af-c309-4afe-9b5d-0ebf68f96875" />


## 7. Prevención

- Habilitar el servicio para que arranque automáticamente.
- Monitorizar el estado del servicio desde Prometheus.
- Revisar que el servicio no se pare despues de un reinicio o actualizacion.
