# Fail2ban

Fail2ban se utiliza para proteger el servidor de ataques de fuerza bruta.

Fail2ban revisa los logs del sistema y bloquea automáticamente las IP que intentan acceder varias veces con intentos fallidos.

En este servidor Fail2ban se utiliza para proteger:

- SSH (para evitar accesos no autorizados)

- Nginx (detección de peticiones repetitivas, errores HTTP sospechosos y posibles intentos de fuerza bruta)


## 1. Instalación

Se habilita el repositorio de ```epel-release``` para poder instalar Fail2ban:
<img width="1021" height="138" alt="image" src="https://github.com/user-attachments/assets/0b41d520-b6dc-476b-a79a-7200e1c9cffb" />

Se instala Fail2ban y se integra con firewalld:
<img width="1017" height="267" alt="image" src="https://github.com/user-attachments/assets/e6969626-8934-4a2a-9585-5bbf6abd9fde" />

Se habilita y se inicia el servicio:
<img width="1023" height="289" alt="image" src="https://github.com/user-attachments/assets/78d4559d-7092-4448-bcbd-b2cc915944ed" />


## 2. Configuración

Se crea el archivo de configuración:
<img width="1022" height="16" alt="image" src="https://github.com/user-attachments/assets/ec1d2e85-510c-4fb7-bc82-7cd4e67d2aef" />

Se modifica el archivo con los ajustes deseados, el tiempo de baneo de una IP, el tiempo en el que se cuentan los intentos, el numero máximo de intentos fallidos, etc:
<img width="1022" height="113" alt="image" src="https://github.com/user-attachments/assets/86283852-7c5b-483a-828d-03de2e133ec8" />


## 3. Protección de SSH

Se crea el archivo de configuración jail:
<img width="1023" height="17" alt="image" src="https://github.com/user-attachments/assets/9357fffa-cd3b-4791-a400-68840debe10b" />

Se configura el archivo de manera que se active la protección SSH y se bloqueen las IPs si realizan 3 fallos seguidos:
<img width="1023" height="112" alt="image" src="https://github.com/user-attachments/assets/15df3e81-8a25-4d37-8054-8e2576a7c1cd" />


## 4. Protección de Nginx (HTTPS)

Se crea el archivo de configuración para el jail:
<img width="1020" height="19" alt="image" src="https://github.com/user-attachments/assets/72b5ebd0-c821-4f57-bbb4-0d2244fa2068" />

Se configura:
<img width="1023" height="256" alt="image" src="https://github.com/user-attachments/assets/d121145b-16ef-4ab5-a5ae-cc435c1065d8" />


## 5. Configuración de los filtros

Se revisa un filtro que ya está creado, y que sirve para detectar solicitudes incorrectas o errores 400 (basura):
<img width="1022" height="20" alt="image" src="https://github.com/user-attachments/assets/2fdc2fe6-a945-4def-97c5-71d0bd3b96e1" />

Se deja como está:
<img width="1022" height="274" alt="image" src="https://github.com/user-attachments/assets/887818e9-1170-4ee7-8b3e-4e4cd0e09fb2" />

Se crea un filtro personalizado de Nginx para detectar patrones repetitivos compatibles con ataques fuerza bruta:
<img width="1020" height="18" alt="image" src="https://github.com/user-attachments/assets/0b03020f-bb5d-4314-9e0c-2c130b00ecac" />

Se configura:
<img width="1025" height="181" alt="image" src="https://github.com/user-attachments/assets/5f86f2a9-5df1-4680-8139-07cf985fe1bd" />


## 6. Jails que se activan con los filtros

Se crea el jail para el filtro de las ```solicitudes incorrectas```:
<img width="1022" height="19" alt="image" src="https://github.com/user-attachments/assets/c12d6e52-a460-4877-82b7-623bd480b795" />

Se configura:
<img width="1022" height="145" alt="image" src="https://github.com/user-attachments/assets/fda1d841-215c-435c-9212-904d98424b26" />

Se crea el jail para el filtro de los ```ataques por fuerza bruta```:
<img width="1022" height="19" alt="image" src="https://github.com/user-attachments/assets/8f5efc5f-a57c-4a96-ad1b-61b16e2e65e6" />

Se configura:
<img width="1026" height="148" alt="image" src="https://github.com/user-attachments/assets/b1324ddf-8bf9-4f3c-a9bf-fe6cca3c5c1f" />


## 7. Integracion con firewald
Fail2ban aplica los baneos a través de rich-rules de firewalld:
<img width="1021" height="66" alt="image" src="https://github.com/user-attachments/assets/838342fc-fcae-45eb-960b-76bc62b57c9a" />

## 8. Validación 

Se revisan las jails activas:
<img width="1021" height="79" alt="image" src="https://github.com/user-attachments/assets/eb7cf742-a9d5-4a93-9ebf-34bdb2423794" />

Se fuerza el baneo de una IP:
<img width="1022" height="49" alt="image" src="https://github.com/user-attachments/assets/1e4a9944-a58d-441e-85e4-0162adc4eef5" />

Comprobar que IP's hay bloqueadas:
<img width="1024" height="163" alt="image" src="https://github.com/user-attachments/assets/7dbe54de-0ae8-432c-96a7-4f78bd879461" />


## 9. Logs y troubleshooting

Se revisan los logs en tiempo real:
<img width="1024" height="178" alt="image" src="https://github.com/user-attachments/assets/ac0d69b8-bc7b-4cf4-ac05-223138b42e52" />

Se desbloquea una de las IP's manualmente:
<img width="1023" height="208" alt="image" src="https://github.com/user-attachments/assets/c6977953-7f99-4892-b606-b1658bf8423e" />


## 10. Conclusión

La implementación de Fail2ban añade una capa adicional de protección ante a ataques repetitivos y accesos no autorizados.

La integración con firewalld y la creación de filtros personalizados permiten adaptar la protección a los servicios utilizados en el servidor.

