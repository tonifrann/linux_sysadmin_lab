# Targets monitorizados

Prometheus monitoriza los siguientes nodos del laboratorio mediante Node Exporter:

| Servidor      | Rol                   | Puerto    |
|---------------|------------------------|-----------|
| core-linux    | Servidor principal     | 9100/tcp  |
| monitoring    | Nodo local             | 9100/tcp  |
| docker-host   | Host de contenedores   | 9100/tcp  |

<img width="1914" height="794" alt="image" src="https://github.com/user-attachments/assets/0c7e3e4e-e115-4f94-83e0-4e4e52506b46" />


## Estado de los targets

- Todo los targets se encuentran en estado UP, lo que indica que Prometheus puede acceder correctamente a sus métricas.
- Los targets se resuelven por hostname en `/etc/hosts`.
- Todos los nodos exponen métricas en `:9100`.
- La lista se puede ampliar al añadir nuevos servidores.
