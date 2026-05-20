# Automatización en FOG

FOG no solo se utiliza para desplegar sistemas operativos, sino también como una plataforma para automatizar tareas.

Esn este servidor, la automatización se utiliza para que todos los equipos sean iguales, reduciendo la intervención manual así y poder administrar todo desde un unico sitio.


## 1. Enfoque de automatización

La automatización en el entorno FOG se basa en tres ideas:

Estandarización de equipos tras el despliegue
Ejecución remota de tareas sobre hosts registrados
Centralización de scripts sin intervención local

Esto permite mantener un entorno homogéneo sin gestionar cada equipo de forma individual.

2. Modelo de ejecución

La automatización no depende del arranque PXE, sino de equipos ya registrados en FOG.

El flujo general es:

El host se registra en FOG
El cliente FOG mantiene comunicación con el servidor
Se asignan tareas o scripts desde la consola
El host ejecuta la tarea en segundo plano
El resultado queda registrado en el sistema
3. Snapins (modelo de distribución)

Los Snapins representan el mecanismo de distribución de software y scripts en el laboratorio.

Se utilizan como “unidad de automatización”, permitiendo:

Instalación de software sin acceso físico
Ejecución de scripts en lote
Configuración inicial de equipos
Tareas de mantenimiento o corrección
4. Integración con el laboratorio

La automatización no se entiende de forma aislada, sino como parte del flujo general del sistema:

PXE → despliegue de sistema base
FOG → registro del host
Snapins → configuración post-despliegue o mantenimiento
Scripts → estandarización del entorno
5. Uso real en el entorno

En este laboratorio, la automatización se utiliza principalmente para:

Aplicar configuraciones comunes en todos los equipos
Evitar configuración manual tras cada despliegue
Mantener coherencia entre estaciones de trabajo
Reducir tiempos de intervención administrativa
