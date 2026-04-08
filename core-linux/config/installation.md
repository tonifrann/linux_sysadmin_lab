# Instalación de Rocky Linux 9

## 1. Descarga de la ISO

La ISO descargada desde la página oficial de Rocky Linux.

## 2. Configuración de la máquina virtual

- 2 vCPU  
- 4 GB RAM  
- 40 GB disco (LVM automático)  
- Red: NAT (Hyper-V)  
- Acceso SSH con root deshabilitado

## 3. Validaciones tras la instalación

### Verificar el disco y el particionado automático

```bash
lsblk
```
<img width="1006" height="150" alt="image" src="https://github.com/user-attachments/assets/c1bab7f4-d0a1-42bf-9a43-c12e3cdb4f41" />

### Verificación del espacio libre del disco
```bash
df -h
```
<img width="1001" height="161" alt="image" src="https://github.com/user-attachments/assets/30483227-e315-4958-b3e8-201704886fab" />


### Cambio de nombre 

```bash
hostnamectl
```
<img width="1000" height="86" alt="image" src="https://github.com/user-attachments/assets/0fa543b5-4427-4b1b-a076-386d52b3209c" />

### La configuración de red
```bash
ip addr
```
<img width="1003" height="143" alt="image" src="https://github.com/user-attachments/assets/b16f70e1-77bf-4b36-87c7-d6c7fd4ea728" />



Nota: Hyper‑V NAT no proporciona DHCP, por lo que la interfaz no obtiene IP automáticamente.
La configuración de red se realiza manualmente en el apartado de [Configuración de red](networking.md)
Se utiliza LVM automático para la instalación inicial, aunque más adelante se configurará manualmente.

