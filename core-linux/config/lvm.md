# Gestión de LVM 

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




## 5. Formateo y montaje

Se formatea el volumen y se monta:

<img width="985" height="256" alt="image" src="https://github.com/user-attachments/assets/0c9c3aeb-3d33-409f-9dc1-113ef0485130" />


Se compueba:

<img width="993" height="197" alt="image" src="https://github.com/user-attachments/assets/a4f85438-3119-44ff-b24c-8ab519f9bf9b" />


## 6. Montaje persistente (fstab)

<img width="1009" height="50" alt="image" src="https://github.com/user-attachments/assets/9670fe8f-7a1b-4172-a869-71997d8925b6" />

<img width="1009" height="278" alt="image" src="https://github.com/user-attachments/assets/bf736e94-743f-48f1-8ded-c44ac1f82247" />


