# Instalación de Rocky Linux 9

## 1. Descarga de la ISO
La ISO se ha descargado desde la página oficial de Rocky Linux.

## 2. Configuración de la máquina virtual
- 2 vCPU  
- 4 GB RAM  
- 40 GB de disco  
- Red: NAT Switch (Hyper‑V)  
- Particionado: Automático (LVM)  
- Root deshabilitado para SSH  

## 3. Primer arranque

Tras completar la instalación y acceder al sistema por primera vez, realizo las comprobaciones iniciales.

### Verificar el disco y el particionado automático

```bash
lsblk
```

```bash
df -h
```

```bash
hostnamectl
```

```bash
ip addr
```

Nota: Hyper‑V NAT no proporciona DHCP, por lo que la interfaz aparece sin IP.
La configuración de red se realiza posteriormente en config/networking.md
