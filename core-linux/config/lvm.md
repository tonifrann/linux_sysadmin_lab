# Gestión de LVM y ampliación de almacenamiento

En este documento, se mostrará la creación del LVM en el servidor y su posterior ampliación añadiendo un nuevo disco.


## 1. Verificación de los discos

Se añaden dos discos de 10GB en el servidor para crear el LVM y se verifican:

<img width="988" height="195" alt="image" src="https://github.com/user-attachments/assets/f9631f72-dad8-4675-b6ca-8843970788a3" />


## 2. Creación de los Physical Volume (PV)

Se inicializan los dos discos que van a formar parte del VG y se comprueban:

<img width="992" height="161" alt="image" src="https://github.com/user-attachments/assets/aace64b4-85fb-4cf8-ab08-5543215fa350" />


## 3. Creación del Volume Group (VG) con dos discos

Se crea el VG usando los dos discos y se comprueba:

<img width="990" height="118" alt="image" src="https://github.com/user-attachments/assets/26c756e8-db05-4f4f-8cfb-b9cae41d3dc9" />


## 4. Creación del Logical Volume (LV)

Se crea el LV utilizando todo el espacio libre del VG y se comprueba: 

<img width="988" height="126" alt="image" src="https://github.com/user-attachments/assets/66777724-4675-4a15-9bcb-df263dba1daa" />


## 5. Formateo y montaje

Se formatea el volumen en XFS el sistema de archivos recomendado por Rocky/RedHat para entornos con LVM:

<img width="992" height="206" alt="image" src="https://github.com/user-attachments/assets/0af4f477-defa-4081-b04d-d4dc755fa2d3" />


Se crea el punto de montaje y se monta:

<img width="992" height="44" alt="image" src="https://github.com/user-attachments/assets/ba34a274-17da-4398-b0b3-ed3b4c72ad8d" />


Se compueba:

<img width="996" height="190" alt="image" src="https://github.com/user-attachments/assets/f55680d2-bc2a-4ee3-800d-2b8f771658d9" />



## 6. Montaje persistente (fstab)

Se obtiene el UUID:

<img width="997" height="46" alt="image" src="https://github.com/user-attachments/assets/1525aef0-6930-4812-a109-f293cd734ef8" />

NOTA: El uso de UUID garantiza que el montaje sea estable incluso si cambian los nombres de los dispositivos.


Se modifica el /etc/fstab:

<img width="1004" height="277" alt="image" src="https://github.com/user-attachments/assets/36ca5680-335b-48aa-9b98-5e99cc63712a" />

Se verifica que la nueva entrada en /etc/fstab se ha montado correctamente.

<img width="996" height="35" alt="image" src="https://github.com/user-attachments/assets/4820a04f-b8d9-43f2-b588-65e722e26d37" />


## 7. Ampliación del LV con un nuevo disco

Se añade un disco nuevo de 5GB y se verifica:

<img width="991" height="227" alt="image" src="https://github.com/user-attachments/assets/3b97ef78-1ee8-4d14-84df-609959e1ff90" />


Se inicializa el disco, se añade al VG y se amplia el LV. La ampliación se realiza sin desmontar el sistema de archivos (en caliente):

<img width="991" height="305" alt="image" src="https://github.com/user-attachments/assets/b709489a-7a81-4715-bc19-132289caca3a" />


Se verifica que se ha ampliado correctamente:

<img width="993" height="189" alt="image" src="https://github.com/user-attachments/assets/3e93fb65-dd88-4392-a52b-f93d57774a56" />


## 8. Snapshots en LVM

LVM también ofrece la posibilidad de crear snapshots, muy útiles antes de aplicar cambios críticos.
En este laboratorio no se han utilizado para mantener el foco en la gestión y ampliación del almacenamiento.
