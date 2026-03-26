# Diagrama de core-linux

```mermaid
flowchart TB
    SEC[Seguridad<br/>SSH, SELinux, firewalld, Fail2ban]
    SRV[Servicios<br/>Nginx, Samba]
    STG[Almacenamiento<br/>LVM, snapshots]
    BCK[Backups<br/>rsync, tar, dd]
    LOG[Logs<br/>logrotate, auditd]
    SEC --> SRV --> LOG
    STG --> BCK --> LOG
