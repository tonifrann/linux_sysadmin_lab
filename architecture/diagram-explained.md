                               +-----------------------+
                               |   ansible-controller  |
                               |     (Rocky Linux 9)   |
                               |        - Ansible      |
                               +-----------+-----------+
                                           |
                                           |
                                           v
+-------------------+          +-----------+-----------+          +---------------------+
|    win-client     |          |         core-linux    |          |     fog-server      |
| Windows Server 22 |<-------->|     Rocky Linux 9     |<-------->|    Ubuntu 22.04     |
| - Pruebas Samba   |   SMB    | - SSH, SELinux        |   TFTP   | - FOG, PXE, DHCP    |
| - PXE boot        |          | - Samba               |          | - TFTP              |
+-------------------+          | - Nginx + HTTPS       |          | - UFW               |
                               | - LVM, backups        |          +----------+----------+
                               | - firewalld           |                     |
                               +-----------+-----------+                     |
                                           |                                 |
                                           | HTTP/HTTPS                      |
                                           v                                 |
                               +-----------+-----------+                     |
                               |        docker-host     |                    |
                               |      Ubuntu 22.04      |                    |
                               | - Docker, Compose      |                    |
                               | - Nginx container      |                    |
                               | - nftables             |                    |
                               +-----------+------------+                    |
                                           |                                 |
                                           | Metrics                         |
                                           v                                 |
                               +-----------+------------+                    |
                               |        monitoring       |<------------------+
                               |      Ubuntu 22.04       |
                               | - Prometheus            |
                               | - Node Exporter         |
                               | - Grafana               |
                               | - rsyslog (central)     |
                               | - iptables              |
                               +-------------------------+
