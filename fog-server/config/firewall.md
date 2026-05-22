# Configuración de Firewall (firewalld)

Este servidor utiliza firewalld para gestionar las reglas de red.  
FOG requiere varios servicios abiertos para que funcione correctamente: interfaz web, PXE, TFTP, NFS y RPC.


## 1. Configuración de los servicios

Acceso HTTP:
<img width="1021" height="66" alt="image" src="https://github.com/user-attachments/assets/c2fbe297-a517-4d24-bb9b-e7dee3fa9c30" />

Arranque por red  (TFTP):
<img width="1021" height="38" alt="image" src="https://github.com/user-attachments/assets/fa7091b1-79a7-4a65-897a-8294406407d5" />

Para almacenar y transferir imagenes (NFS):
<img width="1021" height="101" alt="image" src="https://github.com/user-attachments/assets/23cef64a-42e4-4bbe-b944-b8fbd0daf17c" />

Para usar snapins (FTP):
<img width="1021" height="35" alt="image" src="https://github.com/user-attachments/assets/ed4ab14d-2ab1-49d1-a948-84cee8e8f4ef" />

Se aplican los cambios:
<img width="1023" height="32" alt="image" src="https://github.com/user-attachments/assets/2ee6aa83-cf33-4593-bf29-94a5bdfb2574" />


## 3. Verificación
<img width="1025" height="240" alt="image" src="https://github.com/user-attachments/assets/9dd7a669-9800-49bd-a5a2-1de5a2ed4a9c" />


## 4. Resultado

Con estas reglas, el servidor FOG permite:

- Acceso a la web para la instalación y gestión

- Arranque de los clientes por PXE

- Transferencia de imágenes vía NFS

- Snapins vía FTP

El firewall queda preparado antes de la instalación de FOG.
