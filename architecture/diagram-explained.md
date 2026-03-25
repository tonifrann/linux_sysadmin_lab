flowchart TB

    subgraph Ansible
        A[ansible-controller<br/>(Rocky Linux 9)<br/>- Ansible]
    end

    subgraph Core
        C[core-linux<br/>(Rocky Linux 9)<br/>- SSH, SELinux<br/>- Samba<br/>- Nginx + HTTPS<br/>- LVM, backups<br/>- firewalld]
    end

    subgraph Windows
        W[win-client<br/>(Windows Server 2022)<br/>- Pruebas Samba<br/>- PXE boot]
    end

    subgraph FOG
        F[fog-server<br/>(Ubuntu 22.04)<br/>- FOG, PXE, DHCP<br/>- TFTP<br/>- UFW]
    end

    subgraph Docker
        D[docker-host<br/>(Ubuntu 22.04)<br/>- Docker, Compose<br/>- Nginx container<br/>- nftables]
    end

    subgraph Monitoring
        M[monitoring<br/>(Ubuntu 22.04)<br/>- Prometheus<br/>- Node Exporter<br/>- Grafana<br/>- rsyslog (central)<br/>- iptables]
    end

    A --> C
    C <-- SMB --> W
    C <-- TFTP --> F
    C -->|HTTP/HTTPS| D
    D -->|Metrics| M
    C --> M
    F --> M
    D --> M
