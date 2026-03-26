# Instalación de Rocky Linux 9

## 1. Descarga de la ISO
He descargado la ISO desde la página oficial de Rocky Linux.

## 2. Configuración de la máquina virtual
- 2 vCPU
- 4 GB RAM
- 40 GB disco
- Red en modo puente/NAT

## 3. Proceso de instalación
Capturas:
- Selección de idioma
- Particionado automático/manual
- Configuración de usuario
- Configuración de red

## 4. Primer arranque
Comandos ejecutados:

Lo primero es actualizar todos los paquetes disponibles:

```bash
sudo dnf update -y
```

Asignar el nombre al servidor:

```bash
sudo hostnamectl set-hostname core-linux
```
Verificar el hostname:

```bash
hostnamectl
```
Verificar que el disco está montado correctamente:

```bash
df -h
```
Comprobar la configuración de red actual:

```bash
ip addr
```
