# Automatización en FOG

FOG no solo se utiliza para desplegar sistemas operativos, sino también como una plataforma para automatizar tareas.

En este servidor, la automatización se utiliza para que todos los equipos sean iguales, reduciendo la intervención manual y así poder administrar todo desde un unico sitio.


## 1. Automatización

La automatización en FOG se basa en tres conceptos:

- Estandarización de equipos después del despliegue
  
- Ejecución remota de tareas en hosts registrados
  
- Centralización de scripts sin intervención local
  
El objetivo es reducir tareas repetitivas y mantener igual el entorno.


## 2. Ejecución

La automatización no depende del arranque PXE, sino de los equipos ya registrados en FOG.

El flujo general es:

- El host se registra en FOG
  
- El cliente de FOG mantiene comunicación con el servidor
  
- Desde la consola se asignan tareas a los equipos
  
- El host ejecuta la tarea en segundo plano
  
- El resultado de la tarea se registra en el sistema de FOG


## 3. Snapins 

Los Snapins son la forma de instalación de software y la ejecución de scripts.

Los snapins nos permiten:

- Instalar software sin necesidad de estar fisicamente en el equipo

- Ejecutar scripts en lote

- La configuración inicial de los equipos

- Realizar tareas de mantenimiento o solucionar problemas


## 4. Uso en el entorno

La automatización se utiliza principalmente para:

- Aplicar configuraciones comunes en todos los equipos
  
- Evitar tener que configurar manualmente después de cada despliegue

- Mantener la coherencia entre las estaciones de trabajo

- Reducir el tiempo de intervención

  
